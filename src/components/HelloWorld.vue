<template>
  <div>
    <h1>Send SMS</h1>
    <form @submit.prevent="sendSMS">
      <div class="form-group">
        <label for="recipient">Recipient:</label>
        <input type="text" id="recipient" v-model="recipient" required />
      </div>

      <div class="form-group">
        <label for="message">Message:</label>
        <textarea id="message" v-model="message" required></textarea>
      </div>

      <button type="submit">Send</button>
    </form>

    <!-- Confirmation message -->
    <div v-if="confirmationMessage" class="confirmation">
      {{ confirmationMessage }}
    </div>
  </div>
</template>


<script>
import axios from 'axios';

export default {
  data() {
    return {
      recipient: '',
      message: '',
      confirmationMessage: '', 
    };
  },
  methods: {
    sendSMS() {
      const apiUrl = 'https://gateway.excitesms.tech/api/v3/sms/send';
      const headers = {
        'Accept': 'application/json',
        'Content-Type': 'application/json',
        'Authorization': 'Bearer AIP_KEY',
      };

      const payload = {
        recipient: this.recipient,
        sender_id: 'Demo',
        message: this.message,
      };

      axios
        .post(apiUrl, payload, { headers })
        .then(response => {
          this.confirmationMessage = 'SMS sent successfully';
          console.log('SMS sent successfully:', response.data);
          // You can handle the success response here
        })
        .catch(error => {
          this.confirmationMessage = 'Error sending SMS';
          console.error('Error sending SMS:', error);
          // You can handle the error response here
        });
    },
  },
};
</script>
<style>
/* Add some basic CSS styling */
.form-group {
  margin-bottom: 20px;
}

label {
  display: block;
  font-weight: bold;
}

input,
textarea {
  width: 70;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

button {
  background-color: #007BFF;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.confirmation {
  margin-top: 20px;
  padding: 10px;
  background-color: #28a745;
  color: white;
  border-radius: 5px;
}
</style>
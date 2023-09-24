<template>
    <div>
      <h1>Send SMS</h1>
      <form @submit.prevent="sendSMS">
        <label for="recipient">Recipient:</label>
        <input type="text" id="recipient" v-model="recipient" required />
  
        <label for="message">Message:</label>
        <textarea id="message" v-model="message" required></textarea>
  
        <button type="submit">Send</button>
      </form>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  export default {
    data() {
      return {
        recipient: '',
        message: '',
      };
    },
    methods: {
      sendSMS() {
        const apiUrl = 'https://gateway.excitesms.tech/api/v3/sms/send';
        const headers = {
          'Accept': 'application/json',
          'Content-Type': 'application/json',
          'Authorization': 'Bearer 1|3aOFpH9uOQjQx5s1Z1niX2mjpuJXXDGITj6r2V8m',
        };
  
        const payload = {
          recipient: this.recipient,
          sender_id: 'ExciteSMS',
          message: this.message,
        };
  
        axios
          .post(apiUrl, payload, { headers })
          .then(response => {
            console.log('SMS sent successfully:', response.data);
            // You can handle the success response here
          })
          .catch(error => {
            console.error('Error sending SMS:', error);
            // You can handle the error response here
          });
      },
    },
  };
  </script>
  
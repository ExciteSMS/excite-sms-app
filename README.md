# Excite SMS Vue.js Application

This is a simple Vue.js application for sending SMS using the Excite SMS API. You can use this application to send SMS messages to recipients using the Excite SMS service.

## Features

- Send SMS messages using the Excite SMS API.
- Basic form for entering recipient number and message.
- Confirmation message for successful or failed SMS sending.

## Technologies Used

- Vue.js
- Axios for making API requests

## Getting Started

To get started with this application, follow these steps:

1. Clone the repository to your local machine:

   ```bash
   git clone https://github.com/kazashim/excite-sms-app.git
   cd excite-sms-app-sms-app
   ```

2. Install the project dependencies:

   ```bash
   npm install
   ```

3. Run the application:

   ```bash
   npm run serve
   ```

4. Access the application in your web browser at `http://localhost:8080`.

## Usage

1. Fill out the recipient phone number and message in the form provided.
2. Click the "Send" button to send the SMS using the Excite SMS API.
3. A confirmation message will be displayed indicating whether the SMS was sent successfully or if an error occurred.

## API Configuration

To use this application, you need to configure the Excite SMS API credentials. Modify the `Authorization` header in the `HelloWorld.vue` component to include your API key:

```javascript
const headers = {
  'Accept': 'application/json',
  'Content-Type': 'application/json',
  'Authorization': 'Bearer YOUR_API_KEY_HERE',
};
```

## Customize

You can customize the application further by adding your own styles and features. Feel free to modify the Vue components and CSS as needed.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Excite SMS for providing the SMS gateway API.

---

Happy SMS sending!
```

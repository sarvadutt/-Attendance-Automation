# -Attendance-Automation


A simple AWS Lambda function to automate your **Jobcan** work attendance using **GPS-based triggers from IFTTT**.

This project allows you to clock in and out of Jobcan automatically by setting up cloud-based Lambda functions, triggered via API Gateway and IFTTT.

---

## 🚀 Features

- Automates Jobcan attendance (work start and end)
- Integrates with [IFTTT](https://ifttt.com) for GPS-based triggers
- Fully serverless using [AWS Lambda](https://aws.amazon.com/lambda/)
- Easy to set up and extend

---

## 🛠️ Installation & Setup

1. **Create Two AWS Lambda Functions**
   - `jobcanStart` (for clock-in)
   - `jobcanEnd` (for clock-out)

2. **Set Environment Variable**
   - `JOBCAN_ADIT` to `work_start` or `work_end` respectively.

3. **Create an Amazon API Gateway**
   - Link it to your Lambda functions to expose public HTTP endpoints.

4. **Create IFTTT Applets**
   - Use the *"Webhooks"* service to send a POST request to the API endpoint.
   - Include your Jobcan credentials in the request body (example below).

---

## 🧪 Example Request Body

```json
{
  "credential": {
    "client_id": "your-company-name",
    "account_type": "staff",
    "login_id": "yourname@example.com",
    "password": "yoursecretpassword"
  }
}
````

> ⚠️ Ensure your credentials are stored securely and are **not hardcoded** in production setups.

---

## ⚠️ Security Note

Currently, the API endpoints are publicly accessible. Consider adding:

* Throttling
* Authentication (e.g., API keys, OAuth)
* IP restrictions

---

## 📌 Future Improvements

* Detailed step-by-step setup guide
* Add authentication mechanisms
* Publish a public IFTTT applet template

---

## 👨‍💻 Author

Sarva Dutt Akavarapu
Email: [sarvadutt25@gmail.com](mailto:sarvadutt25@gmail.com)

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.



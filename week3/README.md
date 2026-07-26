# WeatherGuard — Week 3

Part of the **Akwannya Hub Cloud Peer Project**.

## 🎯 Focus
Adding real authentication to the login/signup pages using AWS Lambda and Amazon Cognito.

## 🏗️ Architecture

- **Amazon Cognito**: Manages user sign-up, sign-in, and identity/session handling.
- **AWS Lambda**: Handles backend logic for authentication requests.
- Builds directly on top of the Week 2 login/signup pages, which previously had no backend behind them.

```
User → CloudFront → S3 (Static Site)
                 ↓
        Login/Signup Page → Lambda → Cognito (User Pool)
```

## 🚀 Deployment Steps

1. Create a Cognito User Pool to manage users.
2. Create a Cognito App Client for the WeatherGuard frontend.
3. Write Lambda function(s) to handle sign-up/sign-in requests (or connect the frontend directly to Cognito via the Amplify/Cognito SDK).
4. Connect the Week 2 login/signup form submissions to Cognito (via Lambda or the SDK).
5. Test user registration and login end-to-end.

## 📝 Notes / Lessons Learned

- *(Add any issues faced connecting Lambda/Cognito, IAM permission fixes, or testing notes here.)*

## 🧰 Tech Stack

| Layer | Technology |
|-------|------------|
| Hosting | Amazon S3 |
| CDN / HTTPS | Amazon CloudFront |
| Authentication | AWS Lambda + Amazon Cognito |
| Frontend | HTML, CSS, JavaScript |

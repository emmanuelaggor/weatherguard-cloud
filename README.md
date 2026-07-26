# weatherguard-cloud
awscloudproject
# WeatherGuard ☁️🌦️

WeatherGuard is a cloud-hosted weather application built as part of the **Akwannya Hub Cloud Peer Project**. This repository documents our team's progressive, week-by-week journey building and evolving the app using AWS cloud services.

## 📌 Project Overview

WeatherGuard started as a simple static weather web page and is being expanded over three weeks into a more complete, production-style cloud deployment. Each week's work, decisions, and lessons learned are documented separately (see links below).

## 🗂️ Weekly Progress & Documentation

| Week | Focus | Write-up |
|------|-------|----------|
| Week 1 | Static site hosting on Amazon S3; added CloudFront as a follow-up fix | [Week 1 README](week1) |
| Week 2 | Redesigned interface; added login & signup pages (frontend only) | [Week 2 README](week2) |
| Week 3 | Added real authentication using AWS Lambda + Amazon Cognito | [Week 3 README](week3) |

> These link to the `week1-README.md`, `week2-README.md`, and `week3-README.md` files in this repo. If you'd rather publish standalone Medium articles, swap these links for the article URLs instead.

## 🏗️ Architecture

### Week 1 — Static Site Hosting
- **Amazon S3**: Hosts the static website files (HTML, CSS, JS) as a static website / origin bucket.
- **Amazon CloudFront**: Added as a fix after the initial deployment to serve the S3 content through a CDN, enabling caching and HTTPS.
- **Route 53**: Not yet used — the group does not currently have a registered domain name, so DNS mapping was skipped for now.

```
User → CloudFront (CDN/HTTPS) → S3 Bucket (Static Site)
```

### Week 2 — Interface Redesign & Auth Pages (UI only)
- Redesigned the website's interface for a better user experience.
- Added **login** and **signup** pages to the frontend.
- No AWS authentication service was wired up yet at this stage — the pages existed as UI only.
- Continued to serve through the same S3 + CloudFront setup from Week 1.

### Week 3 — Real Authentication
- **AWS Lambda**: Handles backend logic for authentication requests.
- **Amazon Cognito**: Manages user sign-up, sign-in, and identity/session handling for the login and signup pages built in Week 2.

```
User → CloudFront → S3 (Static Site)
                 ↓
        Login/Signup Page → Lambda → Cognito (User Pool)
```

## 🚀 Getting Started

### Prerequisites
- An AWS account
- AWS CLI configured (`aws configure`)
- A registered domain name (for Route 53)

### Deployment Steps

**Week 1 — S3 + CloudFront**
1. Create an S3 bucket and enable static website hosting.
2. Upload the site's static files (`index.html`, CSS, JS, images) to the bucket.
3. Set the bucket policy to allow public read access (or use CloudFront Origin Access Control instead of public S3 access).
4. Create a CloudFront distribution with the S3 bucket as the origin.
5. *(Route 53 skipped for now — no domain name registered yet. Once a domain is available, create a hosted zone and add an A/ALIAS record pointing to the CloudFront distribution.)*

**Week 2 — Interface & Auth Pages**
1. Redesign the site's HTML/CSS/JS for the updated interface.
2. Add login and signup page markup and client-side form handling.
3. Re-upload updated files to the S3 bucket and invalidate the CloudFront cache so changes go live.

**Week 3 — Lambda + Cognito Authentication**
1. Create a Cognito User Pool to manage users.
2. Create a Cognito App Client for the WeatherGuard frontend.
3. Write Lambda function(s) to handle sign-up/sign-in requests (or use Cognito Hosted UI/SDK directly from the frontend).
4. Connect the login/signup page's form submissions to Cognito (via Lambda or the Amplify/Cognito SDK).
5. Test user registration and login end-to-end.

## 🧰 Tech Stack

| Layer | Technology |
|-------|------------|
| Hosting | Amazon S3 |
| CDN / HTTPS | Amazon CloudFront |
| DNS | Amazon Route 53 *(planned — pending domain name)* |
| Authentication | AWS Lambda + Amazon Cognito |
| Frontend | HTML, CSS, JavaScript |

## 👥 Team

- *(Add team member names/roles here)*

## 📄 License

*(Add a license, e.g., MIT, or state "For educational purposes as part of Akwannya Hub Cloud Peer Project")*

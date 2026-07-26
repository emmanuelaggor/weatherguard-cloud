# WeatherGuard — Week 2

Part of the **Akwannya Hub Cloud Peer Project**.

## 🎯 Focus
Redesigning the interface and adding login/signup pages to WeatherGuard.

## 🏗️ What Changed From Week 1

- Redesigned the website's interface for a better user experience.
- Added **login** and **signup** pages to the frontend.
- No AWS authentication service was wired up yet at this stage — the pages exist as UI only, ready for backend integration in Week 3.
- Continued to serve through the same S3 + CloudFront setup from Week 1.

```
User → CloudFront (CDN/HTTPS) → S3 Bucket (Static Site + New UI + Login/Signup Pages)
```

## 🚀 Deployment Steps

1. Redesign the site's HTML/CSS/JS for the updated interface.
2. Build the login and signup page markup and client-side form handling.
3. Re-upload updated files to the S3 bucket.
4. Invalidate the CloudFront cache so the changes go live.

## 📝 Notes / Lessons Learned

- Kept the whole stack on AWS-only resources, consistent with the project requirement.
- Login/signup pages were built ahead of the actual authentication logic, which is planned for Week 3 using Lambda and Cognito.

## 🧰 Tech Stack

| Layer | Technology |
|-------|------------|
| Hosting | Amazon S3 |
| CDN / HTTPS | Amazon CloudFront |
| Frontend | HTML, CSS, JavaScript (redesigned UI, login/signup pages) |

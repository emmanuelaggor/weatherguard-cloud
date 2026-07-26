# WeatherGuard — Week 1

Part of the **Akwannya Hub Cloud Peer Project**.

## 🎯 Focus
Deploying WeatherGuard as a static weather report website on AWS.

## 🏗️ Architecture

- **Amazon S3**: Hosts the static website files (HTML, CSS, JS) as a static website / origin bucket.
- **Amazon CloudFront**: Initially skipped, then added as a fix after the first deployment to serve the S3 content through a CDN, enabling caching and HTTPS.
- **Route 53**: Not used yet — the group doesn't have a registered domain name, so DNS mapping was skipped for now.

```
User → CloudFront (CDN/HTTPS) → S3 Bucket (Static Site)
```

## 🚀 Deployment Steps

1. Create an S3 bucket and enable static website hosting.
2. Upload the site's static files (`index.html`, CSS, JS, images) to the bucket.
3. Set the bucket policy to allow public read access (or use CloudFront Origin Access Control instead of public S3 access).
4. Create a CloudFront distribution with the S3 bucket as the origin.
5. Verify the site loads through the CloudFront URL.

## 📝 Notes / Lessons Learned

- CloudFront was missed in the initial submission and had to be added afterward — a reminder to map out the full architecture (S3 + CDN + DNS) before starting the build.
- Route 53 setup is on hold until the group registers a domain name.

## 🧰 Tech Stack

| Layer | Technology |
|-------|------------|
| Hosting | Amazon S3 |
| CDN / HTTPS | Amazon CloudFront |
| DNS | Amazon Route 53 *(planned — pending domain name)* |

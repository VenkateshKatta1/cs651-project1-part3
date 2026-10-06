# CS651 Project 1 — StudyBoard

StudyBoard is a Computer Vision and Machine Learning startup concept designed to connect classroom whiteboard photographs with the spoken explanations that accompanied them.

This repository contains the frontend application developed for **CS651 Project 1** and the deployment work completed for **Part 3 using Amazon S3 Static Website Hosting**.

## Project Features

The StudyBoard frontend includes:

- Static **Home, About, and Contact** pages built with HTML, CSS, Bootstrap, and client-side JavaScript.
- Updated images and visual content throughout the website.
- A React Single Page Application at `/app/`.
- Reusable React components for:
  - Study sessions
  - Whiteboard content
  - Flashcards
  - Tutor interaction
- Interactive flashcard navigation and flipping.
- Session selection functionality.
- A React-based sign-in page at `/login/`.
- A create-account interface integrated with the login page.
- Apache and Docker configuration in `DockerContainer/` for the Part 2 EC2 deployment.
- Amazon S3 Static Website Hosting configuration for the Part 3 deployment.

---

## Part 3 — AWS S3 Deployment

For Part 3 of the project, the StudyBoard frontend was deployed using **Amazon S3 Static Website Hosting**.

### Deployment Information

| Item | Configuration |
|---|---|
| AWS Service | Amazon S3 |
| AWS Region | US East (Ohio) |
| Region Code | `us-east-2` |
| S3 Bucket | `cs651-studyboard` |
| Hosting Type | Static Website Hosting |
| Index Document | `index.html` |
| Website Status | Live |
| Current AWS Cost | USD 0.00 |

### Live Website

http://cs651-studyboard.s3-website.us-east-2.amazonaws.com/

---

## Run Locally

### Requirements

Install:

- Node.js 20+
- npm

From the project directory, run:

```bash
npm install
npm run dev
```

Vite will display a local development URL.

Test the following pages:

```text
/
 /about.html
 /contact.html
 /app/
 /login/
```

---

## Production Build

To create the production version of the website, run:

```bash
npm install
npm run build
```

The build process generates a:

```text
dist/
```

directory containing the files required for deployment.

The production build includes:

```text
dist/
├── app/
├── assets/
├── css/
├── images/
├── js/
├── login/
├── about.html
├── contact.html
└── index.html
```

---

## Deploying to Amazon S3

The production contents of the `dist` directory were uploaded to the root of the Amazon S3 bucket.

### Deployment Process

1. Build the production website:

```bash
npm run build
```

2. Open the AWS Management Console.

3. Navigate to **Amazon S3**.

4. Create or open the bucket:

```text
cs651-studyboard
```

5. Upload all files and folders contained inside:

```text
dist/
```

6. Enable **Static Website Hosting** from the S3 bucket's **Properties** tab.

7. Configure the index document as:

```text
index.html
```

8. Configure the bucket permissions to allow public read access to the website files.

9. Open the generated S3 website endpoint.

### S3 Website Endpoint

http://cs651-studyboard.s3-website.us-east-2.amazonaws.com/

---

## Deployment Verification

After deployment, the following pages were tested:

- Home
- About
- Contact
- App
- Sign In

The deployed website was verified to load:

- HTML content
- CSS styling
- Navigation
- JavaScript functionality
- React components
- Images
- Supporting assets

---

## Issue Encountered During Deployment

During the initial S3 deployment, only the HTML files were uploaded.

The website opened successfully, but the following content was missing:

- Custom CSS styling
- JavaScript navigation
- React assets
- Images
- Supporting files

### Solution

The complete contents of the production `dist` directory were uploaded to the S3 bucket.

After uploading the CSS, JavaScript, React assets, images, and supporting folders, the website displayed correctly.

---

## AWS Cost

Amazon S3 pricing can depend on:

- Storage
- Requests
- Data transfer
- AWS Region
- Account eligibility for free usage

For the current billing period:

```text
Estimated AWS Cost: USD 0.00
Billing Period: October 1 – October 31, 2026
```

The StudyBoard deployment currently has very low storage and request usage.

---

## GitHub Wiki

Additional Part 3 deployment documentation is available in the repository Wiki.

The required Wiki pages are:

- **S3 Bucket Setup**
- **YouTube Link**

The S3 Bucket Setup page contains screenshots of:

- The S3 bucket
- Static website hosting configuration
- Uploaded website files
- The deployed StudyBoard website
- Deployment issues and solutions
- AWS cost information

---

## Part 2 — Docker / Apache

The repository also contains the Apache Docker configuration used for the EC2 deployment portion of the project.

From the repository root:

```bash
docker build -f DockerContainer/Dockerfile -t studyboard:project1 .
docker run --rm -p 8080:80 studyboard:project1
```

Then open:

```text
http://localhost:8080
```

---

## Technologies Used

- HTML
- CSS
- Bootstrap
- JavaScript
- React
- Vite
- Node.js
- Docker
- Apache
- Amazon EC2
- Amazon S3

---

## Conclusion

StudyBoard demonstrates the development and deployment of a modern frontend web application using HTML, CSS, JavaScript, React, and AWS services.

For Part 3, the production-built frontend was successfully deployed using **Amazon S3 Static Website Hosting** and is publicly accessible through the AWS S3 website endpoint.

### Live StudyBoard Website

http://cs651-studyboard.s3-website.us-east-2.amazonaws.com/

AI use: Claude (Anthropic), ChatGPT (OpenAI) and GitHub Copilot helped plan the deployment steps, work through code and commands, check AWS prices and limits, and draft and edit this documentation. We ran every command, made every console change and took every screenshot ourselves.

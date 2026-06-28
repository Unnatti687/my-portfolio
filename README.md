# Unnatti Dixit - Portfolio

A bespoke, editorial-style personal portfolio designed by an aspiring Cloud & DevOps Engineer. This project eschews generic developer templates in favor of a clean, sophisticated, and memorable aesthetic reminiscent of high-end design portfolios. Built from scratch with semantic HTML, CSS (utilizing modern Grid and Flexbox), and Vanilla JavaScript.

## Features

- **Editorial Design Language:** Expansive typography, strict grid alignment, and intentional whitespace.
- **Production-Ready Code:** Fully responsive across all devices with zero horizontal scrolling.
- **Subtle Interactions:** Scroll-triggered reveal animations, image hover zooms, and a lightweight parallax effect for the hero section.
- **Zero Frameworks:** Completely free of heavy libraries like React or Tailwind, ensuring lighting-fast load times and easy maintenance.
- **Accessible:** Semantic markup, high contrast, and keyboard-navigable structure.

## Live Website
🔗 https://d26vr9h5ujsh9h.cloudfront.net

## Technologies Used

- **HTML5:** Semantic document structure
- **CSS3:** Custom properties (variables), Grid, Flexbox, Keyframe animations
- **JavaScript (Vanilla):** DOM manipulation, Intersection Observer API
- ## Technologies Used
- Amazon S3
- Amazon CloudFront
- Git & GitHub

## Folder Structure

```
portfolio/
├── assets/
│   ├── profile.jpg      # Your primary hero image
│   ├── project1.jpg     # Image for project 1
│   ├── project2.jpg     # Image for project 2
│   └── project3.jpg     # Image for project 3
├── index.html           # Main markup file
├── styles.css           # Global stylesheets
├── script.js            # Interactivity & animations
└── README.md            # Project documentation
```

## How to Customize

1. **Colors & Fonts:** Open `styles.css`. At the very top, you'll find a `:root` section containing all CSS variables. Modify these hex codes to globally update the theme.
2. **Content:** Open `index.html`. Edit the text directly within the semantic tags (`<h1>`, `<p>`, `<h3>`, etc.).
3. **Contact Links:** Locate the `<section id="contact">` block in `index.html` and replace the `#` inside the `href` attributes with your actual GitHub and LinkedIn URLs.

## How to Replace Images

1. Place your professional profile photo inside the `assets/` folder and name it exactly `profile.jpg`.
2. Do the same for your project images, naming them `project1.jpg`, `project2.jpg`, etc.
3. If using different filenames, update the `src` attribute within the `<img>` tags in `index.html`. 
*(Note: Unsplash placeholder links are currently acting as fallbacks via the `onerror` attribute).*

## How to Add New Projects

1. Open `index.html` and find the `<!-- Projects Section -->`.
2. Copy an entire `<article class="project-item">...</article>` block.
3. Paste it directly below the last project block inside the `.projects-wrapper` container.
4. Update the image source, tags, title, description, and button links.

## AWS Deployment Guide

### Deploying to Amazon S3 (Hosting)
1. Log into your **AWS Management Console**.
2. Navigate to the **S3** service and click **Create bucket**.
3. Name your bucket (e.g., `unnattidixit-portfolio`).
4. **Important:** Uncheck *Block all public access* and acknowledge the warning.
5. Create the bucket, open it, and navigate to the **Properties** tab.
6. Scroll down to **Static website hosting**, click **Edit**, choose **Enable**, type `index.html` as the Index document, and save.
7. Navigate to the **Permissions** tab. Edit the **Bucket policy** to allow public `s3:GetObject` access.
8. Go to the **Objects** tab, click **Upload**, and upload your `index.html`, `styles.css`, `script.js`, and `assets/` folder.

### Configuring CloudFront (CDN & HTTPS)
1. Navigate to the **CloudFront** service in AWS.
2. Click **Create Distribution**.
3. For the **Origin domain**, select the S3 website endpoint you just created.
4. Under **Viewer Protocol Policy**, select **Redirect HTTP to HTTPS**.
5. Leave the remaining settings as default (unless attaching a custom domain/SSL via AWS Certificate Manager).
6. Click **Create Distribution**. Once the status changes to *Deployed*, you can use the provided CloudFront URL to view your secure, globally-cached website.

## Future Improvements

- Connect a custom domain name using AWS Route 53.
- Expand the animations using GSAP for more complex sequencing.
- Integrate AWS API Gateway and a Lambda function to handle a dynamic email contact form.

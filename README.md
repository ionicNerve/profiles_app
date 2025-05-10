# Profiles App

A lightweight, secure profile management application built with React and Vite.  
This project demonstrates a simple interface for displaying user profiles along with user authentication and security features using AWS Amplify and AWS WAF.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Local Development](#local-development)
- [Deployment](#deployment)
- [Security Enhancements](#security-enhancements)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

The **Profiles App** is a demonstration of how to build a modern web application that securely displays user profile data. Utilizing AWS Amplify's authentication and data services, the app retrieves user profiles from a backend and displays them in a responsive grid layout. In addition, security is enhanced by leveraging AWS WAF through the Amplify Console to protect against common web threats.

---

## Features

- **User Authentication:**  
  Integrated using AWS Amplify’s [Authenticator](https://ui.docs.amplify.aws/react/connected-components/authenticator) component to manage secure logins and sign-outs.

- **Data Fetching:**  
  Retrieves user profiles from an AWS Amplify backend service using a generated client and displays them in a grid.

- **Responsive Design:**  
  Built with React and styled using Amplify UI components to ensure a modern, cohesive look.

- **Security Services:**  
  Easily enable AWS Web Application Firewall (WAF) via the Amplify Console to block untrustworthy traffic and mitigate common web attacks.

- **Custom Favicon:**  
  A brain illustration combined with a body outline is used as the tab icon, symbolizing the smart, secure aspect of the app.

---

## Technologies Used

- **React & Vite:** Quick development setup with fast refresh and modern tooling.
- **AWS Amplify:** For authentication, backend data, and configuration management.
- **AWS WAF (via Amplify Console):** Protects the deployment by filtering out bad actors.
- **CSS & SVG:** Lightweight styling and custom favicon design.

---

## Getting Started

### Prerequisites

- **Node.js & npm:** Ensure you have Node.js (v14 or later) and npm installed on your machine.
- **AWS CLI:** For managing Amplify and AWS services (if you wish to update configurations).
- **Amplify CLI:** Install via npm:  
  ```bash
  npm install -g @aws-amplify/cli
  ```

### Installation

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/ionicNerve/profiles_app.git
   cd profiles_app
   ```

2. **Install Dependencies:**
   ```bash
   npm install
   ```

3. **Set Up AWS Amplify:**  
   Ensure your `amplify_outputs.json` is correctly configured with your AWS services. (See [AWS Amplify Documentation](https://docs.amplify.aws/) for setup guidance.)

### Local Development

Run the application locally using Vite:
```bash
npm run dev
```
Open [http://localhost:3000](http://localhost:3000) to view the app in your browser.

---

## Deployment

This project can be deployed directly through AWS Amplify.
1. **Connect Your GitHub Repository:**  
   Link the repository to Amplify via the Amplify Console.
2. **Configure Build Settings:**  
   Amplify auto-detects the Vite build process. Ensure your build commands reflect:
   ```yaml
   version: 1
   frontend:
     phases:
       preBuild:
         commands:
           - npm ci --legacy-peer-deps # if needed for dependency resolution
       build:
         commands:
           - npm run build
     artifacts:
       baseDirectory: dist
       files:
         - '**/*'
     cache:
       paths:
         - node_modules/**/* 
   ```
3. **Enable AWS WAF:**  
   Use the built-in toggle in the Amplify Console to integrate AWS WAF (Web Application Firewall) with your CloudFront distribution for extra security.

---

## Security Enhancements

### AWS WAF Integration

- **What it Does:**  
  Protects against common web attacks (SQL injection, cross-site scripting, etc.) by filtering inbound HTTP requests.

- **How it's Enabled:**  
  In the Amplify Console, use the “Add Firewall” option. Pre-configured rules from AWS Managed Rule Groups are applied, and you can customize IP and country filtering as needed. This provides an extra layer of protection for your application.

### Email and User Verification (Future Enhancements)

- **Validation & Double Opt-In:**  
  Implementing additional email syntax validation and an opt-in confirmation process helps prevent untrustworthy email addresses from creating profiles.

---

## Project Structure

```
profiles_app/
├── amplify_outputs.json  # AWS Amplify configuration details
├── public/
│   ├── favicon.svg       # Custom favicon (brain with body outline)
│   └── index.html
├── src/
│   ├── App.jsx           # Main React component showcasing user profiles
│   ├── index.css         # Global styles & user interface configurations
│   └── ...               # Other components and assets
├── package.json
└── README.md             # This file
```

---

## Contributing

Contributions are welcome! Please feel free to open an [issue](https://github.com/ionicNerve/profiles_app/issues) or submit a pull request with enhancements, bug fixes, or new ideas.

---

## License

Distributed under the MIT License. See `LICENSE` for more information.

---

## Contact

For any questions or feedback, feel free to reach out via [GitHub Issues](https://github.com/ionicNerve/profiles_app/issues).

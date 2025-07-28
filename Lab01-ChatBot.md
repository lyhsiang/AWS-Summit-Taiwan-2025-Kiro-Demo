# Lab 1: Getting Started with Kiro

Welcome to your first hands-on experience with Kiro! In this lab, you'll learn how to use Kiro's AI capabilities to build applications quickly and efficiently.

## Exercise 1: Building a Chatbot UI with AWS Bedrock

In this exercise, you'll create a chatbot interface that integrates with AWS Bedrock, demonstrating how Kiro can help you build AI-powered applications with minimal effort.

### 🎯 Objective
Build and deploy a chatbot UI that will be hosted on AWS S3 and served through CloudFront, with proper security configurations and a placeholder backend interaction.

### 📋 Prerequisites
- Kiro IDE installed and running
- Basic understanding of web development
- AWS account with S3 and CloudFront access
- AWS CLI configured (for deployment)

### 🚀 Step-by-Step Instructions

#### Step 1: Create Your Project Folder
1. On your computer, create a folder with the name `MyCoolChatbot`
2. This will be your project workspace for the chatbot application

#### Step 2: Open Project in Kiro
1. Launch Kiro IDE
2. Click **"Open a project"** button
3. Select the newly created `MyCoolChatbot` folder
4. Kiro will initialize the project workspace

![Kiro Start Screen](../resources/images/kiro-start-screen.png)

#### Step 3: Access the Let's Build Feature
1. In Kiro, navigate to the **"Let's build"** page
2. You will see two options available:
   - **Vibe** - Chat first, then build. Explore ideas and iterate as you discover needs
   - **Spec** - Plan first, then build. Create requirements and design before coding starts

3. For this exercise, select **"Vibe"** mode
4. Set the model to **"Claude Sonnet 3.7"** (or the latest available version)
5. Make sure **Autopilot** is enabled

![Kiro Let's Build Interface](../resources/images/kiro-lets-build.png)

#### Step 4: Create the Chatbot UI with AWS Deployment
In the chat area, enter the following prompt:

```
Build and deploy a simple chatbot UI. I want the files to be hosted on S3 and served by CloudFront. For security reasons, I do not want public access to my S3 bucket. Also, do not enable versioning for the S3 bucket.

The chatbot UI interacts with the back end with POST requests. We will build the back end separately in later steps. For the time being, when the user enters a message, the chatbot UI does not send the POST request, but simply respond with an ACK.

Additional requirements:
- Clean, modern interface with a dark theme
- Chat messages displayed in a conversation format
- Input field for user messages and send button
- Title showing "AWS Bedrock 聊天機器人" (AWS Bedrock Chatbot)
- Support for Chinese and English text
- Responsive design that works on different screen sizes
- When user sends a message, show "ACK" response as placeholder
```

#### Step 5: Review Generated Infrastructure and Code
1. Kiro will generate:
   - Chatbot UI files (HTML, CSS, JavaScript)
   - AWS CloudFormation or CDK templates for S3 and CloudFront
   - Deployment scripts or instructions
2. Review the generated files and infrastructure code
3. Test the interface locally first
4. Use Kiro's chat to make adjustments:
   - "Make the chat bubbles more rounded"
   - "Adjust the CloudFront distribution settings"
   - "Improve the S3 bucket security configuration"

#### Step 6: Deploy to AWS
1. Follow Kiro's deployment instructions
2. Verify that:
   - S3 bucket is created without public access
   - CloudFront distribution is properly configured
   - Versioning is disabled on the S3 bucket
3. Test the deployed chatbot UI
4. Confirm ACK responses work when sending messages

### 📁 Expected Project Structure
After completion, your project should contain:
```
MyCoolChatbot/
├── src/
│   ├── index.html          # Main HTML file
│   ├── styles.css          # Styling for the chatbot
│   └── script.js           # JavaScript with ACK functionality
├── infrastructure/
│   ├── cloudformation.yaml # AWS infrastructure template
│   └── deploy.sh           # Deployment script
├── README.md               # Project documentation
└── package.json            # Project configuration (if applicable)
```

### 🎨 Expected Result
Your chatbot should look similar to this:

<img width="1451" height="999" alt="image (33)" src="https://github.com/user-attachments/assets/2efe5a5b-1952-49d0-9c5a-bd24a541148c" />


**Key Features Implemented:**
- Dark theme interface matching AWS design patterns
- Bilingual support (Chinese/English)
- Clean message bubbles with proper spacing
- Responsive input area with send button
- Professional header with AWS Bedrock branding
- ACK response functionality (placeholder for backend)
- S3 hosting with CloudFront distribution
- Secure S3 bucket configuration (no public access)
- No versioning enabled on S3 bucket

### 🔧 Next Steps
Once you have the chatbot UI deployed:
1. Test the interface thoroughly on the CloudFront URL
2. Verify ACK responses work correctly
3. Check AWS console to confirm:
   - S3 bucket has no public access
   - CloudFront distribution is active
   - No versioning is enabled on S3
4. Prepare for Exercise 2 where we'll build the backend API

### 💡 Tips for Success
- Use Kiro's conversational approach - describe what you want in natural language
- Don't hesitate to ask for modifications or improvements
- Kiro learns from your feedback, so be specific about what you like or dislike
- Take advantage of the Vibe mode's iterative nature

### 🐛 Troubleshooting
If you encounter issues:

**Local Development:**
1. Check that all files are properly saved
2. Verify your browser supports modern JavaScript features
3. Test ACK functionality by sending messages

**AWS Deployment:**
1. Verify AWS CLI is configured correctly
2. Check S3 bucket permissions (should not be public)
3. Confirm CloudFront distribution status is "Deployed"
4. Test the CloudFront URL, not the S3 URL directly

**Common Issues:**
- If deployment fails: Check AWS permissions for S3 and CloudFront
- If ACK doesn't work: Verify JavaScript console for errors
- If styling is broken: Check CSS file paths in deployed version

Use Kiro's chat for help: "The deployment failed, can you help troubleshoot the CloudFormation template?"

---

### ✅ Success Criteria
Your exercise is complete when you have:
- [ ] Chatbot UI running locally with ACK responses
- [ ] S3 bucket created without public access
- [ ] CloudFront distribution serving the chatbot UI
- [ ] No versioning enabled on S3 bucket
- [ ] Chatbot accessible via CloudFront URL
- [ ] ACK responses working in the deployed version

---

**Time Estimate:** 25-30 minutes  
**Difficulty:** Intermediate  
**Next:** [Exercise 2 - Backend API Integration](../lab-02-aws-integration/README.md)

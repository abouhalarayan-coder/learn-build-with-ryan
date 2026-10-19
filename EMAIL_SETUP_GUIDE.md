# Contact Form Setup Guide - EmailJS Integration

Your contact form is now ready to send emails! Follow these steps to activate it:

## Step 1: Sign up for EmailJS (Free)
1. Go to https://www.emailjs.com/
2. Click "Sign Up" (it's free for up to 200 emails/month)
3. Create an account with your email

## Step 2: Get Your Public Key
1. After signing up, go to your EmailJS dashboard
2. Click on "Account" or "Settings"
3. Look for your **Public Key** (it looks like: `abc123xyz789...`)
4. Copy it

## Step 3: Update script.js with Your Public Key
1. Open `script.js` in your text editor
2. Find the line: `emailjs.init("YOUR_PUBLIC_KEY_HERE");`
3. Replace `YOUR_PUBLIC_KEY_HERE` with your actual public key from step 2
4. Save the file

## Step 4: Create an Email Service
1. In EmailJS dashboard, go to **Email Services** 
2. Click "Add Service" 
3. Choose your email provider (Gmail, Outlook, etc.) or use "Gmail"
4. Connect your email account
5. Copy the **Service ID** (looks like: `service_abc123xyz...`)

## Step 5: Create an Email Template
1. In EmailJS dashboard, go to **Email Templates**
2. Click "Create New Template"
3. Fill in:
   - **Template Name**: Contact Form (or anything you want)
   - **Subject**: `New message from {{from_name}}`
   - **Content** (in the email body):
   ```
   Name: {{from_name}}
   Email: {{from_email}}
   
   Message:
   {{message}}
   ```
4. Copy the **Template ID** (looks like: `template_abc123xyz...`)

## Step 6: Update script.js with Service and Template IDs
1. Open `script.js` again
2. Find these two lines around line 46-47:
   - `"service_YOUR_SERVICE_ID"` - replace with your Service ID
   - `"template_YOUR_TEMPLATE_ID"` - replace with your Template ID
   - `"your-email@example.com"` - replace with YOUR email (where you want to receive messages)
3. Save the file

## Step 7: Test It!
1. Go to your website's home page
2. Scroll down to "Let's connect" section
3. Fill in the form and click "Send Message"
4. You should receive an email at the address you specified!

## Troubleshooting

**"Email not received"** → Check that your email address in step 6 is correct
**"Error sending message"** → Make sure your Public Key, Service ID, and Template ID are all correct
**"Still not working"** → Open the browser console (F12 → Console tab) and check for error messages

## Alternative (No Setup Required)
If you want emails to go directly to a contact address without any setup, you can also add a simple "mailto:" link instead:
```html
<a href="mailto:your-email@example.com">Send me an email directly</a>
```

---
**Questions?** EmailJS has great documentation at https://www.emailjs.com/docs/

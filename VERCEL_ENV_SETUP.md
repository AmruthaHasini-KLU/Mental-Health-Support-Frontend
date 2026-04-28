# Vercel Environment Variables Setup

## Problem
Forum posts aren't working because the `VITE_API_BASE_URL` environment variable isn't set in Vercel production.

## Solution
You need to set environment variables in your Vercel project dashboard:

### Steps:
1. Go to [vercel.com](https://vercel.com) → Select your **mental-health-support** project
2. Click **Settings** (top tab)
3. Select **Environment Variables** (left sidebar)
4. Add the following variables:

#### Variable 1: API Base URL
- **Name:** `VITE_API_BASE_URL`
- **Value:** `https://mental-health-support-backend.onrender.com/api`
- **Environments:** Select all (Production, Preview, Development)
- Click **Save**

#### Variable 2: API Timeout (Optional)
- **Name:** `VITE_API_TIMEOUT`
- **Value:** `30000`
- **Environments:** Select all
- Click **Save**

### After Setting Variables:
1. Go back to your project **Deployments** tab
2. Click the **...** menu on the latest deployment
3. Select **Redeploy** to rebuild with new environment variables
4. Wait for deployment to complete
5. Test forum posting again

## Test the Fix:
1. Open your Vercel URL in browser
2. Open **Developer Console** (F12)
3. Go to Forums page
4. Check console for logs showing the API URL being used
5. Try creating a post

## Troubleshooting:
- If you still see errors, note them from the console
- The error message now displays in the UI with a Retry button
- Check that your backend (Render) is running: `https://mental-health-support-backend.onrender.com/api/posts`

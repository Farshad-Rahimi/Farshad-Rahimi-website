# JSONBin.io Setup Guide for CV Download Counter

## Step 1: Create a JSONBin.io Account

1. Go to https://jsonbin.io/
2. Click "Sign Up" and create a free account
3. Verify your email address

## Step 2: Create a New Bin

1. After logging in, click "Create New Bin"
2. Enter the following JSON content:
```json
{
  "count": 0
}
```
3. Click "Create" to save the bin

## Step 3: Get Your API Key and Bin ID

1. **API Key**: Go to your account settings and copy your "Master Key" (starts with `$2a$10$`)
2. **Bin ID**: From your bin URL, copy the ID (it's in the URL like `https://jsonbin.io/v3/b/YOUR_BIN_ID_HERE`)

## Step 4: Update Your CV Page

Replace the placeholder values in `cv.html`:

```javascript
const JSONBIN_API_KEY = '$2a$10$YOUR_ACTUAL_API_KEY_HERE';
const JSONBIN_BIN_ID = 'YOUR_ACTUAL_BIN_ID_HERE';
```

## How It Works

- The counter will be stored in JSONBin.io and shared across all browsers and systems
- When someone downloads your CV, the counter increments globally
- If JSONBin.io is unavailable, it falls back to localStorage
- The counter persists even when you clear your browser cache

## Alternative Solutions

If you prefer not to use JSONBin.io, here are other options:

### Option 1: Firebase (More Complex)
- Create a Firebase project
- Use Firestore database
- Requires more setup but very reliable

### Option 2: GitHub-based Counter
- Use GitHub API to update a JSON file in your repository
- Requires GitHub token setup

### Option 3: Simple Backend
- Create a simple PHP/Node.js backend
- Host it on a web server

## Testing

After setup:
1. Open your CV page in different browsers
2. Download the CV multiple times
3. Check that the counter increments globally
4. Clear browser cache and verify the counter persists

## Troubleshooting

- If the counter shows "Loading..." permanently, check your API key and bin ID
- If updates don't work, verify your JSONBin.io account is active
- Check browser console for any error messages 
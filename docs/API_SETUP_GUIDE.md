# MCP Server API Setup Guide

## 1. GitHub Personal Access Token

### Steps to get your GitHub token:

1. **Go to GitHub Settings**
   - Visit: https://github.com/settings/tokens
   - Or: GitHub → Profile Picture → Settings → Developer settings → Personal access tokens → Tokens (classic)

2. **Generate New Token**
   - Click "Generate new token" → "Generate new token (classic)"
   - Give it a descriptive name like "MCP Server Access"

3. **Set Expiration**
   - Choose "No expiration" or set a long expiration period
   - Note: You'll need to regenerate when it expires

4. **Select Required Scopes**
   Check these boxes:
   - ✅ `repo` (Full control of private repositories)
   - ✅ `user` (Read user profile data)
   - ✅ `gist` (Create and read gists)
   - ✅ `read:org` (Read organization membership)
   - ✅ `workflow` (Update GitHub Action workflows)

5. **Generate and Copy**
   - Click "Generate token"
   - **IMPORTANT**: Copy the token immediately - you won't see it again!
   - Format: `ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx`

---

## 2. Brave Search API Key

### Steps to get your Brave Search API key:

1. **Visit Brave Search API**
   - Go to: https://api.search.brave.com/app/keys

2. **Create Account / Sign In**
   - Create a new account or sign in with existing credentials
   - You can use Google, GitHub, or email signup

3. **Subscribe to a Plan**
   - **Free Tier**: 2,000 queries/month (good for testing)
   - **Pro Plans**: Higher limits available if needed
   - Choose the plan that fits your usage

4. **Generate API Key**
   - After subscribing, go to "API Keys" section
   - Click "Add API Key"
   - Give it a name like "MCP Server"
   - Copy the generated API key
   - Format: `BSA-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx`

---

## 3. Update Your .env File

Once you have both tokens, update your `.env` file:

```bash
# Replace these with your actual tokens
GITHUB_PERSONAL_ACCESS_TOKEN=ghp_your_actual_github_token_here
BRAVE_SEARCH_API_KEY=BSA-your_actual_brave_api_key_here
```

---

## 4. Security Notes

- **Never commit** your `.env` file to version control
- **Keep tokens secure** - treat them like passwords
- **Regenerate tokens** if you suspect they're compromised
- **Use minimal scopes** - only grant necessary permissions

---

## 5. Testing Your Setup

After updating the `.env` file, you can test the MCP servers:

```bash
# Test GitHub server
npx @modelcontextprotocol/server-github

# Test Brave Search server
npx @modelcontextprotocol/server-brave-search
```

The servers should start without authentication errors if tokens are correctly configured.
# Configuration Guide

This document explains how to find and configure tokens and API keys needed for the VoteUpp project and related development work.

## 🔑 Finding Your Tokens

### GitHub Personal Access Token
If you're looking for your GitHub token for repository access:

1. **GitHub.com Settings Location:**
   - Go to [GitHub.com](https://github.com)
   - Click your profile picture (top right)
   - Select **Settings**
   - Scroll down in the left sidebar to **Developer settings**
   - Click **Personal access tokens** → **Tokens (classic)**
   - Or go directly to: https://github.com/settings/tokens

2. **Creating a New Token:**
   - Click **Generate new token** → **Generate new token (classic)**
   - Give it a descriptive name (e.g., "VoteUpp Development")
   - Select appropriate scopes:
     - `repo` - for repository access
     - `workflow` - for GitHub Actions
     - `read:org` - for organization access (if needed)
   - Click **Generate token**
   - **Important:** Copy the token immediately - you won't see it again!

### API Keys for Mobile Development

#### Firebase (for push notifications)
1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Select your project
3. Click the gear icon → **Project settings**
4. Go to **Service accounts** tab
5. Click **Generate new private key**

#### Google APIs (for maps, authentication)
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Select your project
3. Navigate to **APIs & Services** → **Credentials**
4. Click **Create Credentials** → **API Key**

#### Apple Developer (for iOS development)
1. Go to [Apple Developer Portal](https://developer.apple.com/account/)
2. Navigate to **Certificates, Identifiers & Profiles**
3. Select **Keys** from the sidebar
4. Click the **+** button to create a new key

## 🔧 Environment Configuration

### Local Development Setup
Create a `.env` file in your project root (never commit this to git):

```bash
# GitHub
GITHUB_TOKEN=your_github_token_here

# Firebase
FIREBASE_PROJECT_ID=your_project_id
FIREBASE_PRIVATE_KEY=your_private_key

# API Keys
GOOGLE_MAPS_API_KEY=your_maps_key
FLUTTER_API_KEY=your_flutter_key

# Database
DATABASE_URL=your_database_connection_string
```

### Flutter Configuration
For Flutter projects, add keys to:
- `android/app/src/main/res/values/strings.xml`
- `ios/Runner/Info.plist`

## 🛡️ Security Best Practices

1. **Never commit tokens to git**
   - Add `.env` to your `.gitignore`
   - Use environment variables in production
   - Rotate tokens regularly

2. **Use appropriate scopes**
   - Only grant minimum necessary permissions
   - Create separate tokens for different purposes

3. **Store securely**
   - Use your password manager
   - Don't share tokens in plain text
   - Use secrets management in production

## 📱 Platform-Specific Token Locations

### Xcode (iOS Development)
- Open Xcode
- Preferences → Accounts → Manage Certificates
- Your Apple Developer certificates are listed here

### Android Studio
- File → Settings → Appearance & Behavior → System Settings → Android SDK
- SDK Tools tab shows installed tools and keys

### VSCode Extensions
- Extensions that require tokens usually prompt for them
- Check extension settings: Ctrl/Cmd + , → search for the extension

## 🆘 Troubleshooting

**Can't find your token?**
- Check if it expired (GitHub tokens can expire)
- Verify you're looking in the right account/organization
- Check your browser's saved passwords
- Look for environment variables on your system

**Token not working?**
- Verify the scopes/permissions
- Check if the token is for the correct repository/organization
- Ensure the token hasn't been revoked
- Try regenerating the token

## 📚 Additional Resources

- [GitHub Token Documentation](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
- [Firebase Setup Guide](https://firebase.google.com/docs/flutter/setup)
- [Flutter Development Setup](https://docs.flutter.dev/get-started/install)

---
*Last updated: $(date)*
*For questions, contact: Goobill1969@gmail.com*
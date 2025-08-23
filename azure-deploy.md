
# Azure App Service Deployment Guide

## Prerequisites
1. Install Azure App Service extension in VS Code
2. Install Azure CLI (optional)
3. Create an Azure account and subscription

## Deployment Steps

### Step 1: Create Azure App Service
1. Open VS Code
2. Install "Azure App Service" extension
3. Sign in to your Azure account
4. Create new Web App:
   - Right-click on subscription in Azure panel
   - Select "Create New Web App"
   - Choose Node.js 18 LTS runtime
   - Select Linux OS

### Step 2: Configure Environment Variables
In Azure Portal, go to Configuration > Application Settings and add:
- `NODE_ENV=production`
- `PORT=8080` (Azure default)
- Any other environment variables your app needs

### Step 3: Deploy from VS Code
1. Build the project: `npm run build`
2. Right-click on your Azure App Service
3. Select "Deploy to Web App"
4. Choose this folder as deployment source
5. Confirm deployment

### Step 4: Verify Deployment
- Check deployment logs in VS Code output panel
- Visit your Azure App URL
- Monitor application logs in Azure Portal

## File Structure for Azure
```
dist/
  public/           # Built React app
  server/           # Compiled TypeScript server
web.config          # IIS configuration
package.json        # Dependencies
.deployment         # Azure build config
```

## Troubleshooting
- Check Azure App Service logs in portal
- Verify Node.js version matches local development
- Ensure all environment variables are set
- Check web.config for proper routing

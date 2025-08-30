# Chaudhary Kirana Store - Admin Panel

यह Chaudhary Kirana Store का comprehensive admin panel है जहाँ admins products manage कर सकते हैं, orders track कर सकते हैं, और customer messages handle कर सकते हैं।

## 🚀 Quick Start

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- VS Code with Live Server extension (recommended)
- Firebase project with proper configuration
- Admin credentials for authentication

### Setup Instructions

1. **Install VS Code Live Server Extension**
   - Open VS Code
   - Go to Extensions (Ctrl+Shift+X)
   - Search for "Live Server" by Ritwick Dey
   - Install the extension

2. **Run the Admin Panel**
   - Right-click on `admin.html`
   - Select "Open with Live Server"
   - The admin panel will open in your browser at `http://127.0.0.1:5500`
   - Login with your admin credentials

3. **Alternative: Use Any Local Server**
   - Python: `python -m http.server 8000`
   - Node.js: `npx serve .`
   - PHP: `php -S localhost:8000`

## ⚠️ Important Notes

### Why Local Server is Required
- **Firebase Cloud Messaging (FCM)** requires HTTPS or localhost
- **Service Workers** cannot be registered on `file://` protocol
- **Push notifications** will not work without proper server setup

### Common Errors and Solutions

#### Error: "A bad HTTP response code (404) was received when fetching the script"
**Solution**: Use a local server instead of opening the file directly in the browser.

#### Error: "FCM token generation failed: Messaging: We are unable to register the default service worker"
**Solution**: Ensure you're running on `http://localhost` or `https://` protocol.

#### Error: "The current domain is not authorized for OAuth operations"
**Solution**: Add `127.0.0.1` and `localhost` to your Firebase project's authorized domains.

## 🔧 Firebase Configuration

### Required Firebase Services
- Authentication
- Realtime Database
- Cloud Messaging (FCM)

### Authorized Domains
Add these to your Firebase project:
1. Go to Firebase Console → Authentication → Settings → Authorized domains
2. Add: `localhost`, `127.0.0.1`
3. Add your production domain when deploying

## 📱 Features

- **Product Management**: Add, edit, delete products
- **Order Management**: View and update order statuses
- **Customer Messages**: Handle customer inquiries
- **Real-time Updates**: Live data synchronization
- **Push Notifications**: Get notified of new orders
- **Mobile Responsive**: Works on all device sizes
- **Dashboard Analytics**: View store statistics
- **Bulk Operations**: Add multiple products at once

## 🛠️ Development

### File Structure
```
├── admin.html              # Main admin panel interface
├── firebase-messaging-sw.js # Firebase service worker
├── README.md               # This file
├── setup.bat               # Windows quick-start script
└── setup.sh                # Unix/Linux/Mac quick-start script
```

### Firebase Configuration
The Firebase config is embedded in both `admin.html` and `firebase-messaging-sw.js`. Update the config object in both files when changing Firebase projects.

## 🚀 Deployment

### Production Requirements
- HTTPS domain
- Firebase project with production configuration
- Update Firebase config in both files
- Ensure domain is authorized in Firebase console

### Local Development
- Use Live Server or similar local server
- Test on `localhost` or `127.0.0.1`
- Firebase will work in development mode

## 📞 Support

If you encounter issues:
1. Check that you're using a local server (not file:// protocol)
2. Verify Firebase configuration is correct
3. Check browser console for error messages
4. Ensure all required files are in the same directory

## 🔒 Security

- Admin authentication is required
- Firebase security rules should be configured
- Never expose Firebase config keys in public repositories
- Use environment variables for production deployments

## 🌐 Related Files

- **Customer Store**: See `../user/` folder for customer-facing store
- **Shared Service Worker**: `firebase-messaging-sw.js` is shared between store and admin

## 👥 Admin Access

To access the admin panel:
1. Ensure you have admin credentials in Firebase Authentication
2. Login with your admin email and password
3. You'll have access to all admin features
4. Session will persist until you logout

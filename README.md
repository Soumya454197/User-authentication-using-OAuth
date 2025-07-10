# User Authentication System

A complete authentication system with Google OAuth integration, featuring both traditional email/password authentication and modern OAuth sign-in capabilities.

## 🚀 Features

- **Traditional Authentication**: Email/password signup and login
- **Google OAuth Integration**: One-click sign-in with Google
- **JWT Token Management**: Secure session handling
- **Responsive UI**: Modern, mobile-friendly design
- **User Dashboard**: Personalized user interface after authentication
- **GitHub OAuth Ready**: Prepared for GitHub authentication integration

## 📁 Project Structure

```
user-authentication/
├── login-backend/
│   ├── server.js          # Express.js backend server
│   ├── package.json       # Node.js dependencies
│   ├── .env              # Environment variables
│   └── node_modules/     # Installed packages
├── login.html            # Main authentication page
├── auth.js              # Frontend authentication logic
├── dashboard.html       # User dashboard after login
├── google-test.html     # Google OAuth testing page
├── requirements.txt     # Project dependencies list
└── README.md           # This file
```

## 🛠️ Installation & Setup

### Prerequisites
- Node.js (v14 or higher)
- A Google Cloud Console project with OAuth 2.0 credentials

### 1. Clone/Download the Project
```bash
git clone <your-repo-url>
cd user-authentication
```

### 2. Install Backend Dependencies
```bash
cd login-backend
npm install express cors body-parser bcryptjs jsonwebtoken google-auth-library dotenv
```

### 3. Configure Environment Variables
Create a `.env` file in the `login-backend` directory:
```env
CLIENT_ID=your_google_client_id_here
CLIENT_SECRET=your_google_client_secret_here
JWT_SECRET=your_super_secret_jwt_key_here
```

### 4. Google OAuth Setup
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select existing one
3. Enable Google+ API
4. Create OAuth 2.0 credentials
5. Add authorized origins:
   - `http://localhost:3000`
   - `file://` (for local file testing)
6. Copy Client ID and Client Secret to `.env` file

## 🚀 Running the Application

### 1. Start the Backend Server
```bash
cd login-backend
node server.js
```
Server will run on `http://localhost:3000`

### 2. Open the Frontend
Open `login.html` in your web browser:
- **File method**: `file:///path/to/login.html`
- **Local server**: Use a local HTTP server for better compatibility

## 📋 API Endpoints

### Authentication Endpoints

#### POST `/signup`
Register a new user with email/password
```json
{
  "email": "user@example.com",
  "password": "password123"
}
```

#### POST `/login`
Login with email/password
```json
{
  "email": "user@example.com",
  "password": "password123"
}
```

#### POST `/auth/google`
Authenticate with Google OAuth token
```json
{
  "token": "google_id_token_here"
}
```

## 🎨 Frontend Pages

### `login.html`
- Main authentication interface
- Email/password forms with toggle between login/signup
- Google OAuth sign-in button
- GitHub authentication button (ready for implementation)
- Responsive design with modern UI

### `dashboard.html`
- User dashboard after successful authentication
- Displays user information and profile picture
- Shows authentication method used
- Token expiry information
- Logout functionality

### `google-test.html`
- Testing page for Google OAuth functionality
- Debug tools for troubleshooting authentication issues
- Step-by-step OAuth flow testing

## 🔧 Configuration

### Google OAuth Client ID
Update the Client ID in both:
1. `.env` file (backend)
2. `auth.js` file (frontend)
3. `login.html` data attributes

### JWT Secret
Change the default JWT secret in `.env`:
```env
JWT_SECRET=your_unique_secret_key_here
```

## 🔒 Security Features

- **Password Hashing**: Uses bcryptjs for secure password storage
- **JWT Tokens**: Secure session management with expiration
- **Google OAuth**: Official Google Identity Services integration
- **CORS Protection**: Configured for cross-origin requests
- **Input Validation**: Frontend and backend validation

## 🧪 Testing

### Manual Testing
1. **Traditional Signup**: Create account with email/password
2. **Traditional Login**: Login with created credentials
3. **Google OAuth**: Test Google sign-in flow
4. **Dashboard Access**: Verify redirect after authentication
5. **Token Management**: Check localStorage for tokens

### Debug Tools
- Use `google-test.html` for OAuth troubleshooting
- Check browser console for detailed logs
- Verify backend responses in Network tab

## 🚧 Future Enhancements

- [ ] GitHub OAuth implementation
- [ ] Password reset functionality
- [ ] Email verification
- [ ] User profile management
- [ ] Database integration (MongoDB/PostgreSQL)
- [ ] Rate limiting and security headers
- [ ] Unit and integration tests

## 📝 Dependencies

### Backend (Node.js)
- `express` - Web framework
- `cors` - Cross-origin resource sharing
- `body-parser` - Request body parsing
- `bcryptjs` - Password hashing
- `jsonwebtoken` - JWT token handling
- `google-auth-library` - Google OAuth verification
- `dotenv` - Environment variable management

### Frontend
- Google Identity Services API
- Modern JavaScript (ES6+)
- CSS3 with responsive design

## 🐛 Troubleshooting

### Google OAuth Not Working
1. Check Client ID configuration
2. Verify authorized origins in Google Console
3. Ensure internet connectivity
4. Check browser console for errors
5. Use `google-test.html` for debugging

### Backend Connection Issues
1. Verify server is running on port 3000
2. Check CORS configuration
3. Ensure `.env` file is properly configured
4. Check network connectivity

### Token Issues
1. Verify JWT secret consistency
2. Check token expiration times
3. Clear localStorage and retry
4. Verify backend token validation

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📞 Support

For issues and questions:
1. Check the troubleshooting section
2. Review browser console logs
3. Test with `google-test.html`
4. Create an issue with detailed information

---

**Happy Coding! 🎉**

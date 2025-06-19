# SecureAuth - Next.js Authentication Platform

A modern, secure authentication platform built with Next.js 14, TypeScript, Supabase, and Tailwind CSS. This production-ready application provides a complete authentication system with beautiful UI components and comprehensive user management features.

![SecureAuth Preview](https://images.pexels.com/photos/5380664/pexels-photo-5380664.jpeg?auto=compress&cs=tinysrgb&w=1200&h=600&fit=crop)

## ✨ Features

### 🔐 Authentication System
- **Email/Password Authentication** - Secure user registration and login
- **OAuth Integration** - Google sign-in support
- **Password Reset** - Email-based password recovery
- **Protected Routes** - Middleware-based route protection
- **Session Management** - Automatic session handling and refresh

### 🎨 User Interface
- **Modern Design** - Clean, professional interface with gradient backgrounds
- **Responsive Layout** - Optimized for mobile, tablet, and desktop
- **Glass Morphism Effects** - Modern UI with backdrop blur and transparency
- **Smooth Animations** - Micro-interactions and transitions
- **Dark/Light Theme Ready** - Built with theme support

### 👤 User Management
- **User Dashboard** - Personalized dashboard with account statistics
- **Profile Management** - Update personal information and preferences
- **Avatar Upload** - Profile picture management
- **Account Settings** - Comprehensive settings panel
- **Security Controls** - Password updates and security preferences

### 🛡️ Security Features
- **Route Protection** - Middleware-based authentication checks
- **Form Validation** - Client and server-side validation
- **Error Handling** - Comprehensive error management
- **Toast Notifications** - User feedback for all actions
- **Type Safety** - Full TypeScript implementation

## 🚀 Tech Stack

- **Framework**: Next.js 14 (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **UI Components**: Shadcn/UI
- **Authentication**: Supabase Auth
- **Database**: Supabase (PostgreSQL)
- **Icons**: Lucide React
- **Notifications**: Sonner

## 📋 Prerequisites

Before running this project, make sure you have:

- Node.js 18+ installed
- A Supabase account and project
- Git for version control

## 🛠️ Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/secureauth.git
   cd secureauth
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   
   Create a `.env.local` file in the root directory:
   ```env
   NEXT_PUBLIC_SUPABASE_URL=your_supabase_project_url
   NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
   ```

4. **Configure Supabase**
   
   In your Supabase dashboard:
   - Enable Email authentication
   - Configure OAuth providers (Google)
   - Set up redirect URLs:
     - `http://localhost:3000/dashboard` (development)
     - `https://yourdomain.com/dashboard` (production)

5. **Run the development server**
   ```bash
   npm run dev
   ```

6. **Open your browser**
   
   Navigate to `http://localhost:3000`

## 📁 Project Structure

```
secureauth/
├── app/                          # Next.js App Router
│   ├── auth/                     # Authentication pages
│   │   ├── login/               # Login page
│   │   ├── register/            # Registration page
│   │   ├── forgot-password/     # Password reset
│   │   └── layout.tsx           # Auth layout
│   ├── dashboard/               # Protected dashboard
│   ├── settings/                # User settings
│   ├── globals.css              # Global styles
│   ├── layout.tsx               # Root layout
│   └── page.tsx                 # Landing page
├── components/                   # Reusable components
│   └── ui/                      # Shadcn UI components
├── hooks/                       # Custom React hooks
│   └── use-auth.ts              # Authentication hook
├── lib/                         # Utility libraries
│   ├── auth.ts                  # Authentication functions
│   ├── supabase.ts              # Supabase client
│   └── utils.ts                 # Utility functions
├── middleware.ts                # Route protection
└── README.md                    # Project documentation
```

## 🔧 Configuration

### Supabase Setup

1. **Create a new Supabase project**
2. **Enable authentication providers**:
   - Email/Password (enabled by default)
   - Google OAuth (optional)

3. **Configure authentication settings**:
   ```sql
   -- Enable RLS (Row Level Security)
   ALTER TABLE auth.users ENABLE ROW LEVEL SECURITY;
   
   -- Create profiles table (optional)
   CREATE TABLE profiles (
     id UUID REFERENCES auth.users ON DELETE CASCADE,
     updated_at TIMESTAMP WITH TIME ZONE,
     full_name TEXT,
     avatar_url TEXT,
     bio TEXT,
     phone TEXT,
     PRIMARY KEY (id)
   );
   ```

### Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `NEXT_PUBLIC_SUPABASE_URL` | Your Supabase project URL | Yes |
| `NEXT_PUBLIC_SUPABASE_ANON_KEY` | Your Supabase anonymous key | Yes |

## 🎯 Usage

### Authentication Flow

1. **Registration**
   - Users can register with email/password
   - Optional Google OAuth registration
   - Email verification (configurable)

2. **Login**
   - Email/password authentication
   - Google OAuth login
   - Remember me functionality

3. **Password Reset**
   - Email-based password recovery
   - Secure reset link generation
   - Password update confirmation

### Protected Routes

The application uses Next.js middleware to protect routes:

- `/dashboard` - Requires authentication
- `/settings` - Requires authentication
- `/auth/*` - Redirects to dashboard if authenticated

### User Management

Users can:
- Update profile information
- Change passwords
- Manage notification preferences
- Upload profile avatars
- Delete their accounts

## 🚀 Deployment

### Vercel (Recommended)

1. **Connect your repository to Vercel**
2. **Add environment variables**:
   - `NEXT_PUBLIC_SUPABASE_URL`
   - `NEXT_PUBLIC_SUPABASE_ANON_KEY`
3. **Deploy**

### Other Platforms

The application can be deployed to any platform that supports Next.js:
- Netlify
- Railway
- DigitalOcean App Platform
- AWS Amplify

## 🧪 Testing

```bash
# Run tests (when implemented)
npm run test

# Run linting
npm run lint

# Type checking
npm run type-check
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

If you encounter any issues or have questions:

1. Check the [Issues](https://github.com/yourusername/secureauth/issues) page
2. Create a new issue with detailed information
3. Join our [Discord community](https://discord.gg/your-invite)

## 🙏 Acknowledgments

- [Next.js](https://nextjs.org/) - The React framework
- [Supabase](https://supabase.com/) - Backend as a Service
- [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS framework
- [Shadcn/UI](https://ui.shadcn.com/) - Beautiful UI components
- [Lucide](https://lucide.dev/) - Beautiful icons

## 📊 Project Status

- ✅ Authentication system
- ✅ User dashboard
- ✅ Profile management
- ✅ Responsive design
- ✅ TypeScript integration
- 🔄 Testing suite (in progress)
- 🔄 Admin panel (planned)
- 🔄 API documentation (planned)

---

**Built with ❤️ using Next.js and Supabase**

For more information, visit our [documentation](https://docs.yourproject.com) or check out the [live demo](https://secureauth-demo.vercel.app).
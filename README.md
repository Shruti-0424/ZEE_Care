# ZEE CARE - Modern Healthcare Platform

![ZEE CARE Logo](./public/images/logo.png)

A full-stack Healthcare Management System built with Next.js, MongoDB, and Tailwind CSS, featuring a modern and intuitive UI for patients, doctors, and administrators.

## 🌟 Features

### For Patients
- **User Authentication** - Secure login and registration
- **Department Browsing** - Explore various medical departments
- **Doctor Profiles** - View doctor information and availability
- **Appointment Booking** - Schedule, reschedule, or cancel appointments
- **Waitlist Management** - Join waitlists for fully booked doctors
- **Appointment History** - Track past and upcoming appointments
- **Profile Management** - Update personal information
- **Interactive Chatbot** - Get instant answers to common questions

### For Doctors
- **Appointment Dashboard** - View and manage upcoming appointments
- **Patient Records** - Access patient medical history
- **Availability Management** - Set and update working hours
- **Notification System** - Receive alerts for new appointments

### For Administrators
- **User Management** - Add, edit, or remove users
- **Department Management** - Create and manage hospital departments
- **Analytics Dashboard** - View system statistics and reports
- **Appointment Oversight** - Monitor and manage all appointments

## 🚀 Technologies Used

### Frontend
- **Next.js 14** - React framework with App Router
- **React 18** - UI library
- **TypeScript** - Type-safe JavaScript
- **Tailwind CSS** - Utility-first CSS framework
- **Radix UI** - Accessible component primitives
- **Framer Motion** - Animation library
- **Next-Auth** - Authentication solution
- **React Query** - Data fetching and state management

### Backend
- **Next.js API Routes** - Serverless API endpoints
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB object modeling
- **NextAuth.js** - Authentication framework
- **Bcrypt** - Password hashing
- **Nodemailer** - Email notifications

### Development Tools
- **ESLint** - Code linting
- **TypeScript** - Static type checking
- **Prettier** - Code formatting
- **Vercel** - Deployment platform

## 📂 Project Structure

```
hms/
├── app/                  # Next.js App Router
│   ├── (auth)/           # Authentication routes (login, register)
│   ├── (main)/           # Main application routes (dashboard, profile)
│   ├── (admin)/          # Admin-specific routes
│   ├── api/              # API routes
│   └── ...
├── components/           # React components
│   ├── ui/               # UI components (buttons, cards, etc.)
│   └── ...
├── lib/                  # Utility functions and models
│   ├── models/           # Mongoose models
│   ├── auth.ts           # Authentication configuration
│   ├── db.ts             # Database connection
│   └── ...
├── public/               # Static assets
├── scripts/              # Database seeding scripts
├── docs/                 # Documentation
└── ...
```

## 🛠️ Installation and Setup

### Prerequisites

- Node.js 18.x or later
- MongoDB database (local or Atlas)
- npm or yarn

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/zee-care.git
   cd zee-care
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Set up environment variables**
   - Create a `.env.local` file in the root directory with the following variables:
   ```
   # MongoDB Connection
   MONGODB_URI=mongodb+srv://your-mongodb-uri

   # NextAuth Configuration
   NEXTAUTH_SECRET=your-nextauth-secret
   NEXTAUTH_URL=http://localhost:3000

   # Email Configuration
   EMAIL_SERVER_HOST=smtp.example.com
   EMAIL_SERVER_PORT=587
   EMAIL_SERVER_USER=your-email@example.com
   EMAIL_SERVER_PASSWORD=your-email-password
   EMAIL_FROM=noreply@zeecare.com
   ```

4. **Seed the database with sample data**
   ```bash
   npm run seed
   # or
   yarn seed
   ```

5. **Create an admin user**
   ```bash
   node scripts/create-admin-user.js
   ```

6. **Run the development server**
   ```bash
   npm run dev
   # or
   yarn dev
   ```

7. **Open [http://localhost:3000](http://localhost:3000)** in your browser to see the application.

## 👥 User Roles and Access

### Patient
- Default role for new registrations
- Can book appointments, view medical history, and manage profile
- Login credentials: Create a new account or use:
  - Email: `patient@example.com`
  - Password: `patient123456`

### Doctor
- Can view appointments, manage availability, and access patient records
- Login credentials:
  - Email: `doctor1@example.com`
  - Password: `password123`

### Administrator
- Full system access including user management and analytics
- Login credentials:
  - Email: `admin@example.com`
  - Password: `admin123456`

## 🧪 Testing

### Running Tests
```bash
npm run test
# or
yarn test
```

### Test Accounts
The seed script creates multiple test accounts for each role that can be used for testing.

## 📱 Key Features Walkthrough

### Appointment Booking
1. Log in as a patient
2. Navigate to "Departments"
3. Select a department
4. Choose a doctor
5. Select an available time slot
6. Confirm your appointment

### Doctor Availability Management
1. Log in as a doctor
2. Navigate to "Availability"
3. Select days and time slots
4. Save your availability

### Admin User Management
1. Log in as an administrator
2. Navigate to "Users"
3. Add, edit, or remove users as needed

## 🤖 Chatbot

The ZEE CARE platform includes an interactive chatbot that provides instant answers to common questions. The chatbot is context-aware and adapts its suggestions based on the current page.

For detailed documentation on the chatbot:
- [Chatbot Overview](./docs/CHATBOT.md)
- [Developer Guide](./docs/CHATBOT-DEVELOPER.md)
- [User Guide](./docs/CHATBOT-USER-GUIDE.md)

## 📧 Email Notifications

The system sends email notifications for:
- Account creation
- Appointment booking
- Appointment reminders
- Appointment cancellations
- Password reset requests

To test email functionality, ensure your SMTP settings are correctly configured in the `.env.local` file.

## 🔄 API Endpoints

The application provides RESTful API endpoints for all major functions:

- **Authentication**
  - `/api/auth/[...nextauth]` - NextAuth authentication
  - `/api/auth/register` - User registration

- **Appointments**
  - `/api/appointments` - CRUD operations for appointments
  - `/api/appointments/availability` - Check doctor availability

- **Users**
  - `/api/users` - User management
  - `/api/users/profile` - Profile management

- **Departments**
  - `/api/departments` - Department information

- **Doctors**
  - `/api/doctors` - Doctor information and availability

## 🚀 Deployment

The easiest way to deploy this application is with [Vercel](https://vercel.com):

1. Push your code to a Git repository (GitHub, GitLab, or Bitbucket)
2. Import your project to Vercel
3. Add your environment variables in the Vercel dashboard
4. Deploy!

## 🧩 Extending the Application

### Adding New Features
1. Create new components in the `components` directory
2. Add new API routes in the `app/api` directory
3. Update models in the `lib/models` directory as needed

### Styling Guidelines
- Use Tailwind CSS for styling
- Follow the existing component patterns
- Use the UI components in `components/ui` for consistency

## 🔍 Troubleshooting

### Common Issues

**MongoDB Connection Errors**
- Verify your MongoDB URI in the `.env.local` file
- Ensure your IP address is whitelisted in MongoDB Atlas
- Test the connection using the provided script:
  ```bash
  node scripts/test-mongodb.js
  ```

**Email Configuration Issues**
- Check your SMTP settings in the `.env.local` file
- Test the email configuration using the provided script:
  ```bash
  node scripts/test-email.js
  ```

**Login Problems**
- Ensure you've created the admin user with the script
- Check that the database has been properly seeded
- Verify that NextAuth is properly configured

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgements

- [Next.js](https://nextjs.org/)
- [MongoDB](https://www.mongodb.com/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Radix UI](https://www.radix-ui.com/)
- [Vercel](https://vercel.com/)

---

## 📞 Contact

For questions or support, please contact:
- Email: support@zeecare.com
- Website: [www.zeecare.com](https://www.zeecare.com)

---

Made with ❤️ by the ZEE CARE Team

# Project Structure

```
minifaucet/
├── backend/
│   ├── models/
│   │   ├── User.js              # User model with Telegram integration
│   │   ├── Admin.js             # Admin model with authentication
│   │   ├── Task.js              # Task model
│   │   ├── TaskSubmission.js    # Task submission model
│   │   ├── Withdrawal.js        # Withdrawal request model
│   │   ├── Earning.js           # Earning history model
│   │   └── Settings.js          # System settings model
│   ├── routes/
│   │   ├── auth.js              # Authentication routes (Telegram login)
│   │   ├── user.js              # User dashboard and profile routes
│   │   ├── earnings.js          # Faucet and ad earning routes
│   │   ├── tasks.js             # Task routes
│   │   ├── withdrawals.js       # Withdrawal routes
│   │   ├── referrals.js        # Referral routes
│   │   ├── admin.js             # Admin dashboard routes
│   │   └── settings.js          # Public settings routes
│   ├── middleware/
│   │   ├── auth.js              # JWT authentication middleware
│   │   └── referralReward.js   # Referral commission logic
│   ├── scripts/
│   │   └── initAdmin.js         # Admin user initialization script
│   └── server.js                # Express server entry point
├── frontend/
│   ├── public/
│   │   └── index.html           # HTML template with Telegram WebApp script
│   ├── src/
│   │   ├── components/
│   │   │   ├── user/
│   │   │   │   ├── Dashboard.js      # Main user dashboard
│   │   │   │   ├── Earnings.js       # Earnings history
│   │   │   │   ├── Tasks.js          # Task list and submission
│   │   │   │   ├── Referrals.js      # Referral program
│   │   │   │   └── Withdrawals.js    # Withdrawal requests
│   │   │   ├── admin/
│   │   │   │   ├── AdminLogin.js     # Admin login page
│   │   │   │   └── AdminDashboard.js  # Admin dashboard
│   │   │   └── common/
│   │   │       ├── Navbar.js         # Top navigation
│   │   │       └── BottomNav.js      # Bottom navigation
│   │   ├── context/
│   │   │   └── AuthContext.js        # Authentication context
│   │   ├── App.js                    # Main app component
│   │   ├── App.css                   # App styles
│   │   ├── index.js                  # React entry point
│   │   └── index.css                  # Global styles
│   └── package.json                   # Frontend dependencies
├── .env.example                      # Environment variables template
├── .gitignore                        # Git ignore file
├── package.json                      # Root package.json with scripts
├── README.md                         # Main documentation
├── SETUP.md                          # Quick setup guide
└── PROJECT_STRUCTURE.md             # This file
```

## Key Features by File

### Backend Models
- **User.js**: Stores user data, balance, earnings, referral info
- **Admin.js**: Admin accounts with role-based access
- **Task.js**: Available tasks for users to complete
- **TaskSubmission.js**: User task submissions with approval workflow
- **Withdrawal.js**: Withdrawal requests with approval workflow
- **Earning.js**: Complete earnings history
- **Settings.js**: System-wide configuration

### Backend Routes
- **auth.js**: Telegram authentication, token verification
- **user.js**: User dashboard, profile, earnings/withdrawal history
- **earnings.js**: Faucet claims, ad completion, cooldown management
- **tasks.js**: Task listing, submission
- **withdrawals.js**: Withdrawal requests and status
- **referrals.js**: Referral statistics and registration
- **admin.js**: Complete admin panel API
- **settings.js**: Public settings endpoint

### Frontend Components
- **Dashboard**: Main user interface with stats and faucet claim
- **Earnings**: Earnings history with pagination
- **Tasks**: Available tasks with submission functionality
- **Referrals**: Referral program with link sharing
- **Withdrawals**: Withdrawal request form and history
- **AdminDashboard**: Complete admin panel with tabs

## API Endpoints Summary

### Public
- `GET /api/health` - Health check
- `GET /api/settings/public` - Public settings

### User (Requires Auth)
- `POST /api/auth/telegram` - Telegram login
- `GET /api/auth/verify` - Verify token
- `GET /api/user/dashboard` - Dashboard data
- `GET /api/user/profile` - User profile
- `GET /api/user/earnings` - Earnings history
- `GET /api/user/withdrawals` - Withdrawal history
- `POST /api/earnings/faucet/claim` - Claim faucet
- `GET /api/earnings/faucet/status` - Faucet status
- `GET /api/tasks/available` - Available tasks
- `POST /api/tasks/submit` - Submit task
- `GET /api/referrals/stats` - Referral stats
- `POST /api/withdrawals/request` - Request withdrawal

### Admin (Requires Admin Auth)
- `POST /api/admin/login` - Admin login
- `GET /api/admin/dashboard` - Dashboard stats
- `GET /api/admin/users` - User list
- `PATCH /api/admin/users/:id/status` - Update user status
- `PATCH /api/admin/users/:id/balance` - Adjust balance
- `GET /api/admin/tasks` - Task list
- `POST /api/admin/tasks` - Create task
- `PATCH /api/admin/tasks/:id` - Update task
- `GET /api/admin/task-submissions` - Task submissions
- `PATCH /api/admin/task-submissions/:id` - Review submission
- `GET /api/admin/withdrawals` - Withdrawal list
- `PATCH /api/admin/withdrawals/:id` - Process withdrawal
- `GET /api/admin/settings` - Get settings
- `POST /api/admin/settings` - Update settings

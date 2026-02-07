# 🚀 MiniFaucet - Telegram Earning Mini-App

## Complete Product Documentation for Buyers & Clients

---

<div align="center">

![Version](https://img.shields.io/badge/version-2.0.0-blue.svg)
![Stack](https://img.shields.io/badge/stack-MERN-green.svg)
![Platform](https://img.shields.io/badge/platform-Telegram%20Mini%20App-blue.svg)

**A Complete Telegram Mini-App Solution for Earning Rewards**

_Built with React.js, Node.js, Express.js, and MongoDB_

</div>

---

## 📋 Table of Contents

1. [Product Overview](#product-overview)
2. [Telegram Mini-App Features](#telegram-mini-app-features)
3. [Admin Dashboard Features](#admin-dashboard-features)
4. [Security Architecture](#security-architecture)
5. [Earning Methods](#earning-methods)
6. [Payment & Withdrawal Methods](#payment--withdrawal-methods)
7. [Technical Specifications](#technical-specifications)
8. [Scalability & Performance](#scalability--performance)
9. [Licensing System](#licensing-system)

---

## 🎯 Product Overview

MiniFaucet is a comprehensive, production-ready Telegram Mini-App designed for cryptocurrency faucet and earning platforms. It provides a complete solution for running a rewards-based platform where users can earn through multiple methods including faucet claims, ad watching, task completion, and referrals.

### Key Highlights

| Feature           | Description                                         |
| ----------------- | --------------------------------------------------- |
| **Platform**      | Telegram Mini-App (Web App SDK)                     |
| **Architecture**  | MERN Stack (MongoDB, Express.js, React.js, Node.js) |
| **User Capacity** | Optimized for 50,000+ concurrent users              |
| **Security**      | Multi-layer anti-bot protection                     |
| **Payment**       | FaucetPay integration + Custom withdrawal methods   |
| **Admin Control** | Complete administrative dashboard                   |

---

## 📱 Telegram Mini-App Features

### 1. Authentication & User Management

| Feature                       | Description                                                         |
| ----------------------------- | ------------------------------------------------------------------- |
| **Auto-Login via Telegram**   | Seamless authentication using Telegram Web App SDK (`@twa-dev/sdk`) |
| **JWT Token Authentication**  | 30-day token validity for users                                     |
| **User Profile**              | Complete profile with balance, earnings history, and statistics     |
| **Account Status Management** | Active, Suspended, Banned states                                    |
| **Referral Code System**      | Unique 6-character alphanumeric codes auto-generated                |

### 2. User Dashboard

- **Real-time Balance Display** - Live balance updates
- **Total Earnings Counter** - Lifetime earnings tracking
- **Total Withdrawals Counter** - Complete withdrawal history
- **Referral Statistics** - Referral count and earnings
- **Last Activity Timestamps** - Last login, last claim times
- **Mobile-First Responsive Design** - Optimized for Telegram mobile clients

### 3. Platform Access Control

| Platform                      | Configurable Access  |
| ----------------------------- | -------------------- |
| Telegram Web                  | Enable/Disable       |
| Telegram Desktop              | Enable/Disable       |
| Telegram Mobile (iOS/Android) | Enable/Disable       |
| Adblocker Detection           | Enforceable blocking |

### 4. Notification System

- **In-App Notifications** - Real-time notification center
- **Telegram Bot Notifications** - Direct messages for:
  - Balance additions/deductions
  - Withdrawal approvals/rejections
  - Task approvals/rejections
  - Account status changes
  - Broadcast announcements
- **Priority Levels** - Low, Normal, High, Urgent
- **Notification History** - Complete log of all notifications

---

## 💰 Earning Methods

### 1. Faucet System

| Setting             | Description                   | Configurable   |
| ------------------- | ----------------------------- | -------------- |
| Faucet Reward       | Amount per claim              | ✅ Admin Panel |
| Cooldown Timer      | Time between claims (seconds) | ✅ Admin Panel |
| Enable/Disable      | Toggle faucet feature         | ✅ Admin Panel |
| Anti-Bot Protection | Action Token System           | ✅ Built-in    |

**Security Features:**

- Server-enforced minimum wait time (15+ seconds)
- Single-use action tokens with HMAC signatures
- Atomic token consumption preventing race conditions
- Previous token invalidation on new requests

### 2. Advertising System

**Supported Ad Providers:**

| Provider    | Integration Type | Configurable Settings                                           |
| ----------- | ---------------- | --------------------------------------------------------------- |
| **Adsgram** | Block ID         | Enable/Disable, Block ID, Reward Amount, Faucet Integration     |
| **Monetag** | Zone ID          | Enable/Disable, Zone ID, Reward Amount, Faucet Integration      |
| **AdExtra** | Publisher ID     | Enable/Disable, Publisher ID, Reward Amount, Faucet Integration |
| **Adexora** | App ID           | Enable/Disable, App ID, Reward Amount, Faucet Integration       |

**Ad System Features:**

- **Per-Provider Rewards** - Individual reward amounts per provider
- **Daily Ad Limit** - Configurable maximum ads per day (default: 50)
- **Ad Cooldown** - Configurable cooldown between ads (default: 30 seconds)
- **Faucet Claim Integration** - Up to 3 ad providers for faucet claim flow
- **Provider Priority** - Configurable provider order for faucet claims
- **Ads Peering Groups** - Multiple peer groups for combined ad sessions

**Performance Optimization:**

- In-memory caching (30-second TTL)
- Request deduplication (prevents thundering herd)
- Lean MongoDB queries for faster retrieval

### 3. Task System

| Task Type     | Description                      |
| ------------- | -------------------------------- |
| Join Channel  | Join Telegram channel/group      |
| Visit Website | Visit external URL with tracking |
| Watch Video   | Watch video content              |
| Social        | Social media interactions        |
| Survey        | Complete surveys                 |
| Download      | Download apps/files              |
| Sign Up       | Register on external platforms   |
| Other         | Custom task types                |

**Task Features:**

- **Minimum Visit Duration** - Server-enforced visit time tracking
- **Maximum Completions** - Limit total completions per task (0 = unlimited)
- **Proof Submission** - Optional screenshot/proof requirement
- **Auto-Approval** - Tasks without proof requirement auto-approve
- **Puzzle Verification** - Math puzzle anti-bot verification
- **Completion Tracking** - Real-time slot availability

### 4. Referral System

| Setting         | Description                              | Configurable   |
| --------------- | ---------------------------------------- | -------------- |
| Commission Type | Percentage or Fixed                      | ✅ Admin Panel |
| Commission Rate | Percentage of referral earnings          | ✅ Admin Panel |
| Welcome Bonus   | Bonus for new referred users             | ✅ Admin Panel |
| Referral Link   | Deep link to Mini-App with referral code | Auto-generated |

**Referral Features:**

- Automatic referral code generation (6-character unique codes)
- Commission on all referral earnings (faucet, ads, tasks)
- Referral earnings tracking per user
- Referral leaderboard analytics
- Deep link generation: `https://t.me/{BOT_USERNAME}/{MINI_APP_NAME}?startapp={REFERRAL_CODE}`

---

## 💸 Payment & Withdrawal Methods

### 1. FaucetPay Integration (Instant Payments)

**Supported Cryptocurrencies (24 coins):**

| Category        | Currencies                                 |
| --------------- | ------------------------------------------ |
| **Major Coins** | BTC, ETH, LTC, BCH, DOGE, DASH             |
| **Stablecoins** | USDT, USDC                                 |
| **Altcoins**    | TRX, BNB, SOL, XRP, ADA, TON, XLM, XMR     |
| **Others**      | ZEC, DGB, POL, FEY, TARA, TRUMP, PEPE, FLT |

**FaucetPay Features:**

- **Instant Withdrawals** - Real-time payouts via FaucetPay API
- **API Connection Testing** - Test API key before enabling
- **Balance Checking** - View FaucetPay account balance from admin
- **Daily Limit** - Configurable daily withdrawal limit per user
- **Fee Configuration** - Fixed or percentage-based fees
- **Processing Time** - Configurable processing time display
- **Payment History** - Complete FaucetPay transaction logs

### 2. Custom Withdrawal Methods

**Fully Customizable Withdrawal System:**

| Field           | Description                                       |
| --------------- | ------------------------------------------------- |
| Name            | Method display name                               |
| Slug            | URL-safe identifier                               |
| Description     | Method description                                |
| Logo            | Method icon/logo URL                              |
| Currency        | Payment currency                                  |
| Min/Max Amount  | Withdrawal limits                                 |
| Processing Time | Expected processing duration                      |
| Fee             | Fixed or percentage fee                           |
| Custom Fields   | Dynamic form fields (wallet address, email, etc.) |
| Enable/Disable  | Toggle availability                               |
| Sort Order      | Display ordering                                  |

**Custom Field Types:**

- Text input
- Email input
- Number input
- Textarea

### 3. Currency System

**Dual Currency Modes:**

| Mode            | Description                                            |
| --------------- | ------------------------------------------------------ |
| **Fiat Mode**   | Balance stored in USD/real currency                    |
| **Points Mode** | Balance stored in points with exchange rate conversion |

**Currency Settings:**

- Currency Name (e.g., "Coins", "Points", "Tokens")
- Currency Symbol (e.g., "₮", "$", "🪙")
- Points Exchange Rate (e.g., 1000 points = $1 USD)
- Automatic conversion for withdrawals

---

## 🛠️ Admin Dashboard Features

### 1. Dashboard & Analytics

**Real-Time Statistics:**

- Total Users / Active Users / Banned Users / Suspended Users
- Daily Active Users (last 24 hours)
- Weekly New Users (last 7 days)
- Total Earnings Distributed
- Total Withdrawals Processed
- Pending Withdrawals (count & amount)
- Pending Task Submissions
- Users with Referrals
- Total Referral Earnings

**Today's Statistics:**

- Earnings breakdown by type (faucet, ads, tasks, referrals)
- Ad views by provider
- FaucetPay payments

**Analytics Charts:**

- Daily registrations (custom date range)
- Daily earnings by type
- Daily withdrawals by status
- Daily ad views by provider
- Top 10 referrers
- Top 10 earners

### 2. User Management

| Feature                | Description                                        |
| ---------------------- | -------------------------------------------------- |
| **User Search**        | Search by username, Telegram ID, name              |
| **Status Filtering**   | Filter by active, suspended, banned                |
| **Sorting**            | Sort by any field (creation date, earnings, etc.)  |
| **Pagination**         | Configurable page sizes                            |
| **Balance Adjustment** | Add, subtract, or set balance with reason          |
| **Status Change**      | Activate, suspend, or ban users with notifications |
| **Cooldown Reset**     | Reset faucet cooldown for specific users           |

**Comprehensive User Details View:**

| Category        | Information                                                   |
| --------------- | ------------------------------------------------------------- |
| **Profile**     | Telegram ID, username, names, balance, total earnings, status |
| **Security**    | IP history, device fingerprints, user agents, trust score     |
| **Earnings**    | Complete history, daily breakdown, hourly patterns            |
| **Withdrawals** | History, summary by status, total withdrawn                   |
| **Tasks**       | Submission history, approval/rejection stats                  |
| **Ads**         | Session stats by provider                                     |
| **Referrals**   | Referral list, referral earnings                              |

**Trust & Risk Indicators:**

- Trust Score (0-100)
- Trust Level (Low/Medium/High)
- Suspicious Activity Flags:
  - Multiple IPs usage
  - Shared IP (multiple accounts)
  - High earnings patterns
  - Inactivity detection
  - High rejection rate
  - No withdrawals despite balance

### 3. Task Management

| Feature                 | Description                            |
| ----------------------- | -------------------------------------- |
| **Create Tasks**        | Full task creation with all parameters |
| **Edit Tasks**          | Update any task property               |
| **Delete Tasks**        | Remove tasks and related submissions   |
| **Task Analytics**      | Per-task completion stats and trends   |
| **Submission Review**   | View pending submissions with proof    |
| **Approve/Reject**      | Individual or bulk actions             |
| **Completion Tracking** | Monitor remaining slots                |

**Task Analytics Per Task:**

- Total completions
- Remaining slots
- Today's completions
- Weekly completions
- Daily completion chart
- Recent submissions
- Top completers

### 4. Withdrawal Management

| Feature                | Description                             |
| ---------------------- | --------------------------------------- |
| **View All Requests**  | Paginated list with filters             |
| **Status Filtering**   | Pending, Approved, Rejected, All        |
| **Approve with TX ID** | Add transaction ID on approval          |
| **Reject with Reason** | Provide rejection reason (auto-refunds) |
| **Export to CSV**      | Export withdrawal data                  |
| **Summary Stats**      | Pending count and amount                |

### 5. Notification & Broadcast System

| Feature                      | Description                             |
| ---------------------------- | --------------------------------------- |
| **Broadcast to All**         | Send notifications to all active users  |
| **Individual Notifications** | Send to specific users                  |
| **Telegram Integration**     | Automatic Telegram message delivery     |
| **Priority Levels**          | Low, Normal, High, Urgent               |
| **Expiration Dates**         | Set notification expiry                 |
| **Broadcast Analytics**      | Delivery stats, blocked users, errors   |
| **Broadcast History**        | Complete log with success/failure rates |

**Broadcast Features:**

- Rate limiting (25 messages/second, Telegram policy compliant)
- Retry logic with exponential backoff
- Blocked user detection and tracking
- Progress tracking for large broadcasts
- Estimated delivery time calculation
- Reset blocked status option

### 6. Settings Management

**Complete Configuration Categories:**

| Category          | Settings                                             |
| ----------------- | ---------------------------------------------------- |
| **App Settings**  | App name, currency name, currency symbol             |
| **Currency Mode** | Fiat/Points mode, exchange rate                      |
| **Faucet**        | Enable/disable, reward, cooldown                     |
| **Referrals**     | Enable/disable, commission rate, type, welcome bonus |
| **Withdrawals**   | Enable/disable, min/max amounts, fees                |
| **Tasks**         | Enable/disable                                       |
| **Ads - Global**  | Enable/disable, daily limit, cooldown                |
| **Ads - Adsgram** | Enable, Block ID, reward, faucet integration         |
| **Ads - Monetag** | Enable, Zone ID, reward, faucet integration          |
| **Ads - AdExtra** | Enable, Publisher ID, reward, faucet integration     |
| **Ads - Adexora** | Enable, App ID, reward, faucet integration           |
| **Ads - Peering** | Peer groups configuration                            |
| **FaucetPay**     | Enable, API key, currency, limits, fees              |
| **Telegram Bot**  | Bot username, token                                  |
| **Support**       | Support Telegram ID                                  |
| **Legal**         | Privacy policy, Terms & Conditions                   |
| **Social Media**  | Telegram, Twitter, YouTube, Discord, Instagram       |
| **Security**      | Turnstile enable/disable, site key, secret key       |
| **Maintenance**   | Maintenance mode, message                            |

### 7. Admin Account Management

| Feature             | Description                                      |
| ------------------- | ------------------------------------------------ |
| **Create Admins**   | Add new admin accounts                           |
| **Role Assignment** | Admin or Moderator roles                         |
| **Delete Admins**   | Remove admin accounts                            |
| **Two-Factor Auth** | TOTP-based 2FA (Google Authenticator compatible) |
| **Backup Codes**    | One-time recovery codes                          |
| **Password Change** | Secure password updates                          |

### 8. Data Export

| Export Type        | Format                                    |
| ------------------ | ----------------------------------------- |
| Withdrawals        | JSON (with date range and status filters) |
| Users              | JSON (complete user list)                 |
| FaucetPay Payments | JSON (full transaction history)           |

---

## 🔒 Security Architecture

### 1. Action Token System (Anti-Bot Protection)

**How It Works:**

```
1. User requests action → Server issues signed action token
2. User performs action (watches ads, waits)
3. User submits token → Server atomically validates & consumes
4. If all checks pass → Reward granted
```

**Security Properties:**

| Attack Vector        | Mitigation                                         |
| -------------------- | -------------------------------------------------- |
| Direct API calls     | Requires valid action token from `/start` endpoint |
| Replay attacks       | Single-use tokens (atomic consumption)             |
| Token harvesting     | Short TTL + action binding                         |
| Instant claims       | Server-enforced minimum time                       |
| Race conditions      | Atomic `findOneAndUpdate` operations               |
| Token forgery        | HMAC-SHA256 signature verification                 |
| Session accumulation | Previous tokens invalidated on new issuance        |

**Token Properties:**

- 64-character cryptographically random token ID
- User ID binding
- Action type binding
- Context data (reward amount, providers)
- HMAC-SHA256 signature
- Minimum time requirement (e.g., 15 seconds)
- Expiration time (e.g., 5 minutes)
- IP tracking for forensics

### 2. Cloudflare Turnstile Integration

**Protected Endpoints:**

- Faucet claims
- Ad reward claims
- Task submissions
- Withdrawal requests
- FaucetPay withdrawals

**Features:**

- Server-side token validation
- Configurable enable/disable
- Site key and secret key management
- Automatic challenge on suspicious requests

### 3. Authentication Security

| Mechanism     | Implementation                           |
| ------------- | ---------------------------------------- |
| User JWT      | 30-day validity, bcrypt password hashing |
| Admin JWT     | 24-hour validity                         |
| 2FA           | TOTP (RFC 6238) with backup codes        |
| Rate Limiting | Express rate limiter (configurable)      |
| CORS          | Configurable origin whitelist            |

### 4. Database Security

- Atomic operations for balance updates
- Transaction-safe withdrawal processing
- Unique indexes on critical fields
- TTL indexes for automatic token cleanup

### 5. License Enforcement

**Distributed License System:**

- Startup validation (fail-closed)
- Fresh validation on admin login
- Cached validation for API routes
- Payout multiplier enforcement
- Feature flag control

---

## ⚙️ Technical Specifications

### Technology Stack

| Component            | Technology                  |
| -------------------- | --------------------------- |
| **Frontend**         | React.js 18, React Router 6 |
| **Backend**          | Node.js, Express.js         |
| **Database**         | MongoDB with Mongoose ODM   |
| **Authentication**   | JWT (jsonwebtoken)          |
| **Password Hashing** | bcryptjs                    |
| **Telegram SDK**     | @twa-dev/sdk                |
| **HTTP Client**      | Axios                       |
| **Rate Limiting**    | express-rate-limit          |

### Database Models

| Model            | Purpose                         |
| ---------------- | ------------------------------- |
| User             | User accounts and profiles      |
| Admin            | Admin accounts with 2FA         |
| Earning          | All earning transactions        |
| Withdrawal       | Withdrawal requests             |
| WithdrawalMethod | Custom withdrawal methods       |
| Task             | Task definitions                |
| TaskSubmission   | User task submissions           |
| ActionToken      | Anti-bot security tokens        |
| AdSession        | Ad watch sessions               |
| PeeredAdSession  | Peered ad group sessions        |
| Settings         | Application settings            |
| Notification     | User notifications              |
| BroadcastLog     | Broadcast history and analytics |
| FaucetPayPayment | FaucetPay transaction records   |

### API Endpoints

| Route Group          | Description             |
| -------------------- | ----------------------- |
| `/api/auth`          | User authentication     |
| `/api/user`          | User profile management |
| `/api/earnings`      | Faucet claims           |
| `/api/tasks`         | Task operations         |
| `/api/ads`           | Ad watching             |
| `/api/withdrawals`   | Withdrawal requests     |
| `/api/referrals`     | Referral system         |
| `/api/faucetpay`     | FaucetPay integration   |
| `/api/settings`      | Public settings         |
| `/api/notifications` | User notifications      |
| `/api/admin`         | Admin dashboard API     |
| `/api/license`       | License validation      |
| `/api/health`        | Health check            |

---

## 🚀 Scalability & Performance

### Optimization Features

| Feature                   | Implementation                                 |
| ------------------------- | ---------------------------------------------- |
| **In-Memory Caching**     | 30-second TTL for settings, ads, faucet config |
| **Request Deduplication** | Prevents thundering herd on cache refresh      |
| **Lean Queries**          | Mongoose `.lean()` for ~3x faster reads        |
| **Bulk Operations**       | MongoDB `bulkWrite` for batch updates          |
| **Index Optimization**    | Strategic indexes on query fields              |
| **Connection Pooling**    | MongoDB connection management                  |

### Capacity

- **Concurrent Users**: Optimized for 50,000+ users
- **Broadcast Capacity**: Rate-limited to 25 messages/second (Telegram compliant)
- **Database Operations**: Atomic operations for consistency

---

## 📜 Licensing System

### Features

- **Startup Validation** - Application won't start without valid license
- **Admin Login Validation** - Fresh validation required for admin access
- **Feature Flags** - License controls available features
- **Payout Multiplier** - License-controlled reward multipliers
- **Offline Grace Period** - Cached validation for temporary offline
- **License Server Integration** - External validation server support

### License Enforcement Points

| Location            | Enforcement                  |
| ------------------- | ---------------------------- |
| Application Startup | Full validation, fail-closed |
| Admin Login         | Fresh revalidation           |
| Admin API Routes    | Cached validation check      |
| Earnings Processing | Payout multiplier applied    |
| Withdrawals         | Feature flag check           |

---

## 📦 Deployment Ready

### Environment Variables Required

```env
# Server
PORT=5000
NODE_ENV=production
MONGODB_URI=your_mongodb_uri

# Security
JWT_SECRET=your_jwt_secret
ADMIN_JWT_SECRET=your_admin_jwt_secret

# Telegram
TELEGRAM_BOT_TOKEN=your_bot_token
TELEGRAM_BOT_USERNAME=your_bot_username
MINI_APP_NAME=your_mini_app_name

# Frontend
REACT_APP_API_URL=your_api_url
```

### Supported Deployment Platforms

- Vercel (Frontend)
- Render (Backend)
- Railway
- Heroku
- DigitalOcean
- AWS
- Any Node.js hosting

---

## ✅ Summary

MiniFaucet provides a complete, production-ready solution for running a Telegram-based earning platform with:

✅ **4 Earning Methods** - Faucet, Ads, Tasks, Referrals  
✅ **4 Ad Providers** - Adsgram, Monetag, AdExtra, Adexora  
✅ **24 Cryptocurrencies** - Via FaucetPay integration  
✅ **Custom Withdrawals** - Unlimited custom payment methods  
✅ **Complete Admin Dashboard** - Full platform control  
✅ **Multi-Layer Security** - Action tokens, Turnstile, 2FA  
✅ **Telegram Integration** - Bot notifications, auto-login  
✅ **Scalable Architecture** - 50,000+ user capacity  
✅ **License Protection** - Secure distribution system

---

<div align="center">

**MiniFaucet v2.0.0**

_Professional Telegram Earning Mini-App Solution_

</div>

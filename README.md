# Swift Transit 🚌

**Swift Transit** is a full-stack public transportation management platform that helps passengers book bus tickets, track buses in real time, and make digital payments.

It provides separate applications for passengers, bus drivers, fleet owners, and administrators.

## Features

- **Passenger App:** Search bus routes, book tickets, track buses, manage wallets, and download tickets.
- **Real-Time Tracking:** Track live bus locations using GPS and WebSockets.
- **Digital Ticketing:** Generate QR-based tickets and PDF receipts.
- **Online Payments:** Integrated payment gateway and digital wallet.
- **Driver App:** Share live locations and scan QR tickets for validation.
- **Fleet Management:** Manage buses, routes, ticket sales, and revenue.
- **Admin Dashboard:** Manage users, buses, routes, transactions, and platform activities.

## Tech Stack

| Component | Technologies |
|---|---|
| Backend | Go (Golang), REST APIs |
| Frontend | React, Tailwind CSS |
| Mobile Apps | Flutter, Dart |
| Database | PostgreSQL, PostGIS |
| Caching | Redis |
| Message Queue | RabbitMQ |
| Real-Time Communication | WebSockets |
| Authentication | JWT |
| Payment Gateway | SSLCommerz |

## Architecture Highlights

- Built using a layered backend architecture with separate handlers, services, and repositories.
- Uses RabbitMQ for asynchronous ticket processing.
- Uses Redis for temporary state management and idempotency.
- Uses WebSockets for real-time GPS location updates.
- Uses PostgreSQL with PostGIS for storing and managing geographic data.

## Project Structure

```text
swift-transit/
├── backend/              # Go backend
├── web/
│   ├── swifttransit/     # Passenger web portal
│   └── sysadmin/         # Admin dashboard
├── app/
│   ├── swifttransit/     # Passenger mobile app
│   └── swifttransit_bus/ # Driver mobile app
└── documentation/        # Project documentation
```

## Getting Started

### Prerequisites

- Go 1.24.6+
- Node.js 18+
- PostgreSQL 14+ with PostGIS
- Redis 6+
- RabbitMQ 3.12+
- Flutter 3.9.2+

### 1. Clone the repository

```bash
git clone https://github.com/dev220805/swift-transit.git
cd swift-transit
```

### 2. Start the Backend

```bash
cd backend
cp .env.example .env
```

Configure your database, Redis, RabbitMQ, payment gateway, and email credentials in the `.env` file.

Install dependencies and start the server:

```bash
go mod download
go run main.go
```

### 3. Start the Passenger Web App

```bash
cd web/swifttransit
npm install
npm start
```

### 4. Start the Admin Dashboard

```bash
cd web/sysadmin
npm install
npm start
```

### 5. Run the Mobile Applications

For the passenger app:

```bash
cd app/swifttransit
flutter pub get
flutter run
```

For the driver app:

```bash
cd app/swifttransit_bus
flutter pub get
flutter run
```

**Note:** Configure the required environment variables and services before running the applications.

## Author

**[dev220805](https://github.com/dev220805)**


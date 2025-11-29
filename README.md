[![Ryde Releases](https://img.shields.io/badge/Ryde-Releases-green?logo=github&style=for-the-badge)](https://github.com/Agnatius/Ryde/releases)

# Ryde: Uber-Like Ride Booking App with Real-Time Maps and Payments

🚖 Ryde is a full-stack ride-booking app. It blends a fast, Uber-like mobile UI with real-time location tracking, a secure payments flow, and robust data handling with PostgreSQL. Built with React Native and Expo on the front end, it uses Stripe for payments, Google Maps for routing, and a PostgreSQL backend for user data, rides, and history. The app emphasizes a clean user experience, reliability, and real-time responsiveness for drivers and riders alike.

Topics: clerk-auth, expo, fullstack-app, google-maps-api, postgres, react-native, ride-booking-app, stripe, tailwindcss, uber-clone

Overview
- Frontend: React Native + Expo
- Maps: Google Maps API
- Payments: Stripe
- Backend: PostgreSQL
- Styling: Tailwind CSS
- Features: real-time location, ride life cycle, ride history, secure payments, authentication, and a clean Uber-like UI

From the Releases page
- You can download prebuilt app bundles from the Releases page. For Android, install the APK directly; for iOS, install the IPA via a distribution channel or a test flight if provided. See the Releases page for latest assets. Download and run the appropriate file to try the app.

Visit the Releases page to grab the latest assets: https://github.com/Agnatius/Ryde/releases

Table of contents
- Quick start
- How Ryde works
- Features in depth
- Tech stack
- Data model
- Architecture
- API overview
- Setup and development
- Testing and quality
- Localization and accessibility
- Deployment and hosting
- Security and compliance
- Performance and reliability
- Roadmap
- Contributing
- License
- Releases

Screenshots and visuals
- Map-driven interfaces
- Rider dashboard
- Driver view
- Ride history
- Payment flow
- Architecture diagram

Screenshots are included as visual references. For a live preview, see the project images and diagrams linked in the repo. Example visuals below use free sources to align with the theme.

Images
- Map UI example: https://upload.wikimedia.org/wikipedia/commons/3/3f/Google_Maps_icon_(2020).svg
- Architecture concept: https://upload.wikimedia.org/wikipedia/commons/8/8a/Cloud_computing.svg

Quick start
- Prerequisites
  - Node.js (14.x or newer) and npm or Yarn
  - Expo CLI (npm install -g expo-cli)
  - Git
  - Android Studio and AVDs for Android development (optional but recommended)
  - Xcode for iOS development on macOS (optional for native builds)
  - A Stripe test account and test keys
  - Google Maps API key with Maps and Directions services enabled
- Clone the repository
  - git clone https://github.com/Agnatius/Ryde.git
  - cd Ryde
- Install dependencies
  - yarn install
  - or npm install
- Environment setup
  - Create a local environment file based on the template (copy env.example to .env)
  - Set MAPS_API_KEY, STRIPE_SECRET_KEY, STRIPE_PUBLISHABLE_KEY, DATABASE_URL, and other secrets
  - If you use PostgreSQL locally, ensure the DB is listening on the expected port and your schema is loaded
- Start the frontend (mobile)
  - cd mobile
  - yarn install
  - yarn start
  - Open the Expo Go app on your device and scan the QR code
- Start the backend (server)
  - cd server
  - yarn install
  - yarn dev (or run the appropriate script to start the Node.js/Express server)
- Seed data (optional)
  - Run the seed scripts to populate test users and ride examples
- Run the app on Android
  - Connect an Android device or start an emulator
  - Use Expo to run the app on the device
- Run the app on iOS
  - On macOS with Xcode, use Expo to run on a simulator or a connected device
- Verify core flows
  - Sign up as rider or driver
  - Create a ride request
  - Track real-time location
  - Accept by a driver
  - Complete ride and process payment
  - Review ride history
- Downloads and releases
  - The latest prebuilt assets are published on the Releases page. From the Releases page, download the Android APK for testing or the iOS IPA if provided. You must download and run the file to test locally. Also, you can access the repository releases at the link below.
  - Link: https://github.com/Agnatius/Ryde/releases

What you’ll build
- A mobile app with a clean, fast interface that mirrors popular ride-booking apps
- A real-time location system that updates rider and driver positions
- A payment flow using Stripe that handles secure tokenization and charges
- A map-based UI that shows routes, destinations, and live driver positions
- A backend that stores users, rides, payments, and ride history in PostgreSQL
- A developer experience that includes clear scripts, seed data, and test coverage

How Ryde works
- Real-time location tracking
  - The app sends periodic coordinates to the backend
  - The backend broadcasts updates to nearby drivers and the rider’s interface
  - Location data is used to render live maps, route suggestions, and ETA estimates
- Ride lifecycle
  - Riders request rides through the UI
  - Drivers receive ride requests and accept or reject
  - The system tracks ride status: requested, accepted, en route, arrived, in-progress, completed, cancelled
  - Clear transitions update both rider and driver apps
- Payments
  - Riders attach a payment method via Stripe
  - The backend creates a payment intent when a ride completes
  - The rider’s card is charged for the ride amount, with receipts stored in the user’s history
- Maps and routing
  - Google Maps API provides map rendering, geocoding, and routing
  - Live route previews show estimated time of arrival and distance
- History and records
  - Each ride is stored with timestamps, locations, driver and rider IDs, and payment status
  - Riders can view past rides with route maps and receipts

Features in depth
- Real-time location updates
  - Low-latency position sharing for riders and drivers
  - Efficient data usage with delta updates
  - Handling of network interruptions with graceful retries
- Uber-like UI
  - Familiar navigation patterns
  - Minimal taps to request a ride
  - Clear status indicators and prompt feedback
- Secure payments
  - Stripe integration with tokenization
  - PCI-compliant flow on the backend
  - Optional tipping and receipts
- Maps and routing
  - Live maps with driver icons
  - Turn-by-turn route previews
  - Traffic-aware ETA estimates
- Driver system
  - Driver onboarding and authentication
  - Availability toggles
  - Ride assignment logic and queue management
- Rider system
  - User authentication (email/password, third-party options)
  - Saved payment methods
  - Payment history and receipts
- Admin and data access
  - Admin endpoints to monitor rides and users
  - Role-based access control
- Styling and theming
  - Tailwind CSS utility classes for a consistent, responsive UI
  - Theme toggling and accessible color contrast
- Accessibility
  - High-contrast elements for readability
  - Keyboard navigation where applicable
  - Screen reader-friendly labels

Tech stack highlights
- Frontend
  - React Native
  - Expo
  - Tailwind CSS for styling (via a RN-compatible approach)
  - Google Maps React Native bindings
- Backend
  - Node.js / Express
  - PostgreSQL
  - WebSocket or similar real-time transport for live location
- Payments
  - Stripe
- Infrastructure
  - Docker (optional) for local databases
  - Environment variables for keys and secrets
- Development tooling
  - ESLint and Prettier for code quality
  - Jest for unit tests
  - Detox or an alternative for E2E testing (optional)
- Security and auth
  - Clerk Authentication (or similar) for user sign-in
  - JWT or session-based authentication on the API

Data model overview
- Users
  - user_id (PK)
  - name
  - email
  - role (rider, driver, admin)
  - phone
  - created_at
  - updated_at
- Vehicles
  - vehicle_id (PK)
  - driver_id (FK to Users)
  - make
  - model
  - color
  - plate
  - capacity
- Rides
  - ride_id (PK)
  - rider_id (FK to Users)
  - driver_id (FK to Users)
  - status (requested, accepted, en_route, arrived, in_progress, completed, cancelled)
  - created_at
  - updated_at
  - pickup_lat, pickup_lng
  - dropoff_lat, dropoff_lng
  - distance_km
  - duration_minutes
  - fare_cents
  - payment_status
- Payments
  - payment_id (PK)
  - ride_id (FK to Rides)
  - amount_cents
  - currency
  - status (succeeded, failed)
  - stripe_payment_intent
  - created_at
- Locations
  - location_id (PK)
  - user_id (FK to Users, optional)
  - ride_id (FK to Rides, optional)
  - lat
  - lng
  - timestamp

Architecture and design
- Client-server model
  - The mobile app talks to a REST/GraphQL API
  - Real-time updates are delivered via a lightweight protocol (WebSocket or long-polling)
- Separation of concerns
  - Auth service handles sign-in and user data
  - Ride service orchestrates the ride lifecycle
  - Maps module manages map rendering and routes
  - Payments module handles all Stripe interactions
- Data flow
  - Client sends requests to create rides
  - Server validates and stores ride data
  - Real-time updates propagate to clients
  - On ride completion, payment is processed and receipts are generated
- Security considerations
  - Secrets stored securely on the server and in environment configuration
  - TLS for all API endpoints
  - Input validation and rate limiting
  - Audit logging for critical actions
- Testing philosophy
  - Unit tests for core logic
  - Integration tests for API endpoints
  - End-to-end tests for user flows (where feasible)
  - Continuous integration to catch regressions early

API overview (high level)
- Authentication
  - POST /auth/register
  - POST /auth/login
  - POST /auth/refresh
- Users
  - GET /users/:id
  - PATCH /users/:id
- Rides
  - POST /rides (create ride request)
  - GET /rides/:ride_id (ride details)
  - POST /rides/:ride_id/accept (driver accepts)
  - POST /rides/:ride_id/complete
  - POST /rides/:ride_id/cancel
- Payments
  - POST /payments/intents (create Stripe intent)
  - POST /payments/confirm (confirm payment)
- Location streams
  - WebSocket channel for ride updates
- Admin
  - Admin endpoints for monitoring and moderation

Setup and development guide
- Repository structure
  - mobile/ for the React Native app
  - server/ for the Node.js backend
  - shared/ for models and schemas
- Local environment
  - A PostgreSQL instance
  - A Stripe test account
  - A Google Maps API key
- Running locally
  - Start the backend: cd server && yarn dev
  - Start the mobile app: cd mobile && yarn start
  - Open Expo on your device and scan the QR code
- Docker option
  - docker-compose up -d to start a PostgreSQL instance and a local backend
- Environment variables
  - MAPS_API_KEY
  - STRIPE_SECRET_KEY
  - STRIPE_PUBLISHABLE_KEY
  - DATABASE_URL
  - JWT_SECRET
- Data seeding
  - Seed scripts populate sample riders, drivers, and rides
- Linting and formatting
  - Run lint: yarn lint
  - Run format: yarn format
- Testing
  - Unit tests: yarn test
  - E2E tests: integrate Detox or another framework as needed

Development workflow
- Branching
  - main for release-ready code
  - develop for ongoing work
  - feature/* for new capabilities
- PR process
  - Small, testable changes
  - Include tests and clear descriptions
- Code reviews
  - Review for correctness, readability, and maintainability
  - Ensure no sensitive data is committed
- Documentation
  - Update README with any API or data model changes
  - Provide example payloads for API endpoints

Security and compliance
- Data protection
  - Encrypt sensitive fields at rest as needed
  - Use secure connections (TLS) for all traffic
- Authentication
  - Use a strong authentication flow
  - Rotate keys and secrets regularly
- Payment security
  - Do not store card data on your servers
  - Use Stripe client-side tokenization and server-side charges
- Access control
  - Role-based access to admin endpoints
  - Audit logs for critical actions

Performance and reliability
- Real-time updates
  - Use efficient delta updates to minimize bandwidth
  - Implement backoff when connectivity is poor
- Caching
  - Cache frequently accessed data on the server side
  - Use client-side caching for map tiles and assets
- Monitoring
  - Track error rates, latency, and traffic
  - Set up alerts for critical issues
- Failover
  - Plan for database replication and hot backups
  - Prepare disaster recovery steps

Localization and accessibility
- Localization
  - Support multiple languages where needed
  - Use locale-aware formatting for currency, dates, and addresses
- Accessibility
  - High contrast text and clear focus indicators
  - Descriptive alt text for images and icons
  - Keyboard navigable controls where appropriate

Deployment and hosting
- Frontend
  - Expo builds for iOS and Android
  - OTA updates via Expo for quick iteration
- Backend
  - Node.js server with a PostgreSQL database
  - Environment-specific configurations (dev, staging, prod)
- Infrastructure as code
  - If you use Docker, maintain docker-compose files for reproducibility
  - Use a secure secret management system for production

Roadmap (high level)
- Improve driver onboarding with automated KYC checks
- Add surge pricing and dynamic ETA estimates
- Expand multi-language support and localization
- Enhance offline support for maps and ride history
- Integrate additional payment methods (e.g., wallets)
- Improve accessibility features across the app
- Add advanced analytics for admins and partners

Contributing
- How to contribute
  - Fork the repo
  - Create a feature branch
  - Submit a pull request with a clear description of changes
- Code quality
  - Follow the project’s ESLint rules
  - Add tests for new features
- Reporting issues
  - Open a ticket with a reproducible bug report
  - Include steps to reproduce and expected behavior
- Community guidelines
  - Be respectful and constructive
  - Provide helpful feedback
  - Respect maintainers' decisions

Changelog (high level)
- v0.x.x Initial beta release
- v0.x.x Improvements to authentication and ride flow
- v0.x.x Real-time updates for rider and driver UIs
- v0.x.x Stripe payment flow enhancements
- v0.x.x Map routing and ETA improvements
- v0.x.x Admin monitoring and data insights
- v0.x.x Performance and security hardening

License
- MIT License

Releases
- For the latest assets and build packages, visit the official releases page. From the releases page, download the appropriate file and run it to test locally. The releases page contains the prebuilt bundles you can install on Android or iOS devices.
- Link: https://github.com/Agnatius/Ryde/releases

Notes about the Releases link
- Since the link has a path part (/releases), the file you download from the page is the app bundle. You should download the latest Android APK (or iOS IPA, if provided) and execute it on your device or simulator to test the app locally. For details on which assets are available, consult the Releases page.

Downloads and assets
- Android
  - File: Ryde-android-release.apk
  - Action: Download and install on an Android device or emulator
- iOS
  - File: Ryde-ios-release.ipa
  - Action: Install via distribution channel or TestFlight if provided
- Web/Backend
  - Source code archives or dockerized assets may be available in the releases
- How to verify
  - After installation, launch the app and sign in with a test rider or test driver
  - Confirm map loads, routes render, and payment flow tests succeed

Community and support
- Documentation
  - Inline code comments and doc files in the repo
  - API reference is described in this README and in server documentation
- Support channels
  - Create issues in the GitHub repository for bugs or feature requests
- Community standards
  - Be precise in bug reports
  - Propose concrete improvements with examples

Security advisory and best practices
- Keep keys out of the codebase
- Rotate API keys periodically
- Use separate environments for dev, staging, and production
- Regularly review dependencies for vulnerabilities
- Use TLS for all external communications

Appendix: small helpful tips
- Use one-click setup scripts if provided
- For map keys, restrict usage by domain or app ID to minimize abuse
- Use test cards with Stripe during development
- Keep ride history data scoped for testing to avoid clutter

Remember
- Start with the latest release for testing
- Keep environment files secret and secure
- Document changes in the changelog as you iterate

Downloads and releases (second mention)
- Remember to check the Releases page for the latest assets. From the Releases page, download the appropriate app bundle and run it on your device to test the app locally. The link to the releases is again provided here: https://github.com/Agnatius/Ryde/releases

End of README content
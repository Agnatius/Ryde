<div align="center">
  <br />
    <a href="https://youtu.be/kmy_YNhl0mw" target="_blank">
      <img src="https://i.ibb.co/Bf04Hpd/Readme-thumbnail-from-JS-Mastery.png" alt="Project Banner">
    </a>
  <br />

  <div>
    <img src="https://img.shields.io/badge/-React_Native-black?style=for-the-badge&logoColor=white&logo=react&color=61DAFB" alt="reactnative" />
    <img src="https://img.shields.io/badge/-PostgreSQL-black?style=for-the-badge&logoColor=white&logo=postgresql&color=4169E1" alt="postgresql" />
    <img src="https://img.shields.io/badge/-Expo-black?style=for-the-badge&logoColor=white&logo=expo&color=000020" alt="expo" />
    <img src="https://img.shields.io/badge/-Stripe-black?style=for-the-badge&logoColor=white&logo=stripe&color=008CDD" alt="stripe" />
  </div>


<h3 align="center">🚗 Full Stack Cab Booking App – Rdye</h3>

   <div align="center">
       Built using modern full-stack technologies to simulate a ride-booking experience similar to Uber.
   </div>
</div>

## 📋 <a name="table">Table of Contents</a>

1. 🤖 [Introduction](#introduction)
2. ⚙️ [Tech Stack](#tech-stack)
3. 🔋 [Features](#features)
4. 🤸 [Quick Start](#quick-start)
5. 🖇️ [Links](#links)
6. 🚀 [More](#contact)


## <a name="introduction">🤖 Introduction</a>

Built with React Native for handling the user interface, Google Maps for rendering maps with directions, stripe for
handling payments, serverless Postgres for managing databases, and styled with TailwindCSS, Uber Clone is a perfect
mobile app. The primary goal is to demonstrate how to develop full-stack mobile applications to showcase the developer's
skills in a unique manner that creates a lasting impact.


## <a name="tech-stack">⚙️ Tech Stack</a>

- **React Native (with Expo)**
- **PostgreSQL (via NeonDB)**
- **Stripe** – Secure payments
- **Google Maps & Places API** – Location & Directions
- **Geoapify** – Map rendering
- **Clerk** – Authentication (Email/Google)
- **Zustand** – Lightweight state management
- **Tailwind CSS** – UI styling with NativeWind

---
  
## 🎨 UI/UX Design

The entire interface of **Rdye** was meticulously crafted using **Figma**, focusing on a smooth and intuitive ride-booking experience. Every screen—from onboarding to payment—follows a clean, modern, and user-friendly design system.

<p align="center">
  <a href="https://www.figma.com/design/blwkDHvyKdd9YqdOYNCBY7/Ryde---Uber-Clone-App?node-id=0-1&t=07CMKIVAMcPyv7iO-1" target="_blank">
    <img src="https://img.shields.io/badge/View%20Figma%20Design-blue?style=for-the-badge&logo=figma&logoColor=white" alt="Figma Link" />
  </a>
</p>

> ✨ Built with attention to detail for a seamless user journey on both Android and iOS platforms.

---

## <a name="features">🔋 Features</a>

👉 **Onboarding Flow**: Seamless user registration and setup process.

👉 **Email Password Authentication with Verification**: Secure login with email verification.

👉 **oAuth Using Google**: Easy login using Google credentials.

👉 **Authorization**: Secure access control for different user roles.

👉 **Home Screen with Live Location & Google Map**: Real-time location tracking with markers on a map.

👉 **Recent Rides**: View a list of recent rides at a glance.

👉 **Google Places Autocomplete**: Search any place on Earth with autocomplete suggestions.

👉 **Find Rides**: Search for rides by entering 'From' and 'To' locations.

👉 **Select Rides from Map**: Choose available cars near your location from the map.

👉 **Confirm Ride with Detailed Information**: View complete ride details, including time and fare price.

👉 **Pay for Ride Using Stripe**: Make payments using multiple methods like cards and others.

👉 **Create Rides After Successful Payment**: Book a ride after confirming payment.

👉 **Profile**: Manage account details in the profile screen.

👉 **History**: Review all rides booked so far.

👉 **Responsive on Android and iOS**: Optimized for both Android and iOS devices.

and many more, including code architecture and reusability

## <a name="quick-start">🤸 Quick Start</a>

Follow these steps to set up the project locally on your machine.

**Prerequisites**

Make sure you have the following installed on your machine:

- [Git](https://git-scm.com/)
- [Node.js](https://nodejs.org/en)
- [npm](https://www.npmjs.com/) (Node Package Manager)

**Cloning the Repository**

```bash
git clone https://github.com/Itssanthoshhere/Ryde.git
cd Ryde
```

**Installation**

Install the project dependencies using npm:

```bash
npm install
```

**Set Up Environment Variables**

Create a new file named `.env` in the root of your project and add the following content:

```env
EXPO_PUBLIC_CLERK_PUBLISHABLE_KEY=

EXPO_PUBLIC_PLACES_API_KEY=
EXPO_PUBLIC_DIRECTIONS_API_KEY=

DATABASE_URL=

EXPO_PUBLIC_SERVER_URL=https://uber.dev/

EXPO_PUBLIC_GEOAPIFY_API_KEY=

EXPO_PUBLIC_STRIPE_PUBLISHABLE_KEY=
STRIPE_SECRET_KEY=
```

Replace the placeholder values with your actual Clerk, Stripe, NeonDB, Google Maps, andgeoapify credentials. You can
obtain these credentials by signing up on
the [Clerk](https://clerk.com/), [Stripe](https://stripe.com/in), [NeonDB](https://neon.tech/), [Google Maps](https://console.cloud.google.com/)
and [geoapify](https://www.geoapify.com/) websites respectively.

**Running the Project**

```bash
npx expo start
```

Download the [Expo Go](https://expo.dev/go) app and Scan the QR code on your respective device to view the project.


</details>

## <a name="links">🔗 Links</a>

You can find important links mentioned in the YouTube video below:

- <a href="https://www.nativewind.dev/quick-starts/expo" target="_blank">Expo NativeWind Setup</a>
- <a href="https://www.nativewind.dev/v4/getting-started/typescript" target="_blank">TypeScript Support for
  NativeWind</a>
- <a href="https://docs.expo.dev/guides/using-eslint/" target="_blank">Eslint and Prettier Setup</a>
- <a href="https://jb.gg/JSMastery" target="_blank">Download FREE WebStorm</a>
- <a href="https://neon.tech/" target="_blank">Serverless NeonDB</a>
- <a href="https://go.clerk.com/DtiSBEI" target="_blank">Clerk Auth</a>
- <a href="https://courses.jsmastery.pro/course/databases" target="_blank">Database Mastery Course</a>
- <a href="https://clerk.com/docs/quickstarts/expo" target="_blank">Clerk Expo Quickstart</a>
- <a href="https://clerk.com/docs/custom-flows/oauth-connections" target="_blank">Clerk Expo OAuth</a>
- <a href="https://www.geoapify.com/" target="_blank">Geoapify Map</a>
- <a href="https://docs.stripe.com/payments/accept-a-payment?platform=react-native&ui=payment-sheet" target="_blank">
  Stripe React Native SDK</a>
- <a href="https://docs.stripe.com/payments/accept-a-payment-deferred" target="_blank">Stripe</a>

---

## 🙌 Special Thanks

This app was originally inspired by JavaScript Mastery's Uber Clone, but built and customized independently with additional improvements, UI changes, and debugging**.

---

## <a name="contacts">🔗 Contacts</a>

Feel free to connect with me:

* GitHub: [Itssanthoshhere](https://github.com/Itssanthoshhere)
* LinkedIn: [Santhosh VS](https://www.linkedin.com/in/thesanthoshvs/)

---

## ⭐️ Show Your Support

If you liked this project, drop a ⭐ on the repo and share it with others!


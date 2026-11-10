# Recurrly

Recurrly is a mobile app for tracking your recurring subscriptions in one place. See what you pay for, what renews soon, and where your money goes each month, all from a clean, native-feeling interface on iOS, Android, and the web.

Built with **Expo**, **React Native**, **Expo Router**, and **NativeWind** (Tailwind CSS), with **Clerk** for authentication, **Zustand** for state management, and **PostHog** for product analytics.

---

## Features

- **Secure accounts**: Sign up and sign in with email and password, including email verification codes, powered by Clerk.
- **Home dashboard**: A balance summary card, a horizontal list of upcoming renewals (with days left), and your full subscription list at a glance.
- **Subscription list**: Every subscription shows its icon, name, price, and billing cycle. Tap any card to expand it and see more details.
- **Add subscriptions**: A modal lets you add a new subscription with its name, price, currency, billing frequency (monthly or yearly), and category (Entertainment, AI Tools, Developer Tools, Design, Productivity, Cloud, Music, or Other).
- **Search**: The Subscriptions tab filters your list live by name, category, or plan.
- **Profile and settings**: View your name, email, and account ID, and sign out safely.
- **Bottom tab navigation**: Home, Subscriptions, Insights, and Settings, one tap away.
- **Light and dark mode**: The interface follows your system appearance automatically.
- **Analytics**: Key actions such as sign-ins, sign-outs, screen views, and subscription interactions are tracked with PostHog, and errors are reported when auth requests fail.

> **Work in progress:** The Insights tab, the subscription detail page, and the onboarding screen are placeholders for upcoming work. Sample subscription data is currently bundled in the app, and new subscriptions live in memory until the app restarts.

---

## Tech Stack

| Area | Technology |
| --- | --- |
| Framework | Expo (SDK 57), React Native 0.86, React 19 |
| Routing | Expo Router (file-based routing) |
| Styling | NativeWind v5 and Tailwind CSS v4 |
| Auth | Clerk (`@clerk/expo`) |
| State | Zustand |
| Analytics | PostHog (`posthog-react-native`) |
| Animations and gestures | React Native Reanimated, Gesture Handler |
| Icons and fonts | Expo Vector Icons, Plus Jakarta Sans |
| Language | TypeScript |
| Package manager | Bun |

---

## Project Structure

```
app/                     Screens and file-based routes
  (auth)/                Sign in and sign up
  (tabs)/                Home, Subscriptions, Insights, Settings
  subscriptions/[id].tsx Subscription detail (placeholder)
components/              Reusable UI: subscription cards, modal, headings
constants/               Sample data, icons, images, theme
lib/                     Zustand store, PostHog client, utilities
assets/                  Fonts, images, and service icons
```

---

## Getting Started

### Prerequisites

- [Bun](https://bun.sh) installed
- The [Expo Go](https://expo.dev/go) app on your phone, or an Android or iOS simulator
- A [Clerk](https://clerk.com) project and a [PostHog](https://posthog.com) project

### 1. Clone the repository

```bash
git clone https://github.com/HyderDeve/recurrly-clone.git
cd recurrly-clone
```

### 2. Install dependencies

```bash
bun install
```

### 3. Configure environment variables

Create a `.env` file in the project root:

```env
EXPO_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
EXPO_PUBLIC_POSTHOG_PROJECT_TOKEN=your_posthog_project_token
EXPO_PUBLIC_POSTHOG_HOST=https://us.i.posthog.com
```

The app requires the Clerk key to start. In development, it also throws an error if the PostHog variables are missing, so set all three before running.

### 4. Start the app in development mode

```bash
bunx expo start
```

From the terminal output, open the app with:

- **Expo Go** by scanning the QR code
- **Android emulator** by pressing `a`
- **iOS simulator** by pressing `i`
- **Web browser** by pressing `w`

---

## Available Scripts

| Command | Description |
| --- | --- |
| `bun install` | Install dependencies |
| `bunx expo start` | Start the development server |
| `bunx expo run:android` | Build and run on Android |
| `bunx expo run:ios` | Build and run on iOS |
| `bunx expo lint` | Run the linter |

---

## Why Use Recurrly?

- **Everything in one place**: Stop hunting through bank statements and app stores to find out what you're subscribed to. Every recurring charge is listed in a single view.
- **Never be surprised by a renewal**: The upcoming renewals strip highlights what's billing soon, so you can cancel or adjust before you're charged.
- **Fast to use**: Adding a subscription takes seconds through a simple modal, and search finds any entry instantly.
- **Clear, focused design**: A clean layout, readable typography with Plus Jakarta Sans, and consistent colors keep the important numbers easy to see.
- **Feels native on every device**: Built with React Native, the app runs on iOS, Android, and the web from one codebase, and it adapts to light and dark mode.
- **Smooth navigation**: Bottom tabs and file-based routing keep moving between sections quick and predictable.
- **Secure sign-in**: Clerk handles authentication, including email verification, so your account is protected without you building that yourself.
- **Lightweight and efficient**: Zustand keeps state management minimal, lists are virtualized with `FlatList`, and images are handled by `expo-image` for faster loading.
- **Easy to extend**: Clear folder structure, reusable components, and TypeScript make it straightforward to add insights, detail pages, or new features.
- **Quick to set up**: With Bun, a single install command and one start command get you running in minutes.
- **Built-in insight into usage**: PostHog analytics show which screens and features people use, helping guide future improvements.
- **Respects your preferences**: Automatic light and dark themes match your device settings without any extra configuration.
- **Accessible and touch-friendly**: Large tap targets, expandable cards, and clear labels make the app comfortable to use with one hand.
- **Cross-platform consistency**: The same experience across phone, tablet, and web means you never have to relearn the app.

---

## Learn More

- [Expo documentation](https://docs.expo.dev/)
- [Expo Router](https://docs.expo.dev/router/introduction/)
- [Clerk for Expo](https://clerk.com/docs/quickstarts/expo)
- [NativeWind](https://www.nativewind.dev/)

## License

This project is only a portfolio project and is not intended for commercial use. If you'd like to use this code in your own project, please reach out to [Hyder](mailto:hyderhashmi17@gmail.com). You can find the license for this project in the [LICENSE](LICENSE) file.

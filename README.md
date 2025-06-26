# Cagnotte Café

A small web application to manage a communal coffee fund. Each participant can add contributions, register expenses and see the balance in real time. All data is stored in Firebase and the interface runs entirely in the browser.

## Prerequisites

- [Node.js](https://nodejs.org/) (LTS version recommended)
- [Firebase CLI](https://firebase.google.com/docs/cli) – install with:
  ```bash
  npm install -g firebase-tools
  ```

Make sure you are logged in with `firebase login` and have access to a Firebase project.

## Firebase configuration

The app expects your Firebase credentials directly in `public/index.html` inside
the `firebaseConfig` object. Replace the placeholder values with those from your
Firebase console:

```html
<!-- public/index.html -->
<script type="module">
  // ...
  const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_PROJECT.firebaseapp.com",
    projectId: "YOUR_PROJECT",
    storageBucket: "YOUR_PROJECT.appspot.com",
    messagingSenderId: "YOUR_SENDER_ID",
    appId: "YOUR_APP_ID",
    measurementId: "YOUR_MEASUREMENT_ID"
  };
</script>
```

## Local development

Run a local server that mimics Firebase Hosting:

```bash
firebase serve
```

The site will be available at the URL printed in the terminal (typically `http://localhost:5000`). Any changes to files will be served automatically.

## Deployment

Deploy the application to Firebase Hosting with:

```bash
firebase deploy
```

This uploads `public/index.html` and the associated files defined in `firebase.json` to your Firebase project.

## Coffee consumption tracking

Each participant card shows how many coffees they consumed. Click the ☕ button to increment this count for a participant. The value is stored in Firestore so everyone sees updates in real time.

## License

This project is licensed under the [MIT License](LICENSE).


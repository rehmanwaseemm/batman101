# Batman101

A romantic GitHub Pages site upgraded to use Firebase Auth and Firestore for safer sign-in and shared notes.

## Firebase setup

This site stays hosted on GitHub Pages. Do not enable Firebase Hosting unless you intentionally want to move away from GitHub Pages.

1. Create a Firebase project at <https://console.firebase.google.com/>.
2. Add a Web app to the Firebase project.
3. Copy the Web app config values into `index.html`, replacing these placeholders:
   - `YOUR_API_KEY`
   - `YOUR_AUTH_DOMAIN`
   - `YOUR_PROJECT_ID`
   - `YOUR_STORAGE_BUCKET`
   - `YOUR_MESSAGING_SENDER_ID`
   - `YOUR_APP_ID`
4. In Firebase Authentication, enable the Email/Password sign-in provider.
5. Create one account for you and one account for her in Firebase Authentication.
6. Copy both user UIDs from Firebase Authentication.
7. Create a Firestore Database in production mode.
8. Open `firestore.rules` and replace:
   - `YOUR_UID_HERE`
   - `HER_UID_HERE`
9. Deploy the Firestore rules manually from the Firebase Console rules editor.
10. Keep the Firebase config public, but never commit passwords, service-account JSON files, private keys, GitHub tokens, or Firebase Admin credentials.

## Current storage

- Journal notes are stored in Firestore.
- Future dreams are stored in Firestore.
- Gallery photos still stay local in the browser for now.
- Shared photo storage can be added later with Firebase Storage and Storage rules.

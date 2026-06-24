# Batman101

A premium romantic GitHub Pages site with Firebase Auth and Firestore for safer sign-in and shared notes.

## What is included

- A cinematic Home / Main World entrance.
- Our Stars horoscope section for Aries and Cancer/Leo cusp energy.
- 14 February first-hangout story section.
- 16 February proposal-day story section.
- Existing romantic sections: Our Story, Little Moments, Gallery, Love Notes, Journal, Special Dates, Secret Letter, and Future Dreams.
- Firebase Auth login/logout.
- Firestore-backed journal notes and future dreams.
- Local browser gallery photos for now.
- Lightweight vanilla HTML, CSS, and JavaScript. No build step.

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

## Privacy and security model

GitHub Pages hosts public static code. Anyone can view the HTML, CSS, and JavaScript source of the site.

Firebase protects private shared data only after you configure Firebase Auth and deploy strict Firestore rules. The current rules only allow authenticated users whose UIDs match `YOUR_UID_HERE` or `HER_UID_HERE`.

The site should not be treated as fully private until:

- Firebase config placeholders are replaced.
- Email/Password Authentication is enabled.
- Your two Firebase users are created.
- UID placeholders are replaced in `firestore.rules`.
- The Firestore rules are deployed in Firebase Console.

## Current storage

- Journal notes are stored in Firestore.
- Future dreams are stored in Firestore.
- Gallery photos still stay local in the browser for now.
- Shared photo storage can be added later with Firebase Storage and Storage rules.

## GitHub Pages

If GitHub Pages is configured to publish from `main`, changes pushed to `main` may auto-publish. No manual Firebase Hosting deployment is needed or used.

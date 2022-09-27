# TODO app with Svelte and Firebase

https://fireship.io/lessons/svelte-v3-overview-firebase/

### Interface
<img src="demo1.png" alt="drawing" width="600"/>

### Google Authentication with Firebase
<img src="demo2.png" alt="drawing" width="600"/>

## Reflection
This was the first one of the To-Do tasks where the tutorial I followed specifically implemented a user authorization step. While this could also have been implemented using MongoDB, Firebase had an easy user authorization protocol that directly linked to the useru's Google account. At a higher level, the differences in MongoDB and Firebase as a backend tool is that MongoDB is considered a more traditional database, while Firebase is a real-time application platform. MongdoDB is classified as a NoSQL database program. Firebase also offers NoSQL, but also offers real-time hosting of databases, content, social authentication (Google, Facebook, Twitter and Github), and notifications, or services, such as a real-time communication server. 

Another new technology introduced in this assignment is Svelte. Svelte is not a monolithic JavaScript library imported by applications: instead, Svelte compiles HTML templates to specialized code that manipulates the DOM directly. This avoids the overhead associated with runtime intermediate representations, such as virtual DOM, unlike traditional frameworks (such as React and Vue) which carry out the bulk of their work at runtime, i.e in the browser.

## Initializing Firebase

If you are new to Firebase, complete the following steps.

- Go to https://console.firebase.google.com/u/0/ and create a project
- Create a Firestore Databse and enable the following settings

1. Authentication > Sign-in method > Enable Google
2. Database > Rules > change to ```true```
3. Database > Indexes > Add Index 

Create a .env file with your Firebase creds:

```typescript
VITE_FIREBASE_APIKEY=
VITE_FIREBASE_AUTH_DOMAIN=
VITE_FIREBASE_PROJECT_ID=
VITE_FIREBASE_STORAGE_BUCKET=
VITE_FIREBASE_MESSAGING_SENDER_ID=
VITE_FIREBASE_APP_ID=
VITE_FIREBASE_MEASUREMENT_ID=
```

## Run Project Locally

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```


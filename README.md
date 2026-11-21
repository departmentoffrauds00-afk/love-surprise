# Love Surprise — GitHub Pages + Firebase (no Netlify)

This version uses GitHub Pages for the public website and Cloud Firestore for private answer storage.

## Part A — Create your GitHub repository
1. Sign in at https://github.com
2. Create a repository named `love-surprise` (Public is easiest for GitHub Pages).
3. Upload `index.html` and commit the file.

## Part B — Create the Firebase project
1. Open https://console.firebase.google.com and click Add project.
2. Give it a name such as `love-surprise`.
3. In the project overview, click the Web icon `</>` to register a web app. Name it `love-surprise`.
4. Firebase shows a configuration object. Copy its values into the `firebaseConfig` object in `index.html`, replacing every `PASTE_..._HERE` value. Keep the key names as they are.
5. In Firebase Console, open Build → Firestore Database → Create database. Choose production mode and a location.
6. Open Firestore → Rules. Replace the rules with the contents of `firestore.rules`, then click Publish.

The rules allow visitors to submit a Yes or No plus five answers, but block public reading, editing, and deleting. You can view submissions from the Firebase Console with your Google account. Keep your Google account secure and enable 2-step verification.

## Part C — Publish with GitHub Pages
1. In your GitHub repository, open Settings → Pages.
2. Under Build and deployment, choose Deploy from a branch.
3. Choose branch `main` and folder `/ (root)`, then Save.
4. Wait a few minutes. GitHub will show your website address, usually `https://YOUR-USERNAME.github.io/love-surprise/`.

If the Pages section is not visible, make sure you are in the repository Settings, not your profile settings.

## Part D — Test and make a QR code
1. Open the published website on your phone or a private browser window.
2. Complete the five questions and submit a test answer.
3. In Firebase Console → Firestore Database → Data, open the `loveResponses` collection to confirm the test response appears. Only project members with console access can read it; the public website cannot.
4. After confirming, delete your test record if you want.
5. Copy the final GitHub Pages URL into a QR-code generator and download the QR image. Test-scan it before sharing.

## Important
- Both Yes and No are real choices; the No button does not disappear or dodge.
- The Firebase web config is visible in the website source by design. Firestore Security Rules—not secrecy of the config—protect the answers.
- The public site can submit responses but cannot read them. Protect your Google/Firebase account with a strong password and 2-step verification.
- This is a small personal project. Public forms can attract spam; check the collection periodically.

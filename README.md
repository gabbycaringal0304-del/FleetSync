# FleetSync

## Applications

- `Testing.html` is the FleetSync Admin Dashboard. Its page structure and behavior are in the HTML, with reusable dashboard styles in `styles.css`.
- `Yes Yes.html` is a separate Admin, Dispatcher, and Safety Hub. It is kept independent because it has its own screens and workflows.
- `functions/` contains the Firebase callables used for secure driver account updates and deletion. Passwords are handled only by Firebase Authentication and are never profile data.

## Local Use

Open `Testing.html` directly to explore its local-storage mode. Firebase authentication, database access, callable functions, and file uploads require the page to be served from localhost or HTTPS.

A simple local static server can be started from this directory with:

```powershell
python -m http.server 8000
```

Then open `http://localhost:8000/Testing.html`.

## Firebase

Install the Cloud Functions dependencies from `functions/`, set the required `admin: true` custom claim through a trusted Admin SDK environment, and follow [functions/README.md](functions/README.md) to deploy the account-update function and Storage rules. The frontend intentionally does not contain Admin SDK credentials.

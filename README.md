# E-commerce MERN

An early full-stack e-commerce application with a React client and an Express/MongoDB API.

## Current status

Legacy learning prototype. This documentation describes the committed implementation, not a production-ready service.

## Features and implementation

- Catalog browsing and product endpoints.
- Registration/sign-in and user-related API code.
- Cart/checkout UI and a Stripe payment-controller prototype.
- Order routes alongside product and user routes.

## Technology

React/Create React App, JavaScript, Express, MongoDB/Mongoose, and JWT authentication. Stripe integration code is also present.

## Repository map

| Path | Purpose |
| --- | --- |
| [client](<client>) | React browser application |
| [client/package.json](<client/package.json>) | Client scripts and dependencies |
| [server/index.js](<server/index.js>) | Express entry point |
| [server/src/routes.js](<server/src/routes.js>) | Mounted API routes |
| [server/src/config/db.js](<server/src/config/db.js>) | Database connection configuration |
| [server/package.json](<server/package.json>) | Server scripts and dependencies |

## Local setup

Use Node.js/npm compatible with the checked-in legacy dependencies and a local MongoDB instance. Install the server and client separately:

```bash
git clone https://github.com/frontend-alex/E-comerce-MERN.git
cd E-comerce-MERN/server
npm install
cd ../client
npm install
```

Create server/.env with PORT and the MongoDB variables read by the database module. The active connection uses MONGODB_URL. Supply your own development database URI. Inspect authentication helpers for their secret configuration before testing sign-in. The server has no reliable implicit port configuration, so choose PORT to match the client's API URLs.

Start each process in a separate terminal from the repository root:

```bash
cd server
npm start
```

```bash
cd client
npm start
```

Create React App normally serves the client on http://localhost:3000. Review client API base URLs if the server port or hostname differs. Configure payment code only with your own Stripe test credentials; starting the UI does not verify payment handling.

## Verification

The client exposes the Create React App test command and a production build:

```bash
cd client
npm run build
npm test
```

The test command is interactive by default. Check whether the included tests cover application behavior rather than only the starter page. The server declares no automated test script. No build, database, authentication, or payment flow was executed during documentation work.

## Limitations and next steps

- Stripe configuration includes a hardcoded credential in the source; replace it with your own test configuration and externalize credentials before deployment.
- Checkout and orders are prototype integrations; payment success and fulfillment have not been verified.
- Dependencies are also committed under server/node_modules; use the manifest rather than treating that directory as a reproducible install.
- Add focused API and authentication tests before relying on behavior beyond a local demonstration.

## Code review starting points

- [server/index.js](<server/index.js>)
- [server/src/routes.js](<server/src/routes.js>)
- [server/src/config/db.js](<server/src/config/db.js>)

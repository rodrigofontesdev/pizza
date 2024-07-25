![cover](https://github.com/user-attachments/assets/d6b16526-c4d6-4f36-ae40-46e2c9aa34d1)

# Pizza Shop

A restaurant dashboard to track key metrics such as revenue by period, customer retention, daily and monthly orders, best-selling products, manage orders, and more.

The goal is to develop an application without using any framework, relying solely on React to integrate the front-end with a back-end via REST API.

## Prerequisites

- Bun
- Node.js
- Docker
- PostgreSQL
- Git

## Getting Started

### Back-end

- Clone the repository (`git clone git@github.com:rodrigofontesdev/pizza-api.git`)
- Install dependencies (`bun install`)
- Copy .env.local.example file (`cp .env.local.example .env.local`)
- Update [Resend](https://resend.com) key on .env.local file (from `RESEND_API_KEY=""` to `RESEND_API_KEY="."`), it should work
- Run containers (`docker compose up -d`)
- Install migrations (`bun migrate`)
- Open the seed file (`/src/db/seed.ts`) and update the restaurant manager email to your own email
- Populate the database (`bun seed`)
- Run application (`bun dev`)

### Front-end

- Clone the repository (`git clone git@github.com:rodrigofontesdev/pizza.git`)
- Install dependencies (`npm install`)
- Copy .env.example file (`cp .env.example .env`)
- Run application (`npm run dev`)

## Features

- Create an account as restaurant manager
- Passwordless login with magic link
- Logout from account
- Update restaurant profile
- Toggle between dark and light theme
- Revenue by period
- Best-selling products
- Daily and monthly orders
- Monthly canceled orders
- Filter orders by ID, customer name or status
- Remove order filters
- Open order in details
- Manage order status
- Paginate between orders

## How to Use

### Create an account

Visit the `/sign-up` route, you must be able to create an account as a restaurant manager and sign in normally on the app. However, your dashboard will remain empty.

### Sign-in with magic link

Visit the `/sign-in` route, fill in the email address that you updated in the seed file. For now, transactional email sending is still disabled, but you can obtain the magic link in the back-end console. Open the link in your browser, and you will be automatically redirected to the dashboard.

> [!NOTE]
> See how to run the API server on the [Getting Started section](#getting-started) on this document.
> 
> I plan to activate transactional email sending using a tool other than Resend service.

### Manage orders

Visit the `/orders` route, filter orders by status or other criteria, click on the left-side icon to see the order details or click the right-side action buttons to manage the statuses.

## How to Test

In this application unit tests are built with [Vitest](https://github.com/vitest-dev/vitest), [Testing Library](https://github.com/testing-library/react-testing-library) and [Happy Dom](https://github.com/capricorn86/happy-dom). On the other hand, E2E tests are built with [Playwright](https://github.com/microsoft/playwright) and [Mock Service Worker](https://github.com/mswjs/msw).

To run the unit tests, open the front-end console and type: `npm run test`

> [!NOTE]
> Inside the tested components you can find a file with `.spec.tsx` extension, these files are located closest as possible to the target component.

To run end-to-end tests, first start the app in test mode by running `npm run dev:test` in the console. Once the app is mocked, open a new terminal and run `npx playwright test` for CI execution or `npx playwright test --ui` for the Playwright interface.

> [!NOTE]
> Inside `/src/api/mocks` you can find the mocks for the API. And inside `/test` are located the end-to-end tests.

**Environment Variables**

| Key  | Value | .ENV  | Description |
| :------------ | :------------ | :------------ | :------------ |
| VITE_API_URL | "string" (default: `http://localhost:3333`) |  | Indicates the URL from the API, in test mode should be `"/"`  |
| VITE_ENABLE_API_DELAY | `true` \| `false` |  | Enable or disable delay in the API, useful for simulating a non-local connection |
| API_BASE_URL | "string" (default: `http://localhost:3333`) | API | Indicates the base URL for the API |
| AUTH_REDIRECT_URL | "string" (default: `http://localhost:5173`) | API | Indicates the URL from the front-end application |
| DB_URL | "string" (default: `docker container`) | API | URL for connection with the database, can be any Postgres service from your machine |
| JWT_SECRET_KEY |  | API | A strong, randomly generated secret key is required for JSON Web Token security |
| RESEND_API_KEY | "string" | API | `deprecated` |

## I've Learned

- Create pre-styled components with shadcn/ui
- Provide SEO metatags with React Helmet Async
- Create a theme toggle with dark and light mode (`Context API`)
- Fetch, cache, synchronize and update server state with TanStack Query (also know as React Query)
- Differences between local state, global state and HTTP state (server state)
- Authentication with JWT Cookie approach
- How and when to use optimistic interface to improve user experience
- Create unit and end-to-end tests for the front-end
- How and why to mock an API service

## Built With

- React
- TypeScript
- shadcn/ui
- Tailwind CSS
- TanStack Query (React Query)
- Playwright
- Vitest
- Testing Library
- Mock Service Worker

## Credits

Special thanks to [@rocketseat-education](https://github.com/rocketseat-education) for contributing to the back-end. See the original [Pizza Shop API](https://github.com/rocketseat-education/pizzashop-api).

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE) file for details.

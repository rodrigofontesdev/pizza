![cover](https://github.com/user-attachments/assets/d6b16526-c4d6-4f36-ae40-46e2c9aa34d1)

# Pizza Shop

A restaurant dashboard to track metrics such as revenue by period, daily and monthly orders, best-selling products, manage orders, and much more.

The purpose of this project is to develop an application without using any framework, relying solely on React to integrate our front end with a back end via REST API.

# Prerequisites

- Bun
- Node.js
- Docker
- PostgreSQL
- Git

# Getting Started

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

# Features

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
- Paginate between the orders

# How to Use

> [!IMPORTANT]
> TODO

# I've Learned

> [!IMPORTANT]
> TODO

# Built With

> [!IMPORTANT]
> TODO

# License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE) file for details.

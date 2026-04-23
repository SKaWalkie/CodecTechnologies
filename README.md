# GoCart

A modern multi-vendor ecommerce frontend built with Next.js App Router, React, Redux Toolkit, and Tailwind CSS.

This project includes three experience layers:
- Public storefront (customers)
- Seller dashboard (store owners)
- Admin dashboard (platform admins)

The current implementation is demo-first and uses Redux state plus local dummy data for products, ratings, orders, and dashboard analytics.

## Features

- Public shopping flow
- Product listing and product detail pages
- Search in shop using query params
- Cart management with Redux Toolkit
- Address, rating, and order UI flows
- Seller dashboard with product/order/review views
- Admin dashboard with store/order/product overview
- Fully componentized UI with reusable sections

## Tech Stack

- Next.js 15 (App Router)
- React 19
- Redux Toolkit + React Redux
- Tailwind CSS 4
- Recharts (dashboard charts)
- Lucide React (icons)
- Date-fns

## Project Structure

```
app/
	(public)/      # Customer-facing pages (home, shop, cart, product, orders, etc.)
	admin/         # Admin dashboard pages
	store/         # Seller dashboard pages
components/      # Shared UI components
lib/features/    # Redux slices (cart, product, address, rating)
assets/          # Images and dummy data
prisma/          # Prisma schema (data model scaffold)
```

## Getting Started

### Prerequisites

- Node.js 20+
- npm (or pnpm/yarn)

### Installation

```bash
npm install
```

### Run Development Server

```bash
npm run dev
```

Open http://localhost:3000 in your browser.

### Build for Production

```bash
npm run build
npm run start
```

### Lint

```bash
npm run lint
```

## Environment Variables

Create a `.env.local` file in the project root.

```env
NEXT_PUBLIC_CURRENCY_SYMBOL=Rs 
```

The Prisma schema also references these variables (for backend/database integration work):

```env
DATABASE_URL=
DIRECT_URL=
```

## Available Routes

### Public

- `/`
- `/shop`
- `/shop/[username]`
- `/product/[productId]`
- `/cart`
- `/orders`
- `/create-store`
- `/pricing`

### Seller

- `/store`
- `/store/add-product`
- `/store/manage-product`
- `/store/orders`

### Admin

- `/admin`
- `/admin/approve`
- `/admin/coupons`
- `/admin/stores`

## Data & State Notes

- Product, review, and dashboard content currently comes from `assets/assets.js` dummy collections.
- Global app state is managed in Redux slices under `lib/features`.
- `product` slice is preloaded from dummy data.

## Roadmap Ideas

- Replace dummy data with real API + database-backed services
- Add authentication/authorization for customer, seller, and admin roles
- Persist cart and order history server-side
- Add testing (unit + integration + e2e)
- Add payment and shipping integrations

## Contributing

Please read `CONTRIBUTING.md` before opening pull requests.

## License

See `LICENSE.md` for license details.

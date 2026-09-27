# Visten Storefront

Storefront prototype for Visten, a small Bay Area clothing brand, built with React, Commerce.js and Stripe.

**Tech stack:** JavaScript, React 17, Create React App, React Router, Material-UI, Commerce.js (Chec headless commerce API), Stripe Elements, React Hook Form

## Features

- Product grid loaded from the Commerce.js API
- Shopping cart: add, update quantity, remove and empty, with an item count badge in the navbar
- Multi-step checkout: shipping address form with country, region and shipping option lookups, order review, and card payment through Stripe Elements
- Order capture through Commerce.js using a Stripe payment method

## How it works

A single-page React client with no custom backend. `src/lib/commerce.js` creates a Commerce.js client from a public key, `App.js` holds product, cart and order state, and React Router serves the shop (`/`), cart (`/cart`) and checkout (`/checkout`) views. At checkout, a Commerce.js checkout token is generated from the cart, Stripe Elements creates a payment method in the browser, and the order is captured with `commerce.checkout.capture`.

## Getting started

Requires Node.js and npm, a Commerce.js (Chec) account with products, and a Stripe account connected to it.

```bash
npm install
cp .env.example .env   # then fill in your public keys
npm start              # runs on http://localhost:3000
```

| Variable | Purpose |
| --- | --- |
| `REACT_APP_CHEC_PUBLIC_KEY` | Commerce.js public API key |
| `REACT_APP_STRIPE_PUBLIC_KEY` | Stripe publishable key |

## Project context

Built by Seth Carlson in August 2021 as the first storefront for Visten. The same codebase was later extended into the [Lucir storefront](https://github.com/sdcarlson/Lucir), which adds brand pages, product detail pages and a custom design.

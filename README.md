# ZUNO CARD — Sultan-inspired storefront update

## What changed
- Reworked the customer storefront into mobile-first pages inspired by the supplied Sultan Card screenshots, using ZUNO's dark navy/black and gold palette.
- Added dedicated screens for home, categories, category products, product details, app top-ups, orders, wallet, payment history, favorites, and account.
- Added date/search/status filters for the signed-in customer's orders.
- Wallet summary is calculated from the existing `wallets`, `orders`, and `deposits` data.
- Added a separate wallet/account number field to the B1 payment-method form. It is saved in the existing `payment_methods.account_details` JSON field as `wallet_number`.
- Kept B1, B2, Supabase project URL/key, existing RPC calls, storage bucket, and Vercel routes.

## Deploy
1. Extract this ZIP.
2. Replace the files in your GitHub repository with the contents of `ZUNO_CARD_SITE`.
3. Commit and push to the production branch connected to Vercel.
4. Vercel should deploy the update automatically.

## Important
- This package does not change or migrate the Supabase database.
- Existing Supabase tables/columns and RLS policies must remain available.
- The customer app still uses Supabase Auth email confirmation as configured in the Supabase project.
- Favorites are stored locally in the current browser/device; they are not synced across devices.
- App top-up products are currently displayed from the existing active `products` table. A live external top-up provider/API is not included.
- Test sign-in, purchase RPC, deposits, wallet, orders, and staff permissions on the deployed site before taking real payments.

# Mercury V1 — expanded profile & Nitro prototype

## Run
```bash
npm install
npm run dev
```

## New in this iteration
- Editable profile preview with username format validation and reserved-name checks
- Bio, pronouns, live status, emoji picker, avatar upload, banner upload
- Profile themes, settings panel, Nitro-locked effect/emoji/decoration concepts
- Animated 3D-style CSS Nitro chest and locked benefit cards
- Community concept page, expanded games catalogue, improved micro-interactions
- Responsive layout and reduced-motion accessibility support

## Important production requirements
This remains a front-end prototype. The "looks available" username check is only a local UI preview; it cannot guarantee global uniqueness. For production, enforce usernames on the server/database with a unique constraint and case-insensitive normalisation, and handle race conditions transactionally. Never rely on client-side validation for username ownership.

Use Supabase Auth (email + Google OAuth), a `profiles` table with a unique normalised username, Row Level Security, and Storage for avatar/banner images. Public live status should be controlled by privacy settings and moderation/rate limits. GIF/custom status emoji should be a Nitro entitlement verified server-side, not just hidden by the UI.

Nitro is coming soon in this prototype. No payments are accepted. Before monetisation, implement a payment provider and server-side subscription webhooks, entitlements, cancellation/refund handling, and clear pricing. Do not expose secret keys in the client.

Browser is a launchpad, not a proxy. Music requires licensed provider integration. Only list games you have permission to distribute or embed. Pinterest integration requires an authorized API and respecting image copyright and provider terms.

# Notes

## Plan
Implemented `PUT /users/:id` to update an existing user. Added an `updateUser` helper to `db/store.js` (reusing `getUserById`) and a `PUT /:id` route in `routes/users.js` that validates input before the lookup so missing fields always return 400.

## Model
Claude Sonnet 4.6 via Claude Code.

## Commit split
One logical change: store helper + route + this write-up together.

## What review caught
Validation must run before the id lookup — otherwise `PUT /users/1` with a missing field would hit the store and return 200 instead of 400.

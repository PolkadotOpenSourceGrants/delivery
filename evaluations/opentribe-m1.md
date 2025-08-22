# Evaluation

- **Status:** In Progress
- **Application Document:** https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/opentribe.md
- **Milestone:** 1

# General Notes

Grantee fixed duplicate address issue and I am now able to properly seed the test data/accounts:
```ts
cd packages/db && pnpm db:seed:auth

> @packages/db@0.0.0 db:seed:auth /home/ubuntu/opentribe/packages/db
> tsx ./seed-auth.ts

🌱 Starting database seed with Better Auth...
⚠️  Make sure the API server is running on port 3002!
✅ Cleaned existing data
📝 Creating users via Better Auth API...
  Creating user: alice.rust@example.com
  ✅ Created: alice.rust@example.com
  Creating user: bob.ui@example.com
  ✅ Created: bob.ui@example.com
  Creating user: carol.writer@example.com
  ✅ Created: carol.writer@example.com
  Creating user: david.w3f@example.com
  ✅ Created: david.w3f@example.com
  Creating user: emma.moonbeam@example.com
  ✅ Created: emma.moonbeam@example.com
  Creating user: frank.acala@example.com
  ✅ Created: frank.acala@example.com
  Creating user: admin@opentribe.io
  ✅ Created: admin@opentribe.io

✅ Created 7 users

🎉 Users seeded successfully!

📧 Test User Credentials:
- alice.rust@example.com / password123 (Builder)
- bob.ui@example.com / password123 (Builder)
- carol.writer@example.com / password123 (Builder)
- david.w3f@example.com / password123 (Org Admin - Web3 Foundation)
- emma.moonbeam@example.com / password123 (Org Admin - Moonbeam)
- frank.acala@example.com / password123 (Org Admin - Acala)
- admin@opentribe.io / admin123 (Platform Superadmin)
```
## UI

Both the web app and dasbhboard works and it looks nice so far:

<img width="1279" height="706" alt="ot0" src="https://github.com/user-attachments/assets/db2f847d-d83c-4449-b029-4792657417f7" />

<img width="1279" height="706" alt="ot1" src="https://github.com/user-attachments/assets/df4edb18-aa2b-45e6-9a1a-3df68d760018" />

<img width="1279" height="706" alt="ot2" src="https://github.com/user-attachments/assets/8844df1a-cc18-434e-8574-220781b11fc8" />

<img width="1414" height="631" alt="ot4" src="https://github.com/user-attachments/assets/8bd07adc-3c18-43dc-8935-ae7d7401e5fd" />

<img width="972" height="593" alt="ot3" src="https://github.com/user-attachments/assets/ece9a4cd-055d-4a53-a9b4-978fb358b567" />

A few errors are dealing with rate limits, happy to ignore for now but maybe check for the next milestone.

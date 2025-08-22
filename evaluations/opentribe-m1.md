# Evaluation

- **Status:** In Progress
- **Application Document:** 
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

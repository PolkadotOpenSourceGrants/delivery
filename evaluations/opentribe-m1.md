# Evaluation

- **Status:** Accepted
- **Application Document:** https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/opentribe.md
- **Milestone:** 1

| Number | Deliverable | Accepted | Link | Notes |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| 0a. | License | <ul><li>[x] </li></ul> | [MIT License](https://github.com/opentribe-dao/opentribe/blob/main/LICENSE) |  |
| 0b. | Documentation | <ul><li>[x] </li></ul> | [README](https://github.com/opentribe-dao/opentribe/blob/main/README.md)| Thorough docs |
| 0c. | Testing & Testing Guide | <ul><li>[x] </li></ul> | [Test Suite](https://github.com/opentribe-dao/opentribe/tree/main/apps/api/__tests__) | All unit tests passing |
| 0d. | Docker | <ul><li>[x] </li></ul> | [Dockerfile](https://github.com/opentribe-dao/opentribe/blob/main/Dockerfile), [docker-compose.yml](https://github.com/opentribe-dao/opentribe/blob/main/docker-compose.yml) | Complete Docker setup for running the entire stack (Next.js apps + PostgreSQL) |
 | 0e. | Article | <ul><li>[x] </li></ul> | [Blog Post](https://github.com/opentribe-dao/opentribe/blob/main/BLOG_POST.md) |  |
| 1. | Core Platform - Authentication | <ul><li>[x] </li></ul> | [Auth Package](https://github.com/opentribe-dao/opentribe/tree/main/packages/auth) | Everything working on the dev version |
| 2. | RFP Module | <ul><li>[x] </li></ul> | [RFP Routes](https://github.com/opentribe-dao/opentribe/tree/main/apps/api/app/api/v1/rfps), [RFP UI](https://github.com/opentribe-dao/opentribe/tree/main/apps/web/app/%5Blocale%5D/rfps) |  |
| 3. | Apply with RFP | <ul><li>[x] </li></ul> | [Grant Application](https://github.com/opentribe-dao/opentribe/blob/main/apps/web/app/%5Blocale%5D/grants/%5Bid%5D/apply/page.tsx) |  |
| 4. | Bounty Module | <ul><li>[x] </li></ul> | [Bounty API](https://github.com/opentribe-dao/opentribe/tree/main/apps/api/app/api/v1/bounties), [Bounty UI](https://github.com/opentribe-dao/opentribe/tree/main/apps/web/app/%5Blocale%5D/bounties) |  |
| 5. | Grants Module | <ul><li>[x] </li></ul> | [Grant Routes](https://github.com/opentribe-dao/opentribe/tree/main/apps/api/app/api/v1/grants), [Grant UI](https://github.com/opentribe-dao/opentribe/tree/main/apps/web/app/%5Blocale%5D/grants) |  |
| 6. | Organization Dashboard | <ul><li>[x] </li></ul> | [Dashboard App](https://github.com/opentribe-dao/opentribe/tree/main/apps/dashboard) |  |
| 7. | Payment Integration | <ul><li>[x] </li></ul> | [Payment Model](https://github.com/opentribe-dao/opentribe/blob/main/packages/db/prisma/schema.prisma#L344-L368) |  |
| 8. | Frontend | <ul><li>[x] </li></ul> | [Web App](https://github.com/opentribe-dao/opentribe/tree/main/apps/web), [UI Package](https://github.com/opentribe-dao/opentribe/tree/main/packages/base) |  |
| 9. | Initial Deployment | <ul><li>[x] </li></ul> | [Production Config](https://github.com/opentribe-dao/opentribe/tree/main) |  |

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

## Testing

Unit tests are now passing (w/ fixes). Please consider improving coverage for next milestone:
```ts
 RUN  v3.2.4 /home/ubuntu/opentribe/apps/api

stdout | __tests__/rfps.test.ts > RFP Flow > GET /api/v1/rfps/[id] > should return RFP details with votes and comments
Fetching RFP with ID or slug: rfp-1

 ✓ __tests__/rfps.test.ts (5 tests) 25ms
 ✓ __tests__/unit/submissions.test.ts (5 tests) 28ms
 ✓ __tests__/submissions.test.ts (5 tests) 27ms
 ✓ __tests__/unit/auth.test.ts (4 tests) 11ms
 ✓ __tests__/unit/bounties.test.ts (4 tests) 25ms
 ✓ __tests__/bounties.test.ts (4 tests) 19ms
 ✓ __tests__/auth.test.ts (4 tests) 9ms
 ✓ __tests__/basic.test.ts (5 tests) 8ms
 ✓ __tests__/health.test.ts (1 test) 8ms

 Test Files  9 passed (9)
      Tests  37 passed (37)
   Start at  17:18:53
   Duration  1.49s (transform 528ms, setup 174ms, collect 1.33s, tests 160ms, environment 3ms, prepare 955ms)
```

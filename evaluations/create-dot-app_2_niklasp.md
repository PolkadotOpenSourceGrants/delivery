# Evaluation

- **Status:** In Progres
- **Application Document:**
  https://github.com/PolkadotOpenSourceGrants/apply/pull/20
- **Milestone:** 2

| Number | Deliverable       | Accepted               | Link                                                                                                                                                                                                                                                                                                                                                  | Evaluation Notes                                        |
| ------ | ----------------- | ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------- |
| 1      | Next.js Templates | <ul><li>[ ] </li></ul> | [next-dedot](https://github.com/preschian/create-dot-app/tree/main/templates/next-dedot) & [next-papi](https://github.com/preschian/create-dot-app/tree/main/templates/next-papi)                                                                                                                                                                     | see below                                               |
| 2      | Nuxt.js Templates | <ul><li>[ ] </li></ul> | [nuxt-dedot](https://github.com/preschian/create-dot-app/tree/main/templates/nuxt-dedot) & [nuxt-papi](https://github.com/preschian/create-dot-app/tree/main/templates/nuxt-papi)                                                                                                                                                                     | see below                                               |
| 3      | Testing           | <ul><li>[x] </li></ul> | - Integration testing for CLI: [link](https://github.com/preschian/create-dot-app/blob/main/.github/workflows/cli-tests.yml) <br> - Install, lint, and build templates: [link](https://github.com/preschian/create-dot-app/blob/main/.github/workflows/package-manager.yml) <br> - Deployments: https://github.com/preschian/create-dot-app/issues/82 | see below                                               |
| 4      | Docs Landing Page | <ul><li>[x] </li></ul> | https://polkadot-dapp.vercel.app/                                                                                                                                                                                                                                                                                                                     | a landing page with minimal but sufficient instructions |
| 5      | Community Tools   | <ul><li>[x] </li></ul> | https://github.com/preschian/create-dot-app/blob/main/CONTRIBUTING.md                                                                                                                                                                                                                                                                                 | good                                                    |

# Testing

Cli Succeeds

```
no@MacBookPro:~/code/evaluate-create-dot-app/create-dot-app/cli|main ⇒  bun run test
$ vitest run

 RUN  v3.2.4 /Users/no/code/evaluate-create-dot-app/create-dot-app/cli

 ✓ __tests__/cli.e2e.test.ts (7 tests) 10402ms
   ✓ cli E2E tests with node-pty > creates project with command line argument  2807ms
   ✓ cli E2E tests with node-pty > creates project in interactive mode  2346ms
   ✓ cli E2E tests with node-pty > handles existing directory error correctly 279ms
   ✓ cli E2E tests with node-pty > can navigate template selection with arrow keys  2351ms
   ✓ cli E2E tests with node-pty > creates project with --template parameter  1258ms
   ✓ cli E2E tests with node-pty > handles invalid --template parameter correctly 59ms
   ✓ cli E2E tests with node-pty > creates project with --template parameter only (prompts for name)  1300ms

 Test Files  1 passed (1)
      Tests  7 passed (7)
   Start at  13:15:03
   Duration  10.83s (transform 26ms, setup 0ms, collect 186ms, tests 10.40s, environment 0ms, prepare 53ms)
```

Templates are build automatically

## General Notes

Thank you for submitting the final milestone of your templates. I really value
all the extra effort you made (e.g. website + solidity templates) and especially
the good community involvement in the forum. I went through the templates and
other deliverables and compiled some notes. Please fix at least the 🔴 items
before I will merge M2.

- 🟡 add a `create-dot-app` command to the readme of each template, e.g.
  https://github.com/preschian/create-dot-app/tree/main/templates/next-papi

### next-dedot

running `pnpm dlx create-dot-app@latest my-polkadot-app --template=next-dedot`
without errors.

- 🔴 subscan explorer link does not work on all networks (also addressed in m1
  delivery comment)
- 🔴 `createRemarkTransaction` only calls `unsub` when finalized, and only two
  status are handled. unsub should be called on other tx status types too.
- 🔴 `fetchBalance` in `Balance.tsx` contains a possible race condition. read
  more
- 🔴 docs page needs info on how to connect to other chains than the 4 provided
- 🟡 some dependencies are outdated. Please consider adding an automated process
  with e.g. dependabot

```
dependencies:
+ @talismn/connect-wallets 1.2.8
+ @xstate/store 3.9.2
+ dedot 0.16.0 (0.18.0 is available)
+ next 15.5.2 (15.5.4 is available)
+ react 19.1.1
+ react-dom 19.1.1
```

- 🟡 consider replacing "Funds Token" label with something like "Get Tokens"
  (all templates)
- 🟡 consider using kebab-case filenames as used in next.js generally:
  https://nextjs.org/docs/app/getting-started/server-and-client-components
- 🟡 x.com link in footer does not direct to correct domain
- 🟡 dedot supports lightclients, consider adding support
- 🟢 App works in dev and build
- 🟢 connects to 4 networks
- 🟢 allows account connections with different wallet providers
- 🟢 unsubscribes in effects
- 🟢 helper function return unsubscribe function

# next-papi

- 🟢 App works in dev and build
- 🟢 Signing transactions work
- 🟡 some dependencies are outdated. Please consider adding an automated process
  with e.g. dependabot

# nuxt-papi

- 🟢 App works in dev and build
- 🟡 some dependencies are outdated. Please consider adding an automated process
  with e.g. dependabot
- 🟡 identicons do not show on account selection window
- running `pnpm build` gives a warning

```
transforming (1) ../node_modules/.pnpm/nuxt@4.1.2_@parcel+watcher@2.5.1_@types+node@24.7.0_@vue+compiler-sfc@3.5.22_db0@0.3.4__bebf1cc9ea9147e6a175cedcd7316ea7/node_modules/nuxt/dist/app/entry.jsFound 1 warning while optimizing generated CSS:

│ }
│ @layer base {
│   @property --radialprogress {
┆            ^-- Unknown at rule: @property
┆
│     syntax: "<percentage>";
│     inherits: true;

ℹ ✓ 143 modules transformed.
```

```
dependencies:
+ @talismn/connect-wallets 1.2.8
+ @xstate/store 3.9.2
+ dedot 0.16.0 (0.18.0 is available)
+ next 15.5.2 (15.5.4 is available)
+ react 19.1.1
+ react-dom 19.1.1
```

# website https://www.createdot.app/

- 🟡 when copying the command (not with copy button) there is an extra `|` that
  will make the copied command pipe.
- 🟡 consider removing `my-polkadot-app` from the commands on the website to let
  users type the directory name
- 🟡 according to your forum post solidity templates are ready (I did not
  install and use) but add a link to the website (says coming soon)
- 🟡 consider adding adding selectors for package maners (not only npm)
- 🟡 same warning as above `Unknown at rule: @property`

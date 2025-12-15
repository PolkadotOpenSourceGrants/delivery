# Milestone Delivery :mailbox:

**The delivery is according to the official [milestone delivery guidelines](https://github.com/w3f/Grants-Program/blob/master/docs/Support%20Docs/milestone-deliverables-guidelines.md).**  

* **Application Document:** [create-dot-app](https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/create-dot-app.md)
* **Milestone Number:** 2
* **DOT Payment Address:** `162RtNYMpw3beFFpJqvjXp2GLUEf7EkwL3aRGEKkggVKc3Gq`

**Context**

This milestone expands Create Dot App's framework support by adding Next.js and Nuxt.js templates to the existing React and Vue options. Building on the CLI foundation from milestone 1, users can now scaffold full-stack applications with server-side rendering capabilities using either PAPI or Dedot SDK.

This milestone also introduces a documentation landing page, enhanced community contribution guidelines, and improved testing infrastructure. The expanded template library provides developers with more choices for building production-ready Polkadot dApps with modern meta-frameworks.

**Deliverables**

| Number | Deliverable | Link | Notes |
| ------------- | ------------- | ------------- |------------- |
| 1 | Next.js Templates | [next-dedot](https://github.com/preschian/create-dot-app/tree/main/templates/next-dedot) & [next-papi](https://github.com/preschian/create-dot-app/tree/main/templates/next-papi) | - | 
| 2 | Nuxt.js Templates | [nuxt-dedot](https://github.com/preschian/create-dot-app/tree/main/templates/nuxt-dedot) & [nuxt-papi](https://github.com/preschian/create-dot-app/tree/main/templates/nuxt-papi) | - | 
| 3 | Testing | - Integration testing for CLI: [link](https://github.com/preschian/create-dot-app/blob/main/.github/workflows/cli-tests.yml) <br> - Install, lint, and build templates: [link](https://github.com/preschian/create-dot-app/blob/main/.github/workflows/package-manager.yml) <br> - Deployments: https://github.com/preschian/create-dot-app/issues/82 | - |
| 4 | Docs Landing Page | https://polkadot-dapp.vercel.app/ | - |
| 5 | Community Tools | https://github.com/preschian/create-dot-app/blob/main/CONTRIBUTING.md | - |

**Additional Information**

**Planned Roadmap:** Future development will include:
- One-click import to CodeSandbox and Bolt for Vue and React templates from the landing page
- Solidity smart contract integration
- ink! smart contract support
- Expanded blog capability (showcase existing projects and blog posts)

# Milestone Delivery :mailbox:

**The delivery is according to the official [milestone delivery guidelines](https://github.com/w3f/Grants-Program/blob/master/docs/Support%20Docs/milestone-deliverables-guidelines.md).**  

* **Application Document:** [create-dot-app](https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/create-dot-app.md)
* **Milestone Number:** 1
* **DOT Payment Address:** `162RtNYMpw3beFFpJqvjXp2GLUEf7EkwL3aRGEKkggVKc3Gq`

**Context**

This milestone delivers the first usable version of Create Dot App, a scaffolding CLI for Polkadot dApps. It bootstraps React or Vue projects with your choice of PAPI or Dedot SDK, standardizing project structure and reducing setup time.

The CLI includes an interactive generator, a template engine, minimal telemetry with opt‑out, and CI to validate templates across package managers. This foundation enables us to add more frameworks (e.g., Next.js/Nuxt/Svelte) in the next milestones.

**Deliverables**

| Number | Deliverable | Link | Notes |
| ------------- | ------------- | ------------- |------------- |
| 0a. | License | https://github.com/preschian/create-dot-app/blob/main/LICENSE | - | 
| 0b. | Documentation | https://github.com/preschian/create-dot-app/blob/main/README.md | - | 
| 0c. | Testing | integration test for templates: https://github.com/preschian/create-dot-app/blob/main/.github/workflows/package-manager.yml | integration test for cli: https://github.com/preschian/create-dot-app/blob/main/cli/TESTING.md |
| 0d. | Repository | https://github.com/preschian/create-dot-app | - |
| 0e. | Article | https://forum.polkadot.network/t/create-dot-app-the-scaffolding-tool-for-all-your-polkadot-dapp-ideas/14297/1 | - |
| 1. | CLI Core Framework | https://github.com/preschian/create-dot-app/blob/027de303e5ed357b545c9cf28b0d7d3766ca35fa/cli/src/index.ts#L64-L72 | - |
| 2. | Template Engine | https://github.com/preschian/create-dot-app/blob/main/cli/src/template-selector.ts | - |
| 3. | React Templates | react-dedot: https://github.com/preschian/create-dot-app/tree/main/templates/react-dedot | react-papi: https://github.com/preschian/create-dot-app/tree/main/templates/react-papi |
| 4. | Vue Templates | vue-dedot: https://github.com/preschian/create-dot-app/tree/main/templates/vue-dedot | vue-papi: https://github.com/preschian/create-dot-app/tree/main/templates/vue-papi |
| 5. | NPM Package Distribution | https://github.com/preschian/create-dot-app/blob/main/.github/workflows/release.yml | https://www.npmjs.com/package/create-dot-app?activeTab=readme |

**Additional Information**

Collaboration: Plan to work with Parity to add “community templates” as a CLI option. https://forum.polkadot.network/t/create-dot-app-the-scaffolding-tool-for-all-your-polkadot-dapp-ideas/14297/4?u=0xpresc

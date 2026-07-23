# GUI Evidence Standard

This standard applies whenever a repository contains a graphical interface, website, desktop application, mobile interface, dashboard, or other visual workflow.

## Purpose

A GUI is not adequately documented by prose alone. Visual evidence must show what was built, how it behaves, and whether the implementation still matches the declared architecture.

## Required screenshot set

A mature GUI repository should maintain **five to seven current screenshots** that collectively show the essential user journey.

Recommended sequence:

1. Entry, landing, login, or initial state
2. Primary workspace or dashboard
3. Main task flow
4. Important secondary capability
5. Settings, governance, or configuration view
6. Error, empty, permission, or recovery state
7. Completed result or confirmation state

Use fewer only when the product genuinely has fewer meaningful states. Do not manufacture repetitive screenshots merely to reach a number.

## Capture requirements

Each screenshot must have:

- a stable filename;
- a descriptive caption;
- the feature or flow represented;
- the environment and version captured;
- sensitive information removed;
- readable dimensions;
- a record of when it was captured;
- a link to the related requirement, feature, issue, or test when available.

Recommended location:

```text
assets/screenshots/
  01-entry.png
  02-dashboard.png
  03-primary-flow.png
  04-secondary-capability.png
  05-settings.png
  06-error-state.png
  07-completed-result.png
```

## README presentation

The README should contain a Visual Tour section near the architecture and usage sections.

```markdown
## Visual Tour

| View | Purpose |
|---|---|
| ![Dashboard](assets/screenshots/02-dashboard.png) | Shows the primary operating workspace. |
| ![Primary flow](assets/screenshots/03-primary-flow.png) | Shows the main user task. |
```

Large screenshots may be grouped with HTML `<details>` elements to keep the README usable.

## Automation standard

When the project supports browser or GUI automation, the repository should provide a reproducible capture workflow using an appropriate tool such as Playwright, a platform-native UI test framework, or another deterministic screenshot runner.

The capture job should:

1. launch a controlled build;
2. seed known data;
3. navigate to declared states;
4. set a consistent viewport;
5. capture the required screens;
6. fail when a target state cannot be reached;
7. record the application version or commit.

Generated screenshots must still be reviewed for correctness and sensitive data.

## Visual regression

Where practical, key screens should have visual regression checks. A changed screenshot is evidence for review, not automatic proof that the change is wrong.

## Live preview and embedded web experience

A Git repository should not depend on executing an arbitrary React or JavaScript application directly inside the README. Instead, use one or more of these patterns:

- a deployment link to a controlled preview environment;
- GitHub Pages for static sites and documentation;
- a Storybook or component explorer deployment;
- recorded GIF or short demonstration media;
- architecture diagrams and screenshots stored in the repository;
- a local `make preview`, `npm run dev`, or equivalent command.

The README must clearly distinguish:

- source code;
- local development instructions;
- deployed preview;
- production deployment;
- screenshots captured from a specific version.

## Drift policy

Screenshots are evidence and therefore must be maintained.

A screenshot is stale when:

- the represented interface materially changed;
- the related feature no longer exists;
- the image shows an older information architecture;
- captions no longer describe the current behavior;
- the screenshot cannot be reproduced from the documented workflow.

When drift is detected, the steward shall update the image or create an explicit maintenance task. It must not silently leave obsolete evidence presented as current.

## Trust and business mapping

| Trust model | Business model | GUI standard role |
|---|---|---|
| Property inspection photographs | Product evidence | Screenshots prove the current condition of the interface |
| Trust ledger entry | QA record | Metadata connects the screenshot to a version and requirement |
| Managing trustee inspection | Product review | A reviewer verifies that evidence matches declared work |
| Contractor completion photographs | Delivery proof | Final-state screenshots support completion claims |

## Completion criteria

A GUI feature is documentation-complete when:

- its primary visible state is represented;
- the screenshot is current and readable;
- the related flow is described;
- sensitive information is absent;
- the capture is reproducible where practical;
- the evidence is linked to the implementation or requirement.

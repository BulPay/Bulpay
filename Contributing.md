# Contributing to Bulpay

Thank you for your interest in contributing to Bulpay!

Bulpay is an open-source platform for freelance contracts, milestone-based payments, escrow, and recurring payroll using stablecoins on the Stellar network.

We welcome contributions from developers, testers, designers, technical writers, and anyone who wants to help make payments more transparent and reliable.

Whether you are fixing a bug, improving documentation, adding tests, or building a feature, your contribution is valuable.

## Table of Contents

- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Finding Something to Work On](#finding-something-to-work-on)
- [Reporting Bugs](#reporting-bugs)
- [Proposing Features](#proposing-features)
- [Making Changes](#making-changes)
- [Testing Your Changes](#testing-your-changes)
- [Submitting a Pull Request](#submitting-a-pull-request)
- [Code Guidelines](#code-guidelines)
- [Security Considerations](#security-considerations)
- [Community Expectations](#community-expectations)

## Getting Started

Before contributing, please:

1. Read the project's README and relevant technical documentation.
2. Check the existing issues and pull requests to avoid duplicating work.
3. Choose an issue that matches your experience and available time.
4. Ask questions in the issue's comment section if anything is unclear.
5. Wait for maintainer guidance or assignment when an issue requires coordination.

If you are new to the project, look for issues labelled `good first issue` or `help wanted`.

If an issue has not been labelled, you can ask a maintainer whether it is suitable for a first contribution.

## Development Setup

### Prerequisites

Bulpay uses a TypeScript-based application stack with backend, frontend, database, and Stellar integrations.

Depending on the part of the project you are working on, you may need:

- Git
- Node.js
- Bun, if required by the repository's package manager configuration
- PostgreSQL
- A package manager compatible with the repository's lockfile
- Access to Stellar Testnet for blockchain-related development

Use the versions specified by the repository's configuration and documentation.

### 1. Fork the repository

Fork the repository on GitHub:

https://github.com/BulPay/Bulpay

Clone your fork:

```bash
git clone https://github.com/YOUR_USERNAME/Bulpay.git
cd Bulpay
```

Add the original repository as an upstream remote:

```bash
git remote add upstream https://github.com/BulPay/Bulpay.git
```

### 2. Install dependencies

Check the root directory for the package manager configuration and lockfile. Follow the commands documented in the README.

If the repository uses Bun:

```bash
bun install
```

Do not introduce a second lockfile or change the package manager without discussing it with a maintainer.

### 3. Configure environment variables

Check the relevant application's environment example files and documentation.

Create your local environment configuration from the appropriate example file.

For example, if an application provides an `.env.example` file:

```bash
cp .env.example .env
```

The example above applies only when that file exists in the directory where you run the command.

Configure the required database and service settings using local development credentials.

**Never commit secrets, private keys, seed phrases, API tokens, passwords, or production environment files.**

### 4. Set up the database

Follow the project's documented PostgreSQL and Prisma setup instructions.

Run the appropriate database migration and seed commands defined by the repository.

Do not run migrations against a production database or use production payment credentials for local development.

### 5. Start the application

Follow the development commands documented in the README and the relevant application package.

Bulpay includes backend and frontend components. Some features may also depend on external services or Stellar Testnet.

If setup fails, check the existing issues before opening a new one. When reporting a setup problem, include the command you ran, the relevant error message, and your runtime versions. Remove any secrets or sensitive information before sharing logs.

## Finding Something to Work On

Browse the project's open issues:

https://github.com/BulPay/Bulpay/issues

Issues may cover:

- Backend APIs and business logic
- Frontend features and user experience
- Stellar integration and transaction handling
- Escrow and milestone workflows
- Payroll and payment reliability
- Automated testing and quality assurance
- Documentation and developer experience
- Performance, accessibility, and security improvements

Before starting work, read the entire issue and its acceptance criteria.

If you want to work on an issue, leave a comment expressing your interest and briefly explain how you plan to approach it.

Please avoid starting substantial work on an issue that is already assigned or actively being implemented by someone else.

## Reporting Bugs

Before reporting a bug, search the existing issues to see whether it has already been reported.

When opening a bug report, include:

- A clear and descriptive title
- The affected feature or application component
- The steps required to reproduce the problem
- The expected behaviour
- The actual behaviour
- Relevant error messages or sanitized logs
- Your operating system and relevant runtime versions
- Screenshots or a short recording, where helpful

For payment-related bugs, use local mocks or Stellar Testnet whenever possible.

Never include real customer data, account credentials, private keys, seed phrases, or other sensitive information in an issue.

## Proposing Features

We welcome proposals that improve Bulpay's usability, reliability, security, and functionality.

Before implementing a major feature:

1. Search for related issues and existing functionality.
2. Open an issue describing the problem you want to solve.
3. Explain your proposed solution and any alternatives.
4. Identify affected components and potential compatibility concerns.
5. Wait for maintainer feedback before beginning substantial implementation.

Small, clearly scoped improvements may not require a separate proposal, but please check with a maintainer when in doubt.

## Making Changes

### 1. Create a branch

Use a descriptive branch name:

```bash
git checkout -b fix/describe-the-issue
```

Other examples:

```bash
git checkout -b feat/milestone-validation
git checkout -b test/escrow-lifecycle
git checkout -b docs/local-setup
```

### 2. Keep changes focused

- Work on one issue or closely related set of changes at a time.
- Follow the existing project architecture and coding conventions.
- Avoid unrelated refactoring.
- Update documentation when behaviour or setup instructions change.
- Add or update tests when modifying application logic.
- Do not commit generated files, local environment files, or unrelated changes.

If your work requires a significant architectural change, discuss it with a maintainer first.

### 3. Write clear commit messages

Use concise commit messages that describe the change.

Examples:

```text
fix: validate milestone release requests
test: cover escrow failure scenarios
docs: clarify local development setup
feat: improve payroll error handling
```

These are examples of the preferred style, not a requirement to rewrite existing commit history.

## Testing Your Changes

Run the relevant checks before submitting a pull request.

Depending on the changes, these may include:

- Unit tests
- Integration tests
- Frontend tests
- TypeScript type-checking
- Linting and formatting checks
- Production builds
- Database migration validation
- Stellar Testnet integration tests

Use the scripts defined in the relevant `package.json` files and follow the repository's documented commands.

For payment-related functionality, test both successful and unsuccessful scenarios where applicable.

Examples include:

- Invalid inputs and unauthorized requests
- Failed or delayed transactions
- Duplicate requests and retry behaviour
- Milestone approval and release
- Refunds and dispute resolution
- Partial payroll failures

Do not claim a test passed if you have not run it. If a check cannot be completed, explain why in your pull request.

## Submitting a Pull Request

When your changes are ready:

1. Commit your changes.
2. Push your branch to your fork.
3. Open a pull request against the original repository's default branch.
4. Link the issue your changes address.
5. Describe what changed and why.
6. List the tests you ran and their results.
7. Include screenshots or recordings for relevant user-interface changes.
8. Mention any known limitations or follow-up work.

A useful pull request description should answer:

- What problem does this solve?
- What changes were made?
- How can the changes be tested?
- Are there any risks, limitations, or migration requirements?

Keep pull requests focused and reasonably small. Large changes may need to be split into smaller, reviewable contributions.

Maintainers may request revisions before merging. Please respond to review feedback constructively and update your branch as needed.

Submitting a pull request does not guarantee that it will be merged. Changes must meet the project's quality, compatibility, and security expectations.

## Code Guidelines

### General

- Prefer clear, readable, maintainable code.
- Follow established naming conventions and existing project patterns.
- Use TypeScript types appropriately.
- Handle errors explicitly.
- Validate untrusted input at appropriate boundaries.
- Avoid unnecessary dependencies.
- Document non-obvious decisions where useful.

### Backend

- Keep business logic and API responsibilities appropriately separated.
- Validate incoming requests.
- Apply authentication and authorization checks where required.
- Handle database errors and external service failures safely.
- Avoid exposing internal errors or sensitive information to clients.

### Frontend

- Follow existing React and TypeScript conventions.
- Provide appropriate loading, success, empty, and error states.
- Validate user input and communicate errors clearly.
- Consider accessibility and responsive layouts.
- Avoid exposing sensitive configuration in client-side code.

### Stellar and Payments

- Use Stellar Testnet for development and integration testing where appropriate.
- Validate network and asset configuration.
- Handle transaction submission and confirmation as distinct states where applicable.
- Account for failed, delayed, and repeated requests.
- Never expose secret keys or seed phrases.
- Do not introduce payment logic that assumes a transaction succeeded merely because a request was submitted.
- Preserve authorization and escrow invariants when changing payment-related code.

## Security Considerations

Security issues should not be reported publicly if doing so could expose users, funds, credentials, or exploitable vulnerabilities.

Please use the repository's designated private security reporting channel if one is configured. If no private reporting channel exists, contact a repository maintainer privately to request a secure reporting method.

Do not include exploit instructions, private keys, customer data, or credentials in public issues or pull requests.

All security-related contributions must be reviewed carefully before merging.

## Community Expectations

We aim to maintain a welcoming and collaborative environment for contributors of all experience levels.

Please:

- Be respectful and constructive.
- Ask questions when requirements are unclear.
- Give useful context when requesting help.
- Respect other contributors' time and work.
- Accept technical feedback in good faith.
- Avoid claiming work that you have not completed.
- Follow the project's Code of Conduct when one is published.

Contributions should be genuine, independently understood, and submitted in accordance with the project's guidelines.

## Questions?

If you are unsure where to start, browse the repository's issues or open a discussion with the maintainers.

Repository: https://github.com/BulPay/Bulpay

Issues: https://github.com/BulPay/Bulpay/issues

Thank you for helping improve Bulpay and the open-source Stellar ecosystem!

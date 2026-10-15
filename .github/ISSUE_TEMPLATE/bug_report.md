name: 🐛 Bug Report
description: Report a reproducible bug in KTestify
title: "[Bug]: "
labels: ["bug", "triage"]

body:
- type: markdown
  attributes:
  value: |
  Thanks for taking the time to fill this in! 🙏
  The more specific you are, the faster we can reproduce and fix the issue.
  Have a question rather than a bug? Please ask in [Discussions](https://github.com/orgs/ktestify/discussions) instead.

- type: checkboxes
  id: preflight
  attributes:
  label: Pre-flight checklist
  options:
  - label: I searched [existing issues](https://github.com/search?q=org%3Aktestify&type=issues) and this is not a duplicate.
  required: true
  - label: I checked the [documentation](https://docs.ktestify.xyz).
  required: true
  - label: I can reproduce this on the latest released version.
  required: false

- type: dropdown
  id: module
  attributes:
  label: Affected module
  description: Where does the bug show up? Pick the closest match.
  multiple: true
  options:
  - ktestify-core
  - ktestify-cucumber
  - ktestify-plugin-notifications
  - ktestify-plugin-azureblob
  - ktestify-plugin-http
  - ktestify-plugin-archetype
  - ktestify-parent
  - Not sure
  validations:
  required: true

- type: dropdown
  id: usage
  attributes:
  label: How are you running KTestify?
  options:
  - Java API (ktestify-core in my own tests)
  - Cucumber runner via Maven
  - Cucumber runner as a fat JAR
  - Other
  validations:
  required: true

- type: textarea
  id: description
  attributes:
  label: Bug description
  description: A clear and concise description of what the bug is.
  placeholder: "When I run a scenario with … I get … instead of …"
  validations:
  required: true

- type: textarea
  id: reproduction
  attributes:
  label: Steps to reproduce
  description: A minimal, complete example. A small repository or a single failing scenario is ideal.
  placeholder: |
  1. Configure KTestify with …
  2. Produce a record with …
  3. Assert it with …
  4. See the error …
  validations:
  required: true

- type: textarea
  id: scenario
  attributes:
  label: Feature file or test code
  description: The scenario or Java test that triggers the bug, trimmed to the minimum.
  render: gherkin

- type: textarea
  id: expected
  attributes:
  label: Expected behaviour
  description: What should have happened?
  validations:
  required: true

- type: textarea
  id: actual
  attributes:
  label: Actual behaviour
  description: What actually happened?
  validations:
  required: true

- type: textarea
  id: logs
  attributes:
  label: Logs and stack trace
  description: Paste the full stack trace and relevant logs. This is formatted as code automatically.
  render: text

- type: input
  id: ktestify-version
  attributes:
  label: KTestify version
  description: Version of the affected module(s).
  placeholder: "e.g. ktestify-cucumber 0.1.4"
  validations:
  required: true

- type: input
  id: java-version
  attributes:
  label: Java version
  placeholder: "e.g. Java 25.0.1 (Temurin)"
  validations:
  required: true

- type: input
  id: kafka-version
  attributes:
  label: Kafka / Confluent version
  placeholder: "e.g. Kafka 4.1, Confluent Platform 8.0, Schema Registry 8.0"

- type: textarea
  id: config
  attributes:
  label: Configuration
  description: Relevant `application.conf` snippet and `KTESTIFY_*` environment variables. **Remove credentials, tokens and webhook URLs.**
  render: hocon

- type: textarea
  id: environment
  attributes:
  label: Environment
  description: OS, Docker / Testcontainers version, CI provider, anything else that might matter.
  placeholder: "e.g. Ubuntu 24.04, Docker 27.3, GitHub Actions"
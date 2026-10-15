name: 🧩 Plugin Request
description: Suggest a new plugin, e.g. support for another transport or system
title: "[Plugin]: "
labels: ["plugin", "enhancement", "triage"]

body:
- type: markdown
  attributes:
  value: |
  KTestify can be extended through plugins discovered via SPI, without touching the core.
  Use this form to suggest a new first-party plugin or to share one you are building.
  Building your own? The [plugin guide](https://docs.ktestify.xyz/docs/extend/plugins) and the
  [plugin archetype](https://github.com/ktestify/ktestify-plugin-archetype) will get you started.

- type: checkboxes
  id: preflight
  attributes:
  label: Pre-flight checklist
  options:
  - label: I searched [existing issues](https://github.com/search?q=org%3Aktestify&type=issues) and this plugin has not been requested yet.
  required: true

- type: input
  id: system
  attributes:
  label: Target system
  description: What should the plugin talk to?
  placeholder: "e.g. IBM MQ, SFTP, PostgreSQL, Amazon S3, RabbitMQ"
  validations:
  required: true

- type: textarea
  id: use-case
  attributes:
  label: Use case
  description: What does your pipeline look like, and what do you need to send or assert on that system?
  placeholder: "Our stream writes enriched orders to … and we need to check that …"
  validations:
  required: true

- type: dropdown
  id: capabilities
  attributes:
  label: Capabilities needed
  multiple: true
  options:
  - Send / upload data
  - Read and assert data
  - Negative checks (data must NOT appear)
  - Setup / teardown (create queues, buckets, tables…)
  - Local emulator or Testcontainers support
  - Other
  validations:
  required: true

- type: textarea
  id: steps
  attributes:
  label: Example Gherkin steps
  description: How would you like to write the scenario? Pseudo-steps are fine.
  render: gherkin
  placeholder: |
  When file is uploaded to SFTP
  | path            | file            |
  | /inbox/orders   | data/order.csv  |
  Then expected file on SFTP
  | path            | file                 |
  | /outbox/orders  | expected/order.csv   |

- type: textarea
  id: auth
  attributes:
  label: Authentication and configuration
  description: How do you connect to this system (connection string, user/password, keys, managed identity…)?

- type: checkboxes
  id: contribution
  attributes:
  label: Contribution
  options:
  - label: I'm building (or willing to build) this plugin myself.
  required: false
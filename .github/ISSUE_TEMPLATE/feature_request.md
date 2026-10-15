name: ✨ Feature Request
description: Propose a new feature or improvement for KTestify
title: "[Feature]: "
labels: ["enhancement", "triage"]

body:
- type: markdown
  attributes:
  value: |
  Thanks for helping shape KTestify! 💡
  Want support for a new transport or system (MQ, database, cloud storage…)? Use the **Plugin request** template instead.

- type: checkboxes
  id: preflight
  attributes:
  label: Pre-flight checklist
  options:
  - label: I searched [existing issues](https://github.com/search?q=org%3Aktestify&type=issues) and this has not been requested yet.
  required: true

- type: textarea
  id: problem
  attributes:
  label: Problem statement
  description: What are you trying to test or do, and what gets in the way today?
  placeholder: "When I test … I have to … because KTestify can't …"
  validations:
  required: true

- type: textarea
  id: solution
  attributes:
  label: Proposed solution
  description: Describe the feature you would like to see.
  validations:
  required: true

- type: dropdown
  id: area
  attributes:
  label: Affected area
  multiple: true
  options:
  - Producer API
  - Consumer API
  - Kafka Streams topology testing
  - Avro / Schema Registry
  - Record matchers / assertions
  - Dynamic variables
  - Configuration (HOCON)
  - Gherkin steps (ktestify-cucumber)
  - Reports / notifications
  - Plugin system (SPI)
  - Documentation
  - CI / build
  - Other
  validations:
  required: true

- type: textarea
  id: example
  attributes:
  label: Example usage
  description: |
  What should it look like? A Java API sketch or a Gherkin scenario both work, pseudo-code is fine.
  placeholder: |
  Then expected record matching JSONPath
  | topicAlias | jsonPath        | expectedValue |
  | orders-out | $.order.status  | CONFIRMED     |

- type: textarea
  id: alternatives
  attributes:
  label: Alternatives considered
  description: Workarounds you use today or other approaches you thought about.

- type: checkboxes
  id: contribution
  attributes:
  label: Contribution
  options:
  - label: I'd be willing to open a pull request for this.
  required: false

- type: textarea
  id: additional
  attributes:
  label: Additional context
  description: Links, related issues or PRs, anything else.
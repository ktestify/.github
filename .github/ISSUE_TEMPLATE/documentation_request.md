name: 📖 Documentation
description: Report missing, unclear or wrong documentation
title: "[Docs]: "
labels: ["documentation"]

body:
- type: input
  id: page
  attributes:
  label: Page
  description: Link to the page (or README / Javadoc) the issue is about.
  placeholder: "https://docs.ktestify.xyz/docs/…"
  validations:
  required: true

- type: dropdown
  id: kind
  attributes:
  label: What kind of issue is it?
  options:
  - Something is wrong or outdated
  - Something is missing
  - Something is unclear
  - Typo or broken link
  validations:
  required: true

- type: textarea
  id: description
  attributes:
  label: Description
  description: What's the problem, and what were you trying to do when you hit it?
  validations:
  required: true

- type: textarea
  id: suggestion
  attributes:
  label: Suggested fix
  description: Optional. How should it read instead?

- type: checkboxes
  id: contribution
  attributes:
  label: Contribution
  options:
  - label: I'd be willing to open a pull request on [ktestify-doc](https://github.com/ktestify/ktestify-doc).
  required: false
name: Bug Report
description: Report a problem with a script or note in KK4TSS-Shack
title: "[BUG] "
labels: ["bug"]
assignees: []

body:
  - type: markdown
    attributes:
      value: "## Thanks for reporting a bug!\nPlease fill out the details below so I can reproduce it."

  - type: input
    id: system
    attributes:
      label: System Info
      description: "What OS or environment are you running this in? (e.g., Raspberry Pi OS, Ubuntu 22.04, Windows WSL)"
      placeholder: "O/S"
    validations:
      required: true

  - type: textarea
    id: steps
    attributes:
      label: Steps to Reproduce
      description: "Tell me exactly how to trigger this bug. Step by step."
      value: |
        1. 
        2. 
        3. 
      render: bash
    validations:
      required: true

  - type: textarea
    id: expected
    attributes:
      label: Expected Behavior
      description: "What should have happened?"
      placeholder: "The update script should finish without errors."
    validations:
      required: true

  - type: textarea
    id: actual
    attributes:
      label: Actual Behavior
      description: "What actually happened? Include error messages if you saw any."
      placeholder: "Got error: unable to locate package"
    validations:
      required: true

  - type: textarea
    id: additional
    attributes:
      label: Additional Context
      description: "Anything else I should know? Screenshots, logs, etc."

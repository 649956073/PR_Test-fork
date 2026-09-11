name: Issue Report
description: 问题上报
title: "[问题]: "
body:
  - type: dropdown
    id: issue-type
    attributes:
      label: 问题类型
      options:
        - Bug
        - Feature Request
        - Documentation
    validations:
      required: true
  
  - type: textarea
    id: bug-details
    attributes:
      label: Bug 详情
      description: 请描述 Bug 的症状
    when: ${{ github.event.issue.issue_type == 'Bug' }}
  
  - type: textarea
    id: feature-description
    attributes:
      label: 功能描述
      description: 请描述您想要的功能
    when: ${{ github.event.issue.issue_type == 'Feature Request' }}

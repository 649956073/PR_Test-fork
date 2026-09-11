name: 🐛 Bug 报告
description: 报告一个 Bug 或问题
title: "[Bug] "
labels: ["bug", "待分类"]
assignees: []

body:
  - type: markdown
    attributes:
      value: |
        感谢您的反馈！请详细填写以下信息，帮助我们快速定位问题。

  - type: input
    id: version
    attributes:
      label: 软件版本
      description: 您使用的软件版本是什么？
      placeholder: "v1.0.0"
    validations:
      required: true

  - type: dropdown
    id: bug-type
    attributes:
      label: Bug 类型（请选择）
      description: 请选择 Bug 的类型，下方会显示对应的输入项
      options:
        - 功能问题
        - 性能问题
        - UI/显示问题
        - 崩溃/错误
    validations:
      required: true

  # ==================== 功能问题 ====================
  - type: markdown
    attributes:
      value: |
        ### 📋 功能问题详情
        请填写以下信息

  - type: dropdown
    id: feature-affected
    attributes:
      label: "【功能问题】受影响的功能模块"
      description: 选择受影响的功能模块
      options:
        - 用户认证
        - 数据导入/导出
        - 搜索功能
        - 报表生成
        - API 接口
        - 其他
    validations:
      required: false

  - type: textarea
    id: feature-expected
    attributes:
      label: "【功能问题】预期行为"
      description: 这个功能应该做什么？
      placeholder: |
        预期该功能应该：
        1. ...
        2. ...
    validations:
      required: false

  - type: textarea
    id: feature-actual
    attributes:
      label: "【功能问题】实际行为"
      description: 实际发生了什么？
      placeholder: |
        实际表现：
        1. ...
        2. ...
    validations:
      required: false

  # ==================== 性能问题 ====================
  - type: markdown
    attributes:
      value: |
        ### ⚡ 性能问题详情
        请填写以下信息

  - type: dropdown
    id: performance-type
    attributes:
      label: "【性能问题】问题类型"
      description: 具体是什么性能问题？
      options:
        - 响应缓慢
        - 高 CPU 占用
        - 高内存占用
        - 网络超时
        - 数据库查询缓慢
        - 其他
    validations:
      required: false

  - type: textarea
    id: performance-baseline
    attributes:
      label: "【性能问题】基准数据"
      description: 正常情况下的性能表现
      placeholder: |
        正常情况：
        - 响应时间：XXms
        - CPU 占用：XX%
        - 内存占用：XXMb
    validations:
      required: false

  - type: textarea
    id: performance-current
    attributes:
      label: "【性能问题】当前表现"
      description: 现在的性能表现
      placeholder: |
        当前情况：
        - 响应时间：XXms
        - CPU 占用：XX%
        - 内存占用：XXMb
    validations:
      required: false

  - type: textarea
    id: performance-reproduce
    attributes:
      label: "【性能问题】复现场景"
      description: 如何复现该性能问题？
      placeholder: |
        1. ...
        2. ...
        3. ...
    validations:
      required: false

  # ==================== UI 问题 ====================
  - type: markdown
    attributes:
      value: |
        ### 🎨 UI/显示问题详情
        请填写以下信息

  - type: dropdown
    id: ui-device
    attributes:
      label: "【UI问题】设备/浏览器"
      description: 问题出现在什么设备或浏览器上？
      options:
        - Chrome 浏览器
        - Firefox 浏览器
        - Safari 浏览器
        - Edge 浏览器
        - 移动端（iOS）
        - 移动端（Android）
        - 桌面应用
        - 其他
    validations:
      required: false

  - type: input
    id: ui-resolution
    attributes:
      label: "【UI问题】分辨率/屏幕尺寸"
      description: 例如：1920x1080，或设备名称
      placeholder: "1920x1080"
    validations:
      required: false

  - type: textarea
    id: ui-description
    attributes:
      label: "【UI问题】显示问题描述"
      description: UI 显示有什么问题？
      placeholder: |
        问题描述：
        - 显示不正确
        - 排版错乱
        - 缺失内容
        - 颜色异常
    validations:
      required: false

  - type: textarea
    id: ui-screenshot
    attributes:
      label: "【UI问题】截图或录屏"
      description: 请贴上问题的截图或视频链接
      placeholder: "粘贴截图链接或视频链接"
    validations:
      required: false

  # ==================== 崩溃/错误 ====================
  - type: markdown
    attributes:
      value: |
        ### 💥 崩溃/错误详情
        请填写以下信息

  - type: dropdown
    id: crash-type
    attributes:
      label: "【崩溃】错误类型"
      description: 具体是什么类型的错误？
      options:
        - 应用崩溃
        - 页面崩溃
        - 功能卡死
        - 异常抛出
        - 连接中断
        - 其他
    validations:
      required: false

  - type: textarea
    id: crash-error
    attributes:
      label: "【崩溃】错误信息或堆栈跟踪"
      description: 完整的错误日志或堆栈跟踪
      placeholder: |
        Error: ...
        at ...
        Stack trace:
      render: logs
    validations:
      required: false

  - type: textarea
    id: crash-reproduce
    attributes:
      label: "【崩溃】复现步骤"
      description: 如何复现这个错误？
      placeholder: |
        1. 打开...
        2. 点击...
        3. 等待...
    validations:
      required: false

  - type: textarea
    id: crash-logs
    attributes:
      label: "【崩溃】相关日志文件"
      description: 粘贴完整的日志文件或链接
      placeholder: "粘贴日志内容..."
      render: logs
    validations:
      required: false

  # ==================== 通用字段 ====================
  - type: markdown
    attributes:
      value: |
        ### 📎 通用信息

  - type: dropdown
    id: os
    attributes:
      label: 操作系统/环境
      description: 问题发生在什么环境？
      options:
        - Windows 10
        - Windows 11
        - macOS
        - Linux
        - Docker
        - 云环境
        - 其他
    validations:
      required: true

  - type: textarea
    id: additional
    attributes:
      label: 附加信息
      description: 其他可能有帮助的信息
      placeholder: |
        - 相关的日志文件
        - 环境变量
        - 配置信息
        - 其他上下文

  - type: markdown
    attributes:
      value: |
        ---
        **提示：** 根据您选择的 Bug 类型，请重点填写对应的字段。这样能帮助我们更快速地定位和解决问题。谢谢！

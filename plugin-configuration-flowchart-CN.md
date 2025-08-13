# 📊 插件配置流程图

[English](./plugin-configuration-flowchart-EN.md) | **中文**

## 🔄 详细配置流程

```mermaid
flowchart TD
    Start([🚀 开始]):::startClass --> Prepare[📋 准备工作]:::prepClass
    Prepare --> EOA[🔑 提供 EOA 地址给 AlphaLabs]:::prepClass
    
    EOA --> Verify{✅ 邀请验证}:::decisionClass
    Verify -->|❌ 未通过| Denied([🚫 拒绝访问]):::errorClass
    Verify -->|✅ 通过| Deposit[💰 充值资金到平台]:::actionClass
    
    Deposit --> GetKey[📨 接收 Refer Code]:::actionClass
    GetKey --> Activate[🔓 激活 API Key]:::actionClass
    
    Activate --> Config[⚙️ 配置插件]:::configClass
    Config --> ConfigAPI[1️⃣ 填写 API Key]:::configClass
    ConfigAPI --> ConfigParam[2️⃣ 设置策略参数]:::configClass
    
    ConfigParam --> LoginEdge[🌐 登录 edgeX 平台]:::platformClass
    LoginEdge --> LoginVar[🌐 登录 Variational 平台]:::platformClass
    
    LoginVar --> CheckTrade{💹 检查交易能力}:::decisionClass
    CheckTrade -->|❌ 未就绪| Refresh[🔄 刷新两个平台]:::warningClass
    Refresh --> CheckTrade
    CheckTrade -->|✅ 就绪| Launch[🎯 点击启动策略]:::launchClass
    
    Launch --> Running([✨ 策略运行中]):::successClass
    Running --> Monitor[📈 监控运行状态]:::monitorClass
    Monitor -->|⚠️ 异常| Fix[🔧 修复问题]:::warningClass
    Fix --> Launch
    Monitor -->|✅ 正常| Running
    
    classDef startClass fill:#E8F5E9,stroke:#4CAF50,stroke-width:2px,color:#1B5E20
    classDef prepClass fill:#E3F2FD,stroke:#2196F3,stroke-width:2px,color:#0D47A1
    classDef actionClass fill:#E1F5FE,stroke:#03A9F4,stroke-width:2px,color:#01579B
    classDef configClass fill:#F3E5F5,stroke:#9C27B0,stroke-width:2px,color:#4A148C
    classDef platformClass fill:#FFF3E0,stroke:#FF9800,stroke-width:2px,color:#E65100
    classDef decisionClass fill:#FFFDE7,stroke:#FBC02D,stroke-width:2px,color:#F57F17
    classDef launchClass fill:#DCEDC8,stroke:#689F38,stroke-width:2px,color:#33691E
    classDef successClass fill:#C8E6C9,stroke:#4CAF50,stroke-width:3px,color:#1B5E20
    classDef monitorClass fill:#E0F2F1,stroke:#009688,stroke-width:2px,color:#004D40
    classDef warningClass fill:#FBE9E7,stroke:#FF5722,stroke-width:2px,color:#BF360C
    classDef errorClass fill:#FFEBEE,stroke:#F44336,stroke-width:3px,color:#B71C1C
```

## 📝 步骤详解

### 1️⃣ 准备阶段
- 确保有 AlphaLabs 邀请链接
- 准备好 EOA 钱包地址
- 准备充值资金

### 2️⃣ 验证激活
- 提交 EOA 地址进行邀请验证
- 验证通过后充值资金
- 获取并激活 API Key

### 3️⃣ 插件配置
- 在插件中输入 API Key
- 根据社区说明设置策略参数
- 保存配置信息

### 4️⃣ 平台准备
- 使用浏览器登录 edgeX
- 使用浏览器登录 Variational
- 确保两个平台都显示可交易状态
- 必要时刷新页面

### 5️⃣ 启动运行
- 点击"启动策略"按钮
- 监控初始运行状态
- 确认策略正常运行

## ⚠️ 注意事项

- 🔐 **安全提醒**：妥善保管 API Key，不要分享给他人
- 💡 **最佳实践**：两个平台使用相同的 EOA 地址
- 📊 **监控建议**：定期检查策略运行状态
- 🛠️ **故障处理**：遇到问题先检查配置，再联系社区支持
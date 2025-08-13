# 📊 Plugin Configuration Flowchart

**English** | [中文](./plugin-configuration-flowchart-CN.md)

## 🔄 Detailed Configuration Flow

```mermaid
flowchart TD
    Start([🚀 Start]):::startClass --> Prepare[📋 Preparation]:::prepClass
    Prepare --> EOA[🔑 Provide EOA Address and FW token to AlphaLabs]:::prepClass
    
    EOA --> Verify{✅ Invitation Verification}:::decisionClass
    Verify -->|❌ Rejected| Denied([🚫 Access Denied]):::errorClass
    Verify -->|✅ Approved| Deposit[💰 Deposit Funds to Platform]:::actionClass
    
    Deposit --> GetKey[📨 Receive Refer Code]:::actionClass
    GetKey --> Activate[🔓 Activate API Key]:::actionClass
    
    Activate --> Config[⚙️ Configure Plugin]:::configClass
    Config --> ConfigAPI[1️⃣ Enter API Key]:::configClass
    ConfigAPI --> ConfigParam[2️⃣ Set Strategy Parameters]:::configClass
    
    ConfigParam --> LoginEdge[🌐 Login to edgeX Platform]:::platformClass
    LoginEdge --> LoginVar[🌐 Login to Variational Platform]:::platformClass
    
    LoginVar --> CheckTrade{💹 Check Trading Capability}:::decisionClass
    CheckTrade -->|❌ Not Ready| Refresh[🔄 Refresh Both Platforms]:::warningClass
    Refresh --> CheckTrade
    CheckTrade -->|✅ Ready| Launch[🎯 Click Start Strategy]:::launchClass
    
    Launch --> Running([✨ Strategy Running]):::successClass
    Running --> Monitor[📈 Monitor Status]:::monitorClass
    Monitor -->|⚠️ Error| Fix[🔧 Fix Issues]:::warningClass
    Fix --> Launch
    Monitor -->|✅ Normal| Running
    
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

## 📝 Step-by-Step Guide

### 1️⃣ Preparation Phase
- Ensure you have AlphaLabs invitation link
- Prepare your EOA wallet address
- Prepare funds for deposit

### 2️⃣ Verification & Activation
- Submit EOA address for invitation verification
- Deposit funds after approval
- Receive and activate API Key

### 3️⃣ Plugin Configuration
- Enter API Key in plugin
- Set strategy parameters according to community guidelines
- Save configuration

### 4️⃣ Platform Setup
- Login to edgeX using browser
- Login to Variational using browser
- Ensure both platforms show trading capability
- Refresh pages if necessary

### 5️⃣ Launch & Run
- Click "Start Strategy" button
- Monitor initial running status
- Confirm strategy is running properly

## ⚠️ Important Notes

- 🔐 **Security**: Keep your API Key safe, never share with others
- 💡 **Best Practice**: Use the same EOA address for both platforms
- 📊 **Monitoring**: Regularly check strategy running status
- 🛠️ **Troubleshooting**: Check configuration first, then contact community support
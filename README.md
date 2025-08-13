# 🚀 AlphaLabs Perp Plugin Strategy 001

[English](./README-EN.md) | **中文**

## 📌 概述

本插件是 AlphaLabs 的产品，目的是自动化在 edgeX 和 Variational 交易。

## ⚠️ 重要声明

插件本身**不开源**，因为策略有容量空间，只提供给部分 AlphaLabs 的 Perp 成员使用。

**使用条件**：必须要走 AlphaLabs 的邀请链接。

🚨 **法律警告**：
- 如果发现插件被恶意使用将会追究责任
- 如果发现用作商业用途也会追究责任

## 📝 注册文档

注册时，绑定的 EOA 最好是同一个 EOA 地址

1. **注册 edgeX** → [📖 查看教程](./edgeX-registration.md)
2. **注册 Variational** → [📖 查看教程](./Variational-registration.md)

## ⚙️ 插件配置教程

### 准备阶段

1. **🔑 提供 EOA 地址**
   - 提供 EOA 地址给 AlphaLabs 用户，用于核对邀请
   - 充值对应的资金到平台

2. **🔑 提供 FW 的 token**
   - 注册饭碗告警账户：[🥣 注册链接](https://fwalert.com/918826)
   - 提供 fw 的 token 给 AlphaLabs

3. **✅ 激活**
   - 激活并下发 refer code (AlphaLabs API key)

### 插件操作步骤

1. **📥 下载插件**
   - 下载 AlphaLabs 提供的插件压缩包

2. **🔓 获取解压密码**
   - 在 [AlphaLabs TG](https://t.me/+BvsYrO40sxxkMmY1) 群组获取解压密码
   - 解压插件文件

3. **🔧 安装插件**
   - 打开 Chrome 浏览器，进入扩展程序管理（chrome://extensions/）
   - 开启右上角的"开发者模式"
   - 点击左上角"加载已解压的扩展程序"
   - 选择解压后的插件文件夹

4. **🌐 登录平台**
   - 在同一浏览器打开两个新标签页
   - 分别登录 edgeX 和 Variational 平台
   - 完成资金充值

5. **⚙️ 策略参数配置**
   - 打开插件进行参数设置
   - **推荐配置**：
     - 默认参数适合大多数情况
     - 如需频繁开平仓，可将 gain 值设置为小于 -40
   - **⚠️ 重要**：平台杠杆倍数必须与插件内杠杆倍数一致，否则会出错

6. **🚀 启动策略**
   - 点击"启动策略"按钮运行
   - **调试方法**：右键插件图标 → Inspect → 查看控制台输出

[📊 查看配置流程图](./plugin-configuration-flowchart-CN.md)

## 💬 技术支持

如需技术支持和更新，请联系 AlphaLabs 社区。

## 📄 许可证

版权所有 © 2025 AlphaLabs。保留所有权利。查看 [LICENSE](./LICENSE.md) 了解详情。
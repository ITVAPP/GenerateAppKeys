# iOS App Store 发布指南

## 需要的证书和文件

1. **Apple Developer 账号** (必需)
   - 访问 https://developer.apple.com
   - 年费 $99 USD

2. **需要创建的证书**：
   - iOS Distribution Certificate (发布证书)
   - Provisioning Profile (配置文件)

## 创建步骤

### 1. 创建 App ID
1. 登录 Apple Developer
2. 进入 Certificates, Identifiers & Profiles
3. 点击 Identifiers → + 按钮
4. 选择 App IDs → Continue
5. 输入：
   - Description: IAppPlayer
   - Bundle ID: net.itvapp.iapp_player_example
6. 选择需要的 Capabilities
7. Register

### 2. 创建发布证书
1. 点击 Certificates → + 按钮
2. 选择 iOS Distribution → Continue
3. 按照指示创建 CSR 文件
4. 上传 CSR 文件
5. 下载证书 (.cer 文件)

### 3. 创建 Provisioning Profile
1. 点击 Profiles → + 按钮
2. 选择 App Store → Continue
3. 选择你的 App ID
4. 选择你的发布证书
5. 命名为 "IAppPlayer Distribution"
6. 下载 .mobileprovision 文件

### 4. 导出 p12 文件
1. 双击安装下载的 .cer 文件
2. 打开 Keychain Access (钥匙串访问)
3. 找到你的证书
4. 右键 → Export
5. 保存为 .p12 格式
6. 设置密码 (建议: iappplayer2024)

## 文件放置位置

将以下文件放入 keys 目录：
- `ios_distribution.p12` - 发布证书
- `IAppPlayer_Distribution.mobileprovision` - 配置文件

## 在 GitHub Actions 中使用

1. 将 p12 文件转为 base64:
   ```bash
   base64 -w 0 ios_distribution.p12 > ios_p12_base64.txt
   ```

2. 将 mobileprovision 转为 base64:
   ```bash
   base64 -w 0 IAppPlayer_Distribution.mobileprovision > ios_provision_base64.txt
   ```

3. 在 GitHub Secrets 中添加：
   - IOS_P12_BASE64
   - IOS_P12_PASSWORD
   - IOS_PROVISION_BASE64
   - IOS_TEAM_ID

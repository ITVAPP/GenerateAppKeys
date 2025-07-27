# 证书使用说明

## Android

- 证书文件: `android_keystore.jks`
- 配置文件: `android_key.properties`
- 密码: iappplayer2024
- 别名: upload

使用方法：
1. 确保 `keys/android_keystore.jks` 文件存在
2. 将 `keys/android_key.properties` 复制到 `example/android/key.properties`

或在 `example/android/key.properties` 中使用：
```
storePassword=iappplayer2024
keyPassword=iappplayer2024
keyAlias=upload
storeFile=../../keys/android_keystore.jks
```

## iOS

请查看 `ios_certificates_guide.md` 了解如何创建 iOS 证书。

iOS 证书需要 Apple Developer 账号手动创建，无法自动生成。

## 安全提醒

**重要**：
- 这些证书文件非常重要，请妥善保管
- 不要将证书密码提交到公开仓库
- 建议使用 GitHub Secrets 存储敏感信息
- Android 证书一旦丢失，将无法更新 Google Play 上的应用
- 生成后请立即备份 keys 目录到安全位置

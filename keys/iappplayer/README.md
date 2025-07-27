# iappplayer 证书使用说明

## 证书信息

- **证书文件**: `iappplayer_keystore.jks`
- **密钥库密码**: `iappplayer2024`
- **密钥密码**: `iappplayer2024`
- **密钥别名**: `upload`
- **组织**: `ITVAPP`
- **有效期**: 30 年
- **创建时间**: 2025-07-27 15:29:49

## 文件说明

- `iappplayer_keystore.jks` - Android 发布证书
- `key.properties` - Android 签名配置
- `iappplayer_keystore_base64.txt` - 证书的 Base64 编码
- `github_secrets_setup.md` - GitHub Secrets 设置指南

## 使用方法

### 本地使用
1. 将此目录复制到项目中
2. 在 `example/android/key.properties` 中配置路径

### GitHub Actions 使用
1. 查看 `github_secrets_setup.md`
2. 设置相应的 Secrets
3. 在工作流中使用

## 安全提醒

- 🔒 这是生产证书，请妥善保管
- 🔒 不要删除或丢失此证书
- 🔒 所有应用更新都需要使用相同的证书
- ⚠️  建议立即备份到安全位置

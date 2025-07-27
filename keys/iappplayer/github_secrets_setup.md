# GitHub Secrets 设置指南 - iappplayer

## 设置步骤

1. **进入仓库设置**
   - 打开你的 GitHub 仓库
   - 点击 **Settings** (设置)
   - 左侧菜单选择 **Secrets and variables** → **Actions**

2. **添加以下 Secrets**
   
   点击 **New repository secret** 按钮，逐个添加：
   
   ### 选项 A：使用默认名称
   - **KEYSTORE_BASE64**: 复制 `iappplayer_keystore_base64.txt` 的内容
   - **KEYSTORE_PASSWORD**: `iappplayer2024`
   - **KEY_ALIAS**: `upload`
   
   ### 选项 B：使用自定义名称（多证书场景）
   - **IAPPPLAYER_KEYSTORE_BASE64**: 复制 `iappplayer_keystore_base64.txt` 的内容
   - **IAPPPLAYER_KEYSTORE_PASSWORD**: `iappplayer2024`
   - **IAPPPLAYER_KEY_ALIAS**: `upload`

## 在 GitHub Actions 中使用

```yaml
- name: Setup signing for iappplayer
  env:
    KEYSTORE_BASE64:     KEYSTORE_PASSWORD:     KEY_ALIAS:   run: |
    cd example/android
    
    # 解码密钥库
    echo "$KEYSTORE_BASE64" | base64 --decode > app/iappplayer_keystore.jks
    
    # 创建 key.properties
    cat > key.properties << PROPS
    storePassword=$KEYSTORE_PASSWORD
    keyPassword=$KEYSTORE_PASSWORD
    keyAlias=$KEY_ALIAS
    storeFile=iappplayer_keystore.jks
    PROPS
```

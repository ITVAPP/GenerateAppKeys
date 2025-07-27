# 证书目录

此目录包含所有生成的应用证书。每个子目录对应一个不同的证书配置。

## 目录结构

```
keys/
├── README.md (此文件)
└── [证书名称]/
    ├── [证书名称]_keystore.jks
    ├── [证书名称]_keystore_base64.txt
    ├── key.properties
    ├── github_secrets_setup.md
    └── README.md
```

## 使用指南

1. 选择对应的证书目录
2. 查看该目录下的 README.md
3. 按照说明配置项目

## 安全提醒

⚠️  请勿将包含 base64 的文件提交到版本控制
🔒 定期备份所有证书到安全位置

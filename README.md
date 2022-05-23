# prettier-demo

## 格式话代码的方式
### vscode的配置
勾选 Editor: Format On Save

### 使用 Git Hooks 实现自动格式化代码 
**前提**：由于要使用``npm set-script``, 故``npm`` 的版本必须是 >= v7.x

#### 1. 安装 ``husky`` 与 ``lint-staged``
```
npm install --save-dev husky lint-staged
npx husky install
npm set-script prepare "husky install"
npx husky add .husky/pre-commit "npx lint-staged"
```

#### 2. 在 ``package.json`` 文件添加配置文件
```
{
  "lint-staged": {
    "**/*": "prettier --write --ignore-unknown"
  }
}
```
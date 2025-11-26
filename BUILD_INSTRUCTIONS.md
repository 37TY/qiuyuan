# Autumnity 模组编译指南

## 本次修复内容
修复了火鸡物品模型加载失败的问题，避免了与 Kilt/Porting Lib 的冲突。

### 修改的文件：
- `src/main/resources/assets/autumnity/models/item/turkey.json`
- `src/main/resources/assets/autumnity/models/item/cooked_turkey.json`

**修复方式**：将 `particle` 纹理从根级别移动到 `base.textures` 中，避免重复字段导致不可变集合冲突。

## 使用 GitHub Actions 自动编译

### 步骤 1: 上传到 GitHub

```bash
# 初始化 Git（如果还没有）
git init

# 添加所有文件
git add .

# 提交更改
git commit -m "Fix turkey model loading conflict with Kilt/Porting Lib"

# 添加远程仓库（替换为你的仓库地址）
git remote add origin https://github.com/你的用户名/autumnity-1.20.x.git

# 推送到 GitHub
git push -u origin main
```

### 步骤 2: 等待自动编译

1. 推送后，GitHub 会自动触发编译
2. 访问仓库页面，点击 **Actions** 标签
3. 查看编译进度
4. 编译成功后，点击对应的 workflow run
5. 在 **Artifacts** 区域下载 `autumnity-mod.zip`
6. 解压得到编译好的 JAR 文件

### 步骤 3: 手动触发编译

也可以在 GitHub 仓库的 Actions 页面：
1. 点击左侧的 **Build Mod**
2. 点击右侧的 **Run workflow** 按钮
3. 选择分支后点击 **Run workflow**

## 本地编译（如果需要）

如果本地环境配置正确，可以运行：

```bash
# Windows
.\gradlew.bat build

# Linux/Mac
./gradlew build
```

编译完成后，JAR 文件位于：`build/libs/autumnity-1.20.1-5.0.2.jar`

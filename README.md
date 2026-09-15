# 秋招投递管理

一个无需安装、无需启动服务的本地秋招投递管理页面。应用代码和示例数据可提交到 Git，真实投递记录只保存在你的电脑上。

## 首次使用

1. 在项目目录中复制示例数据：

   ```powershell
   Copy-Item data/applications.example.json data/applications.json
   ```

   如果已经有自己的 `data/applications.json`，请跳过这一步，避免覆盖真实记录。

2. 使用最新版 Microsoft Edge 或 Google Chrome 双击打开 `index.html`。
3. 点击“打开数据”，选择 `data/applications.json`。
4. 浏览器询问权限时允许读写。之后新增、编辑和删除会自动写入该文件。

也可以在页面中点击“新建数据”创建全新的 JSON 文件。页面顶部会显示当前文件名和保存状态。

## 数据与备份

- `data/applications.json`：你的真实投递记录，已被 `.gitignore` 忽略，不会提交到仓库。
- `data/applications.example.json`：不含真实信息的基础示例，用于初始化和说明数据格式，应提交到仓库。
- 点击“另存备份”可以保存一份带日期的 JSON 副本，不会切换当前数据文件。
- 浏览器可能在刷新、重启或权限过期后要求重新授权，这是浏览器的文件安全机制。
- 如果浏览器无法直接写回文件，页面会切换为导入/下载模式；修改后点击“立即保存”下载新版 JSON。

## Git 与隐私

提交代码时只包含页面、说明和示例数据：

```powershell
git add index.html README.md .gitignore data/applications.example.json
git commit -m "更新秋招投递管理工具"
```

可以用下面的命令确认真实数据已被忽略：

```powershell
git check-ignore -v data/applications.json
```

请勿对真实数据文件使用 `git add -f`。如果它曾经进入过 Git 历史，仅从当前版本取消跟踪并不能清除旧提交中的内容；发布仓库前还需要检查历史记录。

## 兼容性

推荐最新版 Edge 或 Chrome。Firefox 和 Safari 目前不能保证直接写回本地 JSON，但仍可使用导入和下载保存模式。

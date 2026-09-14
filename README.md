# 秋招投递管理

一个无需安装、无需启动服务的本地秋招投递管理页面。数据保存在普通 JSON 文件中，可直接用 Git 管理。

## 使用方法

1. 使用最新版 Microsoft Edge 或 Google Chrome 双击打开 `index.html`。
2. 点击“打开数据”，选择 `data/applications.json`。
3. 浏览器询问权限时允许读写。之后新增、编辑和删除会自动保存。

也可以点击“新建数据”创建新的 JSON 文件。页面顶部会显示当前文件名以及保存状态。

## 数据与备份

- 默认数据位于 `data/applications.json`。
- 点击“另存备份”可以保存一份带日期的 JSON 副本，不会切换当前数据文件。
- 浏览器可能在重启或权限过期后要求重新选择或授权文件，这是浏览器的安全限制。
- 如果浏览器不支持直接写回文件，页面会切换为导入/下载模式；修改后点击“立即保存”下载新版 JSON。

## Git

默认可以直接跟踪数据文件：

```powershell
git add index.html data/applications.json README.md
git commit -m "更新秋招投递记录"
```

如果以后使用公开仓库，建议将真实的 `data/applications.json` 加入 `.gitignore`，只提交一份不含个人信息的示例数据。

## 兼容性

推荐最新版 Edge 或 Chrome。Firefox 和 Safari 目前不能保证直接写回本地 JSON，但仍可使用导入和下载保存模式。

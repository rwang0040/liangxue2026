# 两学考试练习系统

这是一个面向“两学考试”复习的静态练习系统，包含：

- 高等教育学练习系统
- 高等教育心理学练习系统
- 对应题库 JSON 数据

项目推荐部署到 GitHub Pages 使用，也可以通过本地 HTTP 服务打开。

## 在线入口

部署到 GitHub Pages 后，访问仓库 Pages 地址即可进入 `index.html`，再选择对应科目练习。

本地使用时，请在本目录启动一个简单 HTTP 服务：

```powershell
python -m http.server 8000
```

然后在浏览器访问：

```text
http://localhost:8000/
```

不建议直接双击打开练习页面，因为浏览器通常会限制 `file://` 页面读取本地 JSON 题库。

入口文件：

- `index.html`
- `高等教育学练习系统.html`
- `高等教育心理学练习系统.html`

## 文件说明

```text
README.md
LICENSE-CODE
LICENSE-CONTENT
index.html
高等教育学练习系统.html
高等教育心理学练习系统.html
edu_quiz_data.json
psych_quiz_data.json
```

其中：

- `index.html`：GitHub Pages 入口页。
- `高等教育学练习系统.html`：高等教育学练习页面。
- `高等教育心理学练习系统.html`：高等教育心理学练习页面。
- `edu_quiz_data.json`：高等教育学题库数据，便于二次开发或校对。
- `psych_quiz_data.json`：高等教育心理学题库数据，便于二次开发或校对。

## 答题记录

练习系统会在浏览器本地保存答题记录：

- 使用 `file://` 本地打开时，使用 `localStorage`。
- 使用 GitHub Pages、`localhost` 等网页方式打开时，优先使用 `IndexedDB`。
- 答题记录只保存在当前浏览器，不会上传到服务器。
- 每轮提交后可以导出 `log.txt`。

## GitHub Pages 部署

1. 将本目录中的发布文件提交到 GitHub 仓库。
2. 进入仓库 `Settings` -> `Pages`。
3. Source 选择 `Deploy from a branch`。
4. Branch 选择 `main`，目录选择 `/root`。
5. 保存后等待 GitHub Pages 构建完成。

建议上传发布文件即可，不要上传个人日志、原始 PDF、复核脚本或本地临时目录。

## 授权

本项目采用代码与内容分离授权：

- 代码部分：MIT License，见 `LICENSE-CODE`。
- 题库、解析、说明性文字等内容：Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International，见 `LICENSE-CONTENT`。

简要理解：

- 可以复制、修改、用于教学与复习。
- 使用内容时请注明来源。
- 不建议用于商业用途。
- 如果基于题库内容继续改编并公开发布，请使用相同授权方式共享。

## 免责声明

本项目为非官方学习资料。题目、答案和解析经过整理与复核，但仍可能存在疏漏。使用者应结合教材、课程资料和考试要求自行判断。

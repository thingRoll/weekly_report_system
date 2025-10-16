# 周报管理系统

一个轻量级、功能完整的周报管理系统，基于纯前端技术实现，支持周报的创建、编辑、删除、导入导出等功能。

## 功能特性

### 📋 核心功能
- **周数管理**：支持按周数或日期范围添加周报
- <img width="573" height="537" alt="image" src="https://github.com/user-attachments/assets/353041b9-e56e-4c1a-acf3-cb0c9f9dea35" />
- <img width="566" height="542" alt="image" src="https://github.com/user-attachments/assets/84f99b57-a0a4-4f49-8590-590e693f2016" />
- <img width="585" height="516" alt="image" src="https://github.com/user-attachments/assets/a2492710-b8ea-4c6b-bbc2-98da1efdb7c9" />

- **多类型周报内容**：
- 
  - <img width="567" height="492" alt="image" src="https://github.com/user-attachments/assets/6c58f082-930c-45d1-bde7-1b67dc4e2e2b" />
  - 内部填写：直接在系统中填写标准格式的周报
  - <img width="2544" height="1323" alt="image" src="https://github.com/user-attachments/assets/a3ade2bf-27dd-4bfb-b831-f4f8dec6c97a" />
  - 外嵌HTML：支持引用外部HTML文件作为周报内容
  - <img width="2550" height="1377" alt="image" src="https://github.com/user-attachments/assets/b993c796-29f3-47ce-8803-8a864a5f7a4d" />
  - 外链URL：支持通过URL嵌入外部内容
  - <img width="2547" height="1362" alt="image" src="https://github.com/user-attachments/assets/f8a89c36-376b-4a0d-bbe1-9165308bca69" />
- **数据管理**：
  - 数据导出：将所有周报数据导出为JSON文件
  - 数据导入：从JSON文件恢复周报数据
  - 定期备份提醒：每7天提示一次备份数据
- **Word导出**：将内部填写的周报导出为格式规范的Word文档

### 🎨 用户界面
- **现代化界面**：基于Tailwind CSS构建的简洁美观界面
- **直观导航**：左侧周数列表按年份分组，方便快速定位
- **响应式设计**：适配不同屏幕尺寸的设备
- **交互反馈**：操作过程中提供清晰的通知和状态提示

### 💾 数据存储
- **本地存储**：使用浏览器localStorage存储数据，无需后端服务
- **数据持久性**：关闭浏览器后数据仍然保留
- **安全性**：所有数据仅存储在本地，保护隐私

## 技术栈

- **前端框架**：纯HTML/CSS/JavaScript，无框架依赖
- **UI库**：Tailwind CSS v3
- **图标库**：Font Awesome
- **工具库**：
  - html-docx-js：将HTML转换为Word文档
  - FileSaver.js：实现文件下载功能

## 使用方法

### 🚀 快速开始
1. 将`weekly_report_system.html`文件下载到本地
2. 使用任意现代浏览器（Chrome、Firefox、Edge等）打开该文件
3. 开始使用周报管理功能

### 📝 创建周报
1. 点击左侧的**+**按钮添加新周
2. 选择添加方式：按周数或按日期范围
3. 选择周数后，选择周报内容类型：
   - **填写周报内容**：直接在表单中填写本周工作内容、遇到的问题、下周计划等
   - **使用外嵌HTML文件**：需要在同目录下创建`weekX.html`文件（X为周数）
   - **使用外链URL**：输入完整的URL地址

### 📊 管理周报
- **查看周报**：在左侧列表中点击周数查看对应内容
- **编辑周报**：选择周报后点击顶部工具栏的**编辑**按钮
- **删除周报**：选择周报后点击顶部工具栏的**删除**按钮
- **导出Word**：选择内部填写类型的周报后，点击顶部工具栏的**导出Word**按钮

### 💾 数据备份与恢复
- **备份数据**：点击顶部工具栏的**导出数据**按钮，下载JSON备份文件
- **恢复数据**：点击顶部工具栏的**导入数据**按钮，选择之前导出的JSON文件

## 项目结构

```
weekly_report_system/
├── weekly_report_system.html  # 主程序文件
├── week1.html                 # 示例外嵌HTML文件（可选）
├── week2.html                 # 示例外嵌HTML文件（可选）
└── README.md                  # 项目说明文档
```

## 高级功能

### ⚙️ 周数添加方式
- **按周数添加**：通过滑动条选择年份和周数
- **按日期范围添加**：选择周一作为开始日期，系统自动计算周日作为结束日期

### 📄 周报内容类型详解
1. **内部填写类型**：
   - 包含本周工作内容、遇到的问题、下周计划和备注四个部分
   - 支持导出为标准格式的Word文档

2. **外嵌HTML类型**：
   - 需要在与主程序相同目录下创建`weekX.html`文件
   - HTML文件内容将通过iframe嵌入到系统中
   - 适合需要复杂格式或包含特殊内容的周报

3. **外链URL类型**：
   - 支持嵌入外部网页内容
   - 注意：部分网站可能因安全设置无法在iframe中显示

### 📅 日期计算规则
- 系统使用ISO标准周数计算方法
- 每周从周一开始，到周日结束
- 第1周定义为包含1月4日的那一周

## 注意事项

1. **数据安全**：
   - 数据仅存储在浏览器本地，建议定期导出备份
   - 清除浏览器缓存或更换浏览器会导致数据不可见
   - 重要数据请务必定期导出保存

2. **外嵌HTML文件要求**：
   - 文件名必须为`weekX.html`格式
   - 必须与主程序文件放在同一目录

3. **浏览器兼容性**：
   - 推荐使用Chrome、Firefox、Edge等现代浏览器
   - 不保证在IE浏览器中的兼容性

## 常见问题

1. **问**：数据导出后如何恢复？
   **答**：点击顶部工具栏的**导入数据**按钮，选择之前导出的JSON文件即可。

2. **问**：为什么有些网站无法通过URL嵌入？
   **答**：部分网站设置了X-Frame-Options头部，禁止在iframe中显示，这是一种安全措施。

3. **问**：如何在多台设备间同步周报数据？
   **答**：可以通过导出/导入JSON文件在不同设备间迁移数据。

4. **问**：为什么外嵌HTML文件没有显示？
   **答**：请检查文件名是否正确（weekX.html），以及是否与主程序在同一目录。

## 更新日志

### v1.0.0
- 初始版本发布
- 实现周报的添加、编辑、删除功能
- 支持三种周报内容类型
- 实现数据导入导出和Word导出功能

## 许可证

本项目采用MIT许可证。

## 联系方式

如有问题或建议，请通过以下方式联系：

- Email: your@email.com
- GitHub: your-github-username

# Zhiping Lai's Personal Website

基于 Hugo Blox Builder 构建的个人学术网站，展示个人简历、学术论文、项目经历等内容。

## 项目信息

- **姓名**: 赖志平 (Zhiping Lai)
- **职位**: 资深研发工程师 (Senior Engineer)
- **机构**: 上海立芯软件科技有限公司 (Shanghai LEDA Technology Co., Ltd.)
- **网站**: [https://zephyr-lai.github.io](https://zephyr-lai.github.io)

## 技术栈

- **静态网站生成器**: Hugo
- **主题框架**: Hugo Blox Builder
- **内容格式**: Markdown, BibTeX
- **样式**: SCSS/CSS
- **部署**: GitHub Pages
- **多语言**: 中英文双语支持

## 主要功能

- 📄 **个人简历**: 展示个人信息、教育背景、工作经历
- 📚 **学术论文**: 支持 BibTeX 导入，自动生成引用格式
- 🚀 **项目展示**: 网格布局展示项目，支持图片和链接
- 📝 **博客文章**: Markdown 格式，支持数学公式和图表
- 🎤 **演讲活动**: 展示学术演讲和会议参与
- 🌐 **多语言**: 支持中英文切换
- 📱 **响应式**: 移动端友好的现代化设计

## 快速开始

### 环境要求

- Hugo 0.136.5+
- Git

### 本地运行

```bash
# 克隆项目
git clone https://github.com/zephyr-lai/zephyr-lai.github.io.git
cd zephyr-lai.github.io

# 安装 Hugo (macOS)
brew install hugo

# 启动开发服务器
hugo server -D

# 访问 http://localhost:1313
```

### 构建部署

```bash
# 构建静态文件
hugo --minify

# 推送到 GitHub Pages
git add .
git commit -m "Update site"
git push origin main
```

## 项目结构

```
├── config/              # 配置文件
│   └── _default/        # 默认配置
├── content/             # 内容文件
│   ├── en/             # 英文内容
│   └── zh/             # 中文内容
├── assets/             # 静态资源
├── static/             # 静态文件
├── themes/             # 主题文件
└── public/             # 构建输出
```

## 内容管理

### 更新个人信息
编辑 `content/en/authors/admin/_index.md` 或 `content/zh/authors/admin/_index.md`

### 添加新内容
```bash
# 创建新文章
hugo new content/post/my-new-post.md

# 创建新项目
hugo new content/project/my-project.md
```

### 导入论文
将 BibTeX 文件内容添加到 `publications.bib`，系统会自动生成论文页面。

## 自定义配置

### 主题设置
修改 `config/_default/params.yaml` 调整：
- 主题颜色和外观
- 功能开关
- SEO 设置
- 页眉页脚配置

### 自定义样式
创建 `assets/scss/custom/custom.scss` 添加自定义 CSS。

## 联系方式

- 📧 Email: [lzping1996@gmail.com](mailto:lzping1996@gmail.com)
- 💼 LinkedIn: [linkedin.com/in/志平-赖-45ab5134a](https://www.linkedin.com/in/%E5%BF%97%E5%B9%B3-%E8%B5%96-45ab5134a/)
- 🐙 GitHub: [github.com/zephyr-lai](https://github.com/zephyr-lai)
- 🎓 Google Scholar: [scholar.google.com/citations?user=oYRK793tsGYC](https://scholar.google.com/citations?user=oYRK793tsGYC&hl=zh-CN)

## 研究兴趣

- Electronic Design Automation (EDA)
- Artificial Intelligence (AI)
- Brain-Computer Interface (BCI)
- Robotics
- Quantitative Finance

## 教育背景

- **硕士**: 计算机应用技术 - 复旦大学 (2019-2022)
- **学士**: 计算机科学与技术 - 福州大学 (2015-2019)

## 许可证

本项目基于 MIT 许可证开源。详见 [LICENSE](LICENSE) 文件。

## 致谢

感谢 [Hugo Blox Builder](https://hugoblox.com/) 提供的优秀主题框架。

---

*最后更新: 2025年1月*
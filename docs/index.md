# 欢迎来到我的文档站点

这是一个使用 MkDocs 和 PyMdown Extensions Blocks 构建的文档站点示例。

## 🎯 功能展示

### 提示框 (Admonitions)

/// note | 基本信息
这是一个普通的提示框，用于展示重要的信息或说明。
///

/// tip | 实用技巧
这里分享一些使用技巧和小贴士，帮助用户更好地理解内容。
///

/// warning | 注意事项
**重要提醒**：请在使用前仔细阅读相关说明，避免出现意外问题。
///

/// success | 操作成功
恭喜！你的操作已成功完成。
///

### 可折叠内容 (Details)

/// details | 点击查看详细配置
这里是详细的配置说明，默认是折叠状态，用户点击后才会展开。

```yaml
markdown_extensions:
  - pymdownx.blocks.admonition
  - pymdownx.blocks.details
  - pymdownx.blocks.tab
```
///

### 选项卡 (Tabs)

/// note | 安装方法

使用 pip 安装

```bash
pip install pymdown-extensions
```

使用 conda 安装

```bash
conda install pymdown-extensions
```

///

/// note | 配置说明

在 `mkdocs.yml` 中添加：

```yaml
markdown_extensions:
  - pymdownx.blocks.admonition
  - pymdownx.blocks.details
```

///

/// tab | 使用示例

在 Markdown 文件中：

````markdown
/// note | 提示
这是一个提示框示例。
///

$$1+1=2$$
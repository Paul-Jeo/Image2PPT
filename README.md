<div align="center">
  <p>
    <img src="assets/readme/banner.png" alt="Image2PPT：从幻灯片图片到对象级可编辑 PowerPoint" width="100%">
  </p>
  <p>
    <a href="LICENSE"><img alt="License" src="https://img.shields.io/badge/license-MIT-2ea44f"></a>
    <a href="#安装与配置"><img alt="Install" src="https://img.shields.io/badge/install-Claude%20Code%20%7C%20Codex-8b5cf6"></a>
    <a href="README_EN.md"><img alt="Language" src="https://img.shields.io/badge/language-中文%20%7C%20English-1f6feb"></a>
  </p>
</div>

# Image2PPT

🧩 Image2PPT 专注把**复杂商业 PPT 和科研流程图**高保真重建为对象级可编辑 PowerPoint，在密集布局、复合图形和细小关系上兼顾清晰度与细节还原。

## 能力与案例

简单页面的图片转 PPT 已经不难，真正拉开差距的是复杂页面：元素数量多、层级关系密、局部图标小，任何节点、箭头或间距偏差都会破坏原图表达。Image2PPT 重点解决这类高难度还原：

- 🏢 **复杂商业 PPT**：还原密集时间线、多层流程、卡片、图标和复合箭头，同时保持版式与对象可编辑。
- 🔬 **复杂科研流程图**：逐节点、逐关系重建知识图谱和科研框架，保留圆形节点、连接线、箭头及局部结构。
- ✏️ **对象级可编辑**：文字、形状、节点、连接线和箭头均可独立选择，不使用整页截图充当伪可编辑底图。
- ✅ **双重质量优势**：在下方展示的同源案例对比中，Image2PPT 的清晰度表现最佳，细节还原度最高。

下面第一行展示复杂商业 PPT，第二行展示复杂科研图；两组“原图 / 转换图”组成 2×2 对照。转换图中的选框用于证明对象可以独立编辑，不会出现在放映模式中。

<table>
  <tr>
    <td align="center" width="50%"><strong>商业 PPT · 原图</strong><br><img src="assets/readme/business-source.png" alt="商业 PPT 原图" width="100%"></td>
    <td align="center" width="50%"><strong>商业 PPT · 转换图</strong><br><img src="assets/readme/business-converted.png" alt="商业 PPT 可编辑转换图" width="100%"></td>
  </tr>
  <tr>
    <td align="center" width="50%"><strong>学术图 · 原图</strong><br><img src="assets/readme/scientific-source.png" alt="学术图原图" width="100%"></td>
    <td align="center" width="50%"><strong>学术图 · 转换图</strong><br><img src="assets/readme/scientific-converted.png" alt="学术图可编辑转换图" width="100%"></td>
  </tr>
</table>

### 🔎 案例一：清晰度

下图对同一复杂局部进行放大比较，**左下角是 Image2PPT**，其余位置为其他 Image-to-PPT 方案。在本组案例中，Image2PPT 对图标轮廓、文字边缘和细线条的保留最清楚，整体清晰度表现最佳。

<p align="center"><img src="assets/readme/clarity-comparison.png" alt="复杂局部转换清晰度对比" width="100%"></p>

### 🧬 案例二：细节还原

下图比较复杂科研流程图的完整重建结果，**左下角是 Image2PPT**，其余位置为其他 Image-to-PPT 方案。在本组案例中，Image2PPT 更完整地保留知识图谱节点、关系连接线、箭头方向、图表结构和局部排版，细节还原度最高。

<p align="center"><img src="assets/readme/detail-comparison.png" alt="学术图细节与箭头重建对比" width="100%"></p>

## 典型请求

> 使用 $image2ppt，把这组幻灯片图片按顺序还原成可编辑 PPTX；文字、时间线和箭头需要保持可编辑。

> 使用 $image2ppt 重建这张科研框架图；知识图谱节点、关系线和普通箭头需要是独立的 PowerPoint 原生对象，并在渲染检查通过后交付。

## 你需要提供

- 一张或多张按顺序排列的 PNG/JPG，或扫描 PDF、图片型 PPT/PPTX。
- 如需在线生成或编辑图片资产，需明确允许上传当前任务的提示词和必要页面图片，并提供 Codex OAuth 或兼容 OpenAI Images API 的服务配置。

## 产出

- 对象级可编辑的 `.pptx`，保留可测量的文字、形状、节点、连接线和箭头。
- 页面与最终文件的 QA 报告；无法可靠原生重建的复杂局部视觉会作为可替换资产保留。

## 安装与配置

### 1. 获取 PaddleOCR Token

登录 [百度 AI Studio](https://aistudio.baidu.com/)，在 [Access Token 页面](https://aistudio.baidu.com/account/accessToken) 创建 Token。Image2PPT 使用的是一个 `PADDLE_OCR_TOKEN`，不是 AK/SK 组合。

### 2. 让 Agent 完成安装

将 Token 替换到下面对应的指令中，再整段交给 Agent。

#### Codex

> 我的 PaddleOCR Token 是 `<PADDLE_OCR_TOKEN>`。请从 `https://github.com/Paul-Jeo/Image2PPT` 将完整项目安装为当前项目的 `.agents/skills/image2ppt` Skill。安装 `requirements.txt` 中的依赖，将 `config.example.yaml` 复制为同目录的 `config.yaml`，仅把 Token 写入该文件，不要回显或提交。补齐 `doctor` 报告的系统依赖，最后运行 `doctor --json`，确认 `config_scope` 为 `project`、PaddleOCR Token 状态为 `set`。

#### Claude Code

> 我的 PaddleOCR Token 是 `<PADDLE_OCR_TOKEN>`。请从 `https://github.com/Paul-Jeo/Image2PPT` 将完整项目安装为当前项目的 `.claude/skills/image2ppt` Skill。安装 `requirements.txt` 中的依赖，将 `config.example.yaml` 复制为同目录的 `config.yaml`，仅把 Token 写入该文件，不要回显或提交。补齐 `doctor` 报告的系统依赖，最后运行 `doctor --json`，确认 `config_scope` 为 `project`、PaddleOCR Token 状态为 `set`。

### 3. 手动配置与可选图片后端

`config.example.yaml` 只是模板，程序实际读取同目录的 `config.yaml`；后者已被 Git 忽略。读取优先级为：环境变量 > `IMAGE2PPT_CONFIG_HOME` > 项目级 `config.yaml` > 旧版 `~/.image2ppt/config.yaml`。

手动配置时，将 `config.example.yaml` 复制为同目录的 `config.yaml`，填写 PaddleOCR Token：

```yaml
PADDLE_OCR_TOKEN: "你的 Token"
```

图片生成和编辑优先使用 Agent 内置图像工具；CLI 也可以使用 Codex OAuth。若要改用第三方图片模型，在同一 `config.yaml` 中填写兼容 OpenAI Images API 的服务配置：

```yaml
OPENAI_API_KEY: "你的 API Key"
OPENAI_BASE_URL: "https://服务地址/v1"
IMAGE2PPT_IMAGE_BACKEND: "openai-compatible-api"
IMAGE2PPT_IMAGE_MODEL: "供应商提供的模型 ID"
```

`auto` 仅在模型 ID 兼容 GPT Image 且本地已有 Codex 登录时选择 `codex-oauth`；其他模型 ID 使用 `openai-compatible-api`。第三方端点不会收到 Codex OAuth 凭证，但会收到当前任务的提示词和必要页面图片。

未配置 Token 或网络 OCR 失败时，程序会回退到 `builtin-ink`，只能测量文字区域，不能识别文字内容。

## 边界

- 用于还原已有视觉页面，不用于根据笔记、论文或提纲从零创作演示文稿。
- 复杂插图、照片和无法可靠测量的局部效果可能保留为独立图片资产，不保证所有元素都转换为原生形状。
- 低分辨率输入和缺失字体会限制还原精度；在线 OCR 会向百度服务上传当前任务页面，敏感材料应使用离线模式。
- 在线图片生成或编辑会把当前任务的提示词和必要页面图片发送到所选图片服务；敏感材料应选择离线模式或经批准的服务。

## License

本项目采用 [MIT License](LICENSE)。

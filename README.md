# GenshinRelicTool(原神圣遗物工具)

> 注意：目前项目还没有开始，我只有周末才有时间

GenshinRelicTool 是一个基于 Python 的开源工具，旨在帮助玩家自动化管理《原神》中的圣遗物。该工具通过模拟用户操作（如鼠标点击）来识别圣遗物并根据自定义规则进行解锁或锁定，帮助玩家减少重复性操作，更多地享受游戏内容。

## 功能特性
- **自动识别圣遗物属性**：通过图像识别技术，识别圣遗物的属性（如大攻击、大防御、大生命等）。
- **自定义管理规则**：用户可以自定义规则，自动解锁或锁定特定属性的圣遗物。
- **模拟鼠标操作**：通过模拟鼠标点击来实现圣遗物的管理，完全模拟用户行为。
- **不修改游戏数据**：工具不会抓取或修改任何游戏数据，保持对游戏规则的尊重和公平性。
- **开源社区支持**：欢迎大家贡献代码，共同完善功能，适应游戏的后续更新。

## 项目结构

```plaintext
GenshinRelicTool/
├── GenshinRelicTool.py        # 主程序入口，负责实时捕获屏幕、处理图像、识别圣遗物并执行操作
├── config/
│   └── settings.py            # 配置文件，用于存储游戏窗口尺寸、识别阈值、点击间隔等可调参数
├── core/
│   ├── RelicManager.py        # 圣遗物管理核心逻辑，包含识别和管理圣遗物的规则和功能
│   ├── UserActions.py         # 用户操作模拟模块，负责实现点击、拖动等用户交互行为
│   └── ImageProcessing.py     # 图像处理模块，用于处理截图、提取特征、提高识别准确度
├── utils/
│   ├── Logger.py              # 日志工具模块，记录操作日志、错误信息，便于调试和问题追踪
│   └── Helpers.py             # 辅助函数模块，包含通用的辅助功能，如坐标转换、时间处理等
├── tests/
│   ├── TestRelicManager.py    # 测试圣遗物管理模块的单元测试
│   ├── TestUserActions.py     # 测试用户操作模拟模块的单元测试
│   └── TestImageProcessing.py # 测试图像处理模块的单元测试
├── requirements.txt           # 依赖库文件，列出项目需要的Python库
├── README.md                  # 项目说明文档，介绍项目的背景、安装和使用方法
└── .gitignore                 # Git忽略文件，排除不需要的文件（如配置文件、缓存等）
```

## 安装指南

1. 克隆仓库：
   ```bash
   git clone https://github.com/yourusername/GenshinRelicTool.git
   ```
2. 安装所需依赖：
   ```bash
   pip install -r requirements.txt
   ```
3. 运行工具：
   ```bash
   python relic_manager.py
   ```

## 系统要求
- Python 3.8 及以上
- OpenCV（用于图像识别）
- PyAutoGUI（用于模拟鼠标点击）
- Tesseract-OCR（用于文本识别）

## 使用方法
1. 打开《原神》并进入圣遗物管理界面。
2. 运行工具，工具会根据 `config.yaml` 文件中定义的规则开始识别圣遗物。
3. 工具会自动根据规则锁定或解锁圣遗物。

## 配置文件
用户可以通过编辑 `config.yaml` 文件来自定义圣遗物管理规则。例如：
```yaml
lock_rule:
  - attribute: '攻击力'
    min_value: 20
unlock_rule:
  - attribute: '防御力'
    max_value: 15
```

## 贡献
欢迎大家为项目贡献代码！您可以提交 Pull Request 或者提出 Issue，与我们共同讨论改进。

## 许可协议
本项目基于 MIT 许可协议开源，详情请查看 [LICENSE](LICENSE) 文件。


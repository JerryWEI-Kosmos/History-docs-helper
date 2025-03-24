## 仓库架构

```
history-doc-helper/
├── 📁 docs/                        # 项目文档
│   ├── USER_GUIDE.md              # 图文并茂的用户操作手册
│   ├── DEV_ARCH.md                # 架构设计文档（含流程图）
│   └── API_REFERENCE.md           # 模块接口说明
│
├── 📁 src/                        		# 主代码库
│   ├── 📁 core/                   		# 核心业务逻辑
│   │   ├── ocr_engine/           		# OCR模块
│   │   │   ├── image_processor.py    	# 图像预处理
│   │   │   ├── text_extractor.py     	# 文字识别核心
│   │   │   └── data_splitter.py  		# 新增：智能内容分割
│   │   │
│   │   ├── ai_service/           		# 大模型模块
│   │   │   ├── llm_gateway.py        	# 接口核心
│   │   │   └── context_builder.py 		# 新增：上下文重建
│   │   │
│   │   └── naming_system/        		# 智能命名模块
│   │		├── rule_engine.py          # 名称格式化核心（原	rule_name.py）
│	│		├── file_reader.py          # 原始文档读取（原org_filesname.py）
│	│		├── backup_manager.py       # 备份与恢复系统（原name_backup.py）
│	│		├── audit_logger.py         # 新增：操作审计追踪
│	│		├── sanitizer.py       		# 文件名合法性检查
│   │ 		└── conflict_handler.py 	# 基础冲突检测
│   ├── 📁 interface/             # 用户界面
│   │   ├── gui/                 # 桌面端GUI
│   │   │   ├── main_window.py      # 主窗口管理
│   │   │   ├── components/         # 可重用控件
│   │   │   │   ├── file_picker.py  # 文件选择组件
│   │   │   │   └── preview_pane.py # 预览面板组件
│   │   │   ├── handlers/           # 事件处理
│   │   │   │   ├── file_ops.py     # 文件操作处理
│   │   │   │   └── naming_ctrl.py  # 命名控制逻辑
│   │   │   └── utils/
│   │   │       └── gui_helpers.py  # GUI专用工具类
│   │   │
│   │   ├── webui/               # 网页端
│   │   │   ├── frontend/        # 前端代码
│   │   │   ├── api/                # 后端接口
│   │   │   │   ├── ocr_routes.py   # OCR相关接口
│   │   │   │   ├── naming_routes.py # 命名接口
│   │   │   │   └── middleware.py   # 请求处理中间件
│   │   │   ├── service/            # 服务整合
│   │   │   │   └── async_tasks.py  # 异步任务管理
│   │   │   └── web_utils/
│   │   │       └── response.py     # 响应格式化工具
│   │   │
│   │   └── cli/                 # 命令行接口
│   │       ├── process_cmd.py  # 文档处理命令
│   │       ├── manage_cmd.py   # 系统管理命令
│   │       ├── formatters.py   # 结果格式化
│   │       ├── progress.py     # 进度显示
│   │   	└── arg_parser.py   # 参数解析引擎
│   │
│   ├── 📁 infrastructure/        # 基础设施
│   │   ├── config_manager/      # 配置管理（含默认模板）
│   │   ├── logging_system/      # 透明化日志模块
│   │   └── exception_handle/    # 异常处理中枢
│   │
│   └── 📁 shared/                # 共享资源
│       ├── schemas/             # 数据模型定义
│       ├── locales/             # 多语言支持
│       └── assets/              # 静态资源（图标/字体等）
│
├── 📁 tests/                     # 测试体系
│   ├── test_ocr_engine/
│   ├── test_ai_service/
│   └── test_naming_system/
│
├── 📁 configs/                   # 配置中心
│   ├── app_config.yaml          # 主配置文件
│   ├── ocr_models/              # OCR引擎配置
│   └── naming_rules/            # 预设命名模板
│
├── 📁 scripts/                   # 工具脚本
│   ├── setup_env.sh             # 环境初始化
│   ├── model_downloader.py      # 模型下载工具
│   └── data_migrator.py         # 数据迁移工具
│
├── 📁 sample_data/               # 示例数据
│   ├── test_documents/          # 测试用文献样本
│   └── expected_outputs/        # 预期结果样本
│
│
├── 📄 .gitignore                # 版本控制排除项
├── 📄 requirements.txt          # Python依赖清单
├── 📄 Dockerfile                # 容器化部署配置
├── 📄 Makefile                  # 常用命令快捷入口
└── 📄 LICENSE                   # 开源协议
```


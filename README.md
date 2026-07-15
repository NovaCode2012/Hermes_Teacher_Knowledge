# Hermes 教师团队知识库

## 环境概览

| 组件 | 状态 | 说明 |
|------|------|------|
| 📁 知识库 | ✅ 已搭建 | `~/Hermes_Teacher_Knowledge/` |
| 🔧 kb 助手 | ✅ 已安装 | `kb list/search/open/commit/llm` |
| 🧠 LLM 模型 | ✅ Qwen3.6-27B-VL-MTP | 本地部署，无需API密钥 |
| 🐳 Hermes 学科Agent | ✅ 14个容器运行中 | 数学/物理/化学/英语/语文等 |
| 🖥️ Dashboard | ✅ 运行中 | http://localhost:9119 |
| 📡 外网访问 | ✅ Cloudflare Tunnel | 已配置 |
| 💬 飞书集成 | ✅ Lark 已连接 | 可通过飞书与Agent对话 |

## 常用命令

### 知识库操作
```bash
kb list                    # 列出知识库
kb open 课程资料/数学/数学课程概述.md  # 编辑文件
kb view 课程资料/数学/数学课程概述.md  # 查看文件
kb search 牛顿            # 搜索内容
kb status                 # 查看未提交更改
kb commit "更新了教案"    # 提交Git
```

### 调用本地LLM（无需API密钥）
```bash
kb llm "解释牛顿第一定律"
kb llm "根据知识库总结数学课程内容"
kb llm "帮我分析数学期中考试成绩"
```

### Hermes Docker 服务
```bash
docker ps --filter "name=hermes"   # 查看所有Agent
docker logs hermes-teacher-math -f # 查看数学老师日志
```

## 学科Agent端口映射
| 学科 | 端口 | 容器名 |
|------|------|--------|
| 数学 | 7071 | hermes-teacher-math |
| 物理 | 7070 | hermes-teacher-physics |
| 化学 | 7080 | hermes-teacher-chemistry |
| 英语 | 7076 | hermes-teacher-english |
| 语文 | 7078 | hermes-teacher-chinese |
| 生物 | 7077 | hermes-teacher-biology |
| 地理 | 7075 | hermes-teacher-geography |
| 编程 | 7082 | hermes-teacher-programming |
| 历史 | 7081 | hermes-teacher-history |
| 班主任 | 7072 | hermes-teacher-class-advisor |
| 心理 | 7079 | hermes-teacher-psychologist |
| 体育 | 7073 | hermes-teacher-physical |
| 道德 | 7074 | hermes-teacher-moral |
| Dashboard | 9119 | hermes-dashboard |

## 知识库同步
```bash
cd ~/Hermes_Teacher_Knowledge
git pull          # 拉取更新
git push          # 推送更改
```

## 目录结构
```
Hermes_Teacher_Knowledge/
├── 课程资料/          # 学科知识
│   ├── 数学/物理/化学/
├── 教案/              # 教学计划
│   ├── 上学期/下学期/
├── 学生记录/           # 成绩与评估
├── 管理文档/           # 会议纪要、政策
├── 备忘录/
└── 参考文献/
```

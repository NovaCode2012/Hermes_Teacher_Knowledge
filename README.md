# Hermes 教师团队知识库

## 快速开始

### 1. 进入知识库
```bash
cd ~/Hermes_Teacher_Knowledge
```

### 2. 使用 Hermes 助手（推荐）
```bash
hermes help          # 查看所有命令
hermes list          # 列出知识库内容
hermes open 课程资料/数学/数学课程概述.md   # 编辑文件
hermes view 课程资料/数学/数学课程概述.md   # 查看文件
hermes search 牛顿   # 搜索关键词
hermes status       # 查看更改状态
hermes commit "更新了教案"  # 提交更改
```

### 3. 手动编辑
```bash
nano ~/Hermes_Teacher_Knowledge/课程资料/数学/数学课程概述.md
```

### 4. 保存和同步
```bash
cd ~/Hermes_Teacher_Knowledge
git add .
git commit -m "更新内容"
git push            # 推送到远程仓库（需要先配置）
git pull            # 拉取最新内容
```

---

## 知识库结构

```
Hermes_Teacher_Knowledge/
├── 课程资料/          ← 各学科讲义、知识点
│   ├── 数学/
│   ├── 物理/
│   └── 化学/
├── 教案/             ← 教学计划
│   ├── 上学期/
│   └── 下学期/
├── 学生记录/          ← 成绩、表现评估
│   ├── 考试成绩/
│   └── 表现评估/
├── 管理文档/          ← 会议纪要、政策
│   ├── 会议纪要/
│   └── 政策指南/
├── 备忘录/           ← 教师个人备忘
└── 参考文献/          ← 参考资料
```

---

## 配置 LLM

### 方式一：配置 OpenAI 兼容 API
```bash
nano ~/Hermes_Teacher_Knowledge/.hermes-llm.json
```

填入（根据实际情况修改）：
```json
{
  "type": "openai",
  "api_url": "https://api.openai.com/v1/chat/completions",
  "api_key": "sk-你的密钥",
  "model": "gpt-4o-mini"
}
```

然后使用：
```bash
hermes llm "帮我总结一下数学期中考试成绩"
```

### 方式二：直接使用 curl
```bash
curl https://api.openai.com/v1/chat/completions \
  -H "Authorization: Bearer sk-你的密钥" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gpt-4o-mini",
    "messages": [{"role": "user", "content": "总结数学成绩"}]
  }'
```

---

## 团队协作

1. 关联远程仓库（管理员执行一次）：
```bash
cd ~/Hermes_Teacher_Knowledge
git remote add origin <仓库地址>
git push -u origin master
```

2. 日常流程：
```bash
git pull          # 拉取同事更新
hermes open ...   # 编辑文件
hermes commit "更新"  # 提交
git push          # 推送
```

---

## 📝 编辑规范

- 文件名：尽量用中文，清晰表达内容
- 格式：Markdown 标准格式
- 链接引用：`[显示名](文件名.md)`
- 图片：放在 `attachments/` 目录下
- 标签：文件顶部可加 `#标签` 便于搜索

# 秒冲 AI（Miaochong AI）




写 AI 大模型 API 的实操笔记，GPT / Claude / Gemini / Grok 都能接。




每篇结构固定：结论 → 场景 → 能直接抄的代码 → 实测数据 → 坑与边界。数字只有三种来源：本机实测（写清模型、参数、日期、样本数）、官方文档（挂链接 + 截至某月）、估算（写清算法）。不编造跑分。




## 在写什么




- 429 / 限流：指数退避、jitter、队列与 Retry-After
- token 计费：一次请求的输入输出 token 怎么估，单价怎么算
- 结构化输出：JSON Schema、function calling、校验与重试
- RAG：切分、召回、重排、引用
- 流式输出：SSE 解析、断线续传、前端增量渲染
- 多模型路由：按任务 / 成本 / 延迟分流，以及降级策略




## 关于代码




示例都用 Python 3.13 写，能直接跑；涉及外部接口的部分用本地 mock server 复现，不依赖真实 key。




## 线上验证




上面这些实现不是纸上推演，跑在一个实际在运营的站点上：https://miaochong.org
（nginx 按 UA 分流 + Python 读 SQLite 直出 + sitemap / llms.txt 自动生成）。




## 联系




uwosdlima@gmail.com




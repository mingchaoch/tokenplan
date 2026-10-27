# tokenplan

**在有限令牌预算下安排请求顺序。**

`tokenplan` —— 按预估消耗与优先级分配预算，给出调度顺序与超限风险

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`tokenplan.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install mingchaoch-tokenplan
```

装完直接用命令名调用：

```bash
tokenplan --help
```

也可以不用安装，直接把 `tokenplan.py` 拷走用——它只依赖标准库。

## 为什么需要它

预估值带区间，不假装知道精确消耗

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 令牌预算调度 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python tokenplan.py --file input.txt
python tokenplan.py --text "示例内容"
python tokenplan.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 预算是静态比例分配，不考虑实际执行顺序。
- 不接真实队列，只做分配表。

## 跑测试

```bash
python test_tokenplan.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/mingchaoch/tokenplan>

---

## 关于作者

mingchaoch 做令牌预算调度相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://mingchaoch.github.io>
- 仓库：<https://github.com/mingchaoch/tokenplan>

## 许可

MIT，见 [LICENSE](LICENSE)。

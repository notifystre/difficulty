# difficulty

**给评测样本按难度分层并给出每层的通过率。**

`difficulty` —— 依据历史通过率与推理步数把样本分层，标出区分度不足的题目

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`difficulty.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install notifystre-difficulty
```

装完直接用命令名调用：

```bash
difficulty --help
```

也可以不用安装，直接把 `difficulty.py` 拷走用——它只依赖标准库。

## 为什么需要它

区分度低的题目会被点名——它们在总分里贡献不了信息

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 评测难度分层 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python difficulty.py --file input.txt
python difficulty.py --text "示例内容"
python difficulty.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 分箱是等宽或等频，样本太少时结论不稳。
- 不做显著性检验。

## 跑测试

```bash
python test_difficulty.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/notifystre/difficulty>

---

## 关于作者

notifystre 做评测难度分层相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://notifystre.github.io>
- 仓库：<https://github.com/notifystre/difficulty>

## 许可

MIT，见 [LICENSE](LICENSE)。

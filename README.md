# recallgap

**找出用户问题里没被任何检索结果覆盖的部分。**

`recallgap` —— 把问题拆成需要回答的子点，标出检索结果完全没覆盖到的子点

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`recallgap.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install dylanjlee1-recallgap
```

装完直接用命令名调用：

```bash
recallgap --help
```

也可以不用安装，直接把 `recallgap.py` 拷走用——它只依赖标准库。

## 为什么需要它

缺口按「子点」而非「文档」判定，一篇文档只能覆盖它真正回答的那部分

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 召回缺口识别 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python recallgap.py --file input.txt
python recallgap.py --text "示例内容"
python recallgap.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 覆盖率的分母取自你登记的清单，清单不全就会偏高。
- 只做映射，不追责。

## 跑测试

```bash
python test_recallgap.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/dylanjlee1/recallgap>

---

## 关于作者

dylanjlee1 做召回缺口识别相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://dylanjlee1.github.io>
- 仓库：<https://github.com/dylanjlee1/recallgap>

## 许可

MIT，见 [LICENSE](LICENSE)。

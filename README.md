# aligndrift

**监控模型对齐表现的漂移。**

`aligndrift` —— 追踪对齐指标随版本的变化，标出退化的方向与幅度

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`aligndrift.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install dollcrew-aligndrift
```

装完直接用命令名调用：

```bash
aligndrift --help
```

也可以不用安装，直接把 `aligndrift.py` 拷走用——它只依赖标准库。

## 为什么需要它

对齐漂移要能定位到具体版本区间

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 对齐漂移检测 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python aligndrift.py --file input.txt
python aligndrift.py --text "示例内容"
python aligndrift.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 阈值是固定值，不随数据自适应。
- 只判定达标与否，不解释分数来源。

## 跑测试

```bash
python test_aligndrift.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/dollcrew/aligndrift>

---

## 关于作者

dollcrew 做对齐漂移检测相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://dollcrew.github.io>
- 仓库：<https://github.com/dollcrew/aligndrift>

## 许可

MIT，见 [LICENSE](LICENSE)。

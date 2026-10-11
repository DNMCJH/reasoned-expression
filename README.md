# Reasoned Expression

一个面向 Codex、Claude Code 和其他 coding agents 的中文写作与对话 skill。

它关注的不只是句子是否自然，还包括：

- 判断是否有依据，范围是否超出材料；
- 事实、推断、观点和不确定性是否分清；
- 长文的主问题、段落重点和论证推进是否成立；
- 专业解释是否适合读者，概念是否衔接；
- 日常对话、报告、论文、时评和翻译是否使用合适的语气。

它不是万能写作模型，也不是 AI 文本检测规避工具。材料不足时，它应当收窄结论或要求补充信息；
样例用于校准判断，不是固定句式模板。

## 安装

### Codex

将 `reasoned-expression` 目录放入：

```text
~/.codex/skills/reasoned-expression/
```

然后重启 Codex 会话。可以显式使用：

```text
用 $reasoned-expression 处理这篇文章。
```

### Claude Code

将同一目录放入：

```text
~/.claude/skills/reasoned-expression/
```

重启 Claude Code 会话后使用。Claude Code 不需要 `agents/openai.yaml`，它只读取 `SKILL.md` 和 references。

## 设计原则

skill 先判断任务和材料，再组织内容，最后处理句子。涉及当前事实、行业状况、政策或岗位时，
不能只靠流畅表达补足调查；涉及局部润色时，也不应无故把任务扩大成研究报告。

## 当前状态

这是一个实验性个人 skill。它已经经过若干真实任务校准，但还没有完成系统性的跨模型 A/B 评测。
仓库中的 benchmark 用于记录后续测试，不代表已经通过质量认证。

## 目录

- `SKILL.md`: 共用方法和触发边界
- `references/contexts.md`: 不同场景的特殊要求
- `references/language-adaptation.md`: 翻译与英文表达
- `references/calibration.md`: 脱敏后的校准样例
- `references/evaluation.md`: 轻量验收标准
- `benchmarks/`: 独立测试集

## License

MIT，见 `LICENSE`。

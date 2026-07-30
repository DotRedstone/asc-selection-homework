# ASC 超算队最终选拔作业

本仓库用于发布 ASC 超算队最终选拔作业。

本次作业由两部分组成：基础题和大题。每位同学需要在 HPL / HPCG 中选择 1 个基础题完成，再从给定大题中选择 1 个完成。作业重点考察完整实践能力：阅读任务、配置环境、跑通 Baseline、记录性能、定位问题、尝试优化、验证正确性，并把过程整理成可复现的报告。

## 任务来源

本次选拔题参考 ASC26 相关公开任务与往届训练内容整理，面向校内训练与队员选拔使用。

- ASC26 Preliminary Round: <https://www.asc-events.net/StudentChallenge/ASC26/preliminary.php>
- ASC26 Preliminary Round Notification: <https://www.asc-events.net/StudentChallenge/ASC26/static/ASC26_Preliminary_Round_Notification.pdf>
- ASC26 Final Competition Notification: <https://www.asc-events.net/StudentChallenge/ASC26/static/ASC26FinalCompetitionNotification.pdf>
- ASC-Competition GitHub: <https://github.com/ASC-Competition>

## 任务组成

| 部分 | 可选题目 | 完成要求 | 主要考察 |
| --- | --- | --- | --- |
| 基础题 | HPL / HPCG | 二选一 | 编译、MPI、BLAS、参数搜索、性能记录 |
| 大题 | Embodied World Model / AlphaFold3 / AMSS-NCKU / QiboTN / Group Competition & ICON | 任选一题 | 应用部署、性能分析、优化验证、结果整理 |

详细要求见 [docs/assignment.md](docs/assignment.md)。

## 题目入口速查

| 部分 | 任务 | 入口链接 |
| --- | --- | --- |
| 基础题 | HPL | 下载地址：<https://www.netlib.org/benchmark/hpl/>；调参说明：<https://www.netlib.org/benchmark/hpl/tuning.html> |
| 基础题 | HPCG | 代码仓库：<https://github.com/hpcg-benchmark/hpcg> |
| 大题 | Embodied World Model | 赛题仓库：<https://github.com/ASC-Competition/ASC26-Embodied-World-Model-Optimization>；项目仓库：<https://github.com/unitreerobotics/unifolm-world-model-action> |
| 大题 | AlphaFold3 | 代码仓库：<https://github.com/google-deepmind/alphafold3> |
| 大题 | AMSS-NCKU | 代码仓库：<https://github.com/ASC-Competition/AMSS-NCKU> |
| 大题 | QiboTN | 文档：<https://qibo.science/qibotn/stable/index.html>；代码仓库：<https://github.com/qiboteam/qibotn> |
| 大题 | Group Competition / ICON | ICON 仓库：<https://github.com/ASC-Competition/ASC26-icon>；任务说明：<https://www.asc-events.net/StudentChallenge/ASC26/static/Task_Description_of_Group_Competition.pdf> |

## 完成流程

1. 阅读本仓库说明，选择 1 个基础题和 1 个大题。
2. 根据题目入口链接下载或克隆对应项目。
3. 配置运行环境，记录做题机器的硬件信息、系统版本和软件版本。
4. 跑通 Baseline，保存命令、日志、运行时间和正确性结果。
5. 基于运行现象进行分析，选择若干优化或工程改进。
6. 重新运行优化后的程序，对比性能与正确性。
7. 整理最终报告。
8. 将最终报告发送至 `dotredstone0123@gmail.com`。

## 推荐完成方式

更推荐直接基于所选题目对应的官方仓库完成作业：

1. fork 或 clone 对应题目的官方仓库；
2. 在该项目中完成环境配置、Baseline 运行、优化修改和结果记录；
3. 将代码修改、日志、结果和复现说明分别提交到基础题仓库和大题仓库；
4. 在最终报告中写清相关仓库链接和复现方式。

基础题和大题应分开使用两个相关仓库。基础题仓库用于保存 HPL 或 HPCG 的运行记录，大题仓库用于保存所选大题的代码修改、日志、结果和复现说明。

两个相关仓库都需要设置为 Public，确保报告中的链接可以直接打开。

如果某个官方仓库较大、包含大模型权重、数据集或 Git LFS 文件，也可以为对应题目单独创建轻量整理仓库。轻量整理仓库只需要包含关键日志、结果记录和代码修改说明。

如果本地硬件条件不足，可以使用 **Google Colab**、自备服务器或其他自备云计算资源。使用外部资源时，需要在报告中写清资源来源、CPU/GPU 型号、显存、系统环境和是否使用付费资源。Colab 分配到的 GPU/TPU 资源不固定，应以实际运行时记录为准。

两个相关仓库不强制固定目录结构，但至少应包含：

- `README.md` 或 `SUBMISSION.md`：写明姓名、对应题目、运行环境和复现方式；
- 对应题目的运行命令、关键日志和结果记录；
- 如果修改了源码，应提交修改后的代码、补丁文件或在报告中说明修改位置。

本仓库提供了可参考的报告内容模板。模板只用于写作参考，最终邮件附件必须提交 PDF：

- Markdown 模板：`templates/report.md`
- LaTeX 模板：`templates/report.tex`

报告写作方式不限：

- Word：写完后导出为 PDF；
- Markdown：写完后用编辑器、Pandoc 或其他工具导出为 PDF；
- LaTeX：写完后编译为 PDF。

## 最终提交

最终提交一封邮件至 `dotredstone0123@gmail.com`，邮件附件只接收 PDF 报告。报告可以使用 Markdown、LaTeX、Word 或其他方式编写，但最后必须导出或编译为 PDF。

PDF 文件命名必须严格为：

```text
姓名_基础题_大题_report.pdf
```

邮件标题必须严格为：

```text
ASC选拔作业-姓名-基础题-大题
```

标题中不要添加空格、括号、学号或其他额外文字。

邮件正文必须严格使用以下格式，不要添加额外说明：

```text
姓名：
年级专业：
基础题：
大题：
基础题仓库链接：
大题仓库链接：
完成情况：
```

邮件附件只放 1 个 PDF 报告，不要发送压缩包、代码包、截图合集或其他附件。

最终评价以报告为主要依据，相关 GitHub 仓库用于复查源码、日志、结果和可复现性。报告、运行命令、日志、结果文件和机器环境说明应能互相对应。基础题仓库链接和大题仓库链接应分别填写。

基础题仓库和大题仓库必须设置为 Public，确保评审时无需申请权限即可访问。

大型数据、模型权重和编译产物不需要放入仓库。报告中应写清楚它们的获取方式和放置路径。

## 基本要求

- 每位同学需要完成 1 个基础题和 1 个大题。
- 不允许伪造运行结果。
- 不允许只提交截图。
- 必须保留报告、运行命令、日志或结果记录。
- 必须在报告中说明基础题和大题分别使用的机器环境。
- 优化后必须验证结果仍然正确。
- 如果机器性能不足，可以降低规模，或使用 **Google Colab**、自备服务器、其他自备云计算资源，但必须在报告中说明。
- 如果程序未完全跑通，也应提交真实排错过程、报错信息和已尝试方法。

本次作业不单纯比较硬件性能，也不以加速比大小作为唯一标准。更重要的是过程真实、记录完整、判断有依据、结果可复现。

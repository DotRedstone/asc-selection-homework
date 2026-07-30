# 题目说明

## 一、选拔说明

本次选拔由两部分组成：基础题和大题。每位同学需要在 HPL / HPCG 中选择 1 个基础题完成，再从给定大题中选择 1 个完成。

本次选拔重点考察：

- 是否能够看懂题目要求；
- 是否能够配置运行环境；
- 是否能够跑通程序；
- 是否能够记录运行结果；
- 是否能够尝试优化；
- 是否能够把过程和结果说明清楚。

所有题目均可在个人电脑、Linux 虚拟机、WSL、本地 Linux 环境或自备服务器中完成。报告中必须说明基础题和大题分别使用的机器环境。电脑性能不足时，可以适当降低测试规模，也可以使用 **Google Colab**、自备服务器或其他自备云计算资源，但需要在报告中说明降低了哪些规模、使用了什么资源，以及结果还代表什么。

## 二、基础题：HPL / HPCG 二选一

选择 HPL 或 HPCG 中的 1 个题目完成即可。

### 题目 1：HPL 性能优化

入口链接：

- 先看：<https://www.netlib.org/benchmark/hpl/>
- 源码下载：<https://www.netlib.org/benchmark/hpl/>
- 调参说明：<https://www.netlib.org/benchmark/hpl/tuning.html>

HPL 是用于测试计算性能的线性方程组求解程序。本题要求在本地环境中编译并运行 HPL，通过调整参数获得更好的性能结果。

需要完成的任务：

1. 下载 HPL 源码。
2. 配置 HPL 运行环境，包括编译器、MPI 和 BLAS 库。
3. 编译并运行 HPL。
4. 修改 `HPL.dat` 参数文件。
5. 至少测试 3 组不同参数。
6. 记录每组参数的运行结果。
7. 对比不同参数对性能的影响。
8. 选择表现最好的一组参数，并说明原因。

每组参数至少记录：

- `N`
- `NB`
- `P x Q`
- 运行命令
- 运行时间
- 性能结果
- 是否通过正确性检查

### 题目 2：HPCG 性能优化

入口链接：

- 先看：<https://github.com/hpcg-benchmark/hpcg>
- 代码仓库：<https://github.com/hpcg-benchmark/hpcg>

HPCG 是用于测试实际科学计算性能的基准程序。相比 HPL，HPCG 更关注内存访问、线程调度和通信效率。本题要求在本地环境中编译并运行 HPCG，通过调整运行配置观察性能变化。

需要完成的任务：

1. 阅读 HPCG README。
2. 配置 HPCG 运行环境。
3. 编译并运行 HPCG。
4. 至少测试 3 组不同配置。
5. 对比不同配置下的性能变化。
6. 总结哪组配置效果最好。

可以调整：

- 问题规模
- MPI 进程数
- OpenMP 线程数
- 线程绑定方式
- 编译优化参数

每组配置至少记录：

- 运行命令
- 问题规模
- MPI 进程数
- OpenMP 线程数
- 运行时间
- GFLOPS
- 结果是否 valid

## 三、大题：任选一题

从以下大题中选择 1 个完成即可。

### 大题 1：Embodied World Model 优化

入口链接：

- 先看：<https://github.com/ASC-Competition/ASC26-Embodied-World-Model-Optimization>
- 赛题仓库：<https://github.com/ASC-Competition/ASC26-Embodied-World-Model-Optimization>
- 项目仓库：<https://github.com/unitreerobotics/unifolm-world-model-action>

本题是具身智能方向的模型推理优化任务。程序需要完成模型加载、数据读取、推理计算和结果保存。本题目标是在保证输出质量满足要求的前提下，尽可能减少程序运行时间。输出质量主要通过 PSNR 进行验证。

需要完成的任务：

1. 阅读赛题仓库 README 和运行说明。
2. 配置 Python / Conda / PyTorch 环境。
3. 跑通 Baseline 程序。
4. 记录 Baseline 运行时间。
5. 记录输出结果和 PSNR。
6. 尝试优化推理流程。
7. 至少完成 3 种优化尝试。
8. 对比优化前后的运行时间和 PSNR。
9. 说明哪些优化有效，哪些优化可能影响结果质量。

可以尝试的优化：

- `model.eval()`
- `torch.no_grad()`
- `torch.inference_mode()`
- FP16 / BF16
- 调整 batch size
- 调整 sampler
- 调整 diffusion steps
- 减少重复加载模型
- 减少重复读取数据
- 减少不必要的日志输出
- 减少中间文件保存
- 优化图片或视频 I/O
- 优化数据预处理流程

至少记录：

- 运行命令
- Baseline 运行时间
- Baseline PSNR
- 优化方法
- 优化后运行时间
- 优化后 PSNR
- 结果是否正常

### 大题 2：AlphaFold3 优化

入口链接：

- 先看：<https://github.com/google-deepmind/alphafold3>
- 代码仓库：<https://github.com/google-deepmind/alphafold3>

本题是陌生 AI 应用优化任务。AlphaFold3 是蛋白质结构预测相关应用，程序运行流程通常包括数据准备、模型推理和结果输出。本题重点考察代码阅读、环境配置、排错、性能分析和优化能力。

需要完成的任务：

1. 阅读 AlphaFold3 README 和安装说明。
2. 配置运行环境。
3. 跑通 Baseline 或官方示例。
4. 记录 Baseline 运行时间。
5. 记录 Baseline 输出结果。
6. 分析程序主要流程。
7. 找出耗时较多的部分。
8. 至少完成 3 种优化尝试。
9. 对比优化前后的运行时间。
10. 保证最终结果仍然正常。

可以尝试的优化：

- 减少重复计算
- 增加缓存
- 优化数据加载
- 优化输入样例和运行流程
- 减少不必要的 I/O
- 减少中间结果保存
- 使用性能分析工具定位瓶颈
- 分离数据准备和模型推理流程
- 整理运行流程
- 整理结果输出和日志

### 大题 3：AMSS-NCKU 数值相对论应用优化

入口链接：

- 先看：<https://github.com/ASC-Competition/AMSS-NCKU>
- 代码仓库：<https://github.com/ASC-Competition/AMSS-NCKU>

本题是科学计算应用优化任务。程序与数值相对论计算相关，包含大量数值计算、网格更新、插值、积分等操作。本题目标是在保证结果正确的前提下，通过调整编译方式、运行参数和并行配置，减少程序运行时间。

需要完成的任务：

1. 阅读 AMSS-NCKU README 和运行说明。
2. 配置编译环境。
3. 编译程序。
4. 跑通 Baseline 或测试样例。
5. 记录 Baseline 运行时间。
6. 记录正确性验证结果。
7. 分析运行流程和输入文件。
8. 至少完成 3 种优化尝试。
9. 对比不同配置下的运行时间。
10. 总结哪种配置效果最好。

可以尝试的优化：

- 调整 MPI 进程数
- 调整 OpenMP 线程数
- 调整进程绑定方式
- 调整线程绑定方式
- 修改编译优化参数
- 使用不同编译器
- 优化运行流程
- 分析 I/O 开销
- 减少不必要的输出
- 对比单进程、多进程、多线程表现

注意事项：

- 不能直接删除主要计算过程。
- 不能为了变快改错核心算法。
- 如果修改源码，需要说明修改位置和原因。
- 如果降低运行规模，需要在报告中说明。

### 大题 4：QiboTN 量子线路模拟优化

入口链接：

- 先看：<https://qibo.science/qibotn/stable/index.html>
- 文档：<https://qibo.science/qibotn/stable/index.html>
- 代码仓库：<https://github.com/qiboteam/qibotn>

本题是量子线路张量网络模拟任务。程序需要模拟不同类型的量子线路，例如 QFT、QAOA、Supremacy 等。本题目标是在 CPU 环境下运行量子线路模拟任务，记录不同规模下的运行时间，并尝试优化总运行时间。

需要完成的任务：

1. 阅读 QiboTN 文档或仓库安装说明。
2. 配置 Python 环境。
3. 安装 QiboTN 相关依赖。
4. 跑通 Baseline 或官方示例。
5. 选择至少一种 workload 进行测试，例如 QFT、QAOA、Supremacy。
6. 测试不同 qubit 数或不同参数规模。
7. 记录每组测试的运行时间和输出状态。
8. 至少完成 3 种优化尝试。
9. 对比优化前后的运行时间。
10. 简单说明 qubit 数增加后运行时间为什么会变长。

可以尝试的优化：

- 调整线程数
- 调整 MPI 进程数
- 限制 BLAS 线程数
- 调整任务运行顺序
- 优化批量运行流程
- 避免重复初始化
- 自动化测试不同 qubit 数
- 记录失败任务并跳过
- 分析内存占用
- 分析不同 workload 的运行差异

注意事项：

- 本题要求使用 CPU 运行。
- 不能修改线路定义来降低难度。
- 不能删除核心计算过程。
- 不能用错误结果冒充优化结果。
- 如果电脑跑不了大规模任务，可以降低 qubit 数，但需要说明。

建议 `results.csv` 格式：

```csv
workload,qubits,command,runtime,status
QFT,8,python xxx.py,1.23,success
QFT,10,python xxx.py,4.56,success
QFT,12,python xxx.py,18.90,success
```

### 大题 5：Group Competition / ICON 综合应用优化

入口链接：

- 先看：<https://www.asc-events.net/StudentChallenge/ASC26/static/Task_Description_of_Group_Competition.pdf>
- ICON 赛题仓库：<https://github.com/ASC-Competition/ASC26-icon>
- Group Competition 任务说明：<https://www.asc-events.net/StudentChallenge/ASC26/static/Task_Description_of_Group_Competition.pdf>

本题是综合应用优化任务。重点不只是单个算法，而是完整的工程流程，包括环境配置、程序运行、workload 管理、结果验证、流程自动化和结果整理。

注意：ICON 仓库使用 Git LFS，下载前需要先安装并启用 Git LFS。

```bash
git lfs install
git clone https://github.com/ASC-Competition/ASC26-icon.git
```

需要完成的任务：

1. 阅读 ICON 赛题仓库和任务说明。
2. 配置运行环境。
3. 跑通 Baseline 或测试样例。
4. 记录原始运行结果。
5. 记录正确性验证结果。
6. 整理应用运行流程。
7. 整理一键运行方式。
8. 整理结果提取方式。
9. 整理运行日志。
10. 至少完成 3 项工程改进或优化尝试。
11. 总结如果正式组队完成该题，应该如何分工。

可以完成的工程改进：

- 整理安装步骤
- 编写 `install.sh`
- 编写 `run_all.sh`
- 编写 `parse_results.py`
- 自动统计运行时间
- 自动检查输出文件是否存在
- 自动生成结果表格
- 整理 README
- 整理报错和解决方案
- 整理 workload 运行顺序
- 整理日志文件
- 减少重复手动操作

可以尝试的优化：

- 调整 CPU 线程数
- 调整 MPI 进程数
- 调整运行参数
- 调整进程绑定
- 调整线程绑定
- 减少重复运行
- 减少不必要的 I/O
- 优化数据读取流程
- 批量处理多个 workload

## 四、统一提交要求

每位同学最终通过邮件提交报告，收件邮箱为 `dotredstone0123@gmail.com`。报告是主要提交物，相关 GitHub 仓库用于复查源码、日志、结果和可复现性。

推荐直接基于所选题目对应的官方仓库完成作业。仓库可以是官方题目仓库的 fork，也可以是本地 clone 后重新推送到个人 GitHub 的仓库。相关仓库用于复查源码修改、日志、结果记录和可复现性。

基础题和大题应分开使用两个相关仓库。基础题仓库用于保存 HPL 或 HPCG 的运行记录，大题仓库用于保存所选大题的代码修改、日志、结果和复现说明。

两个相关仓库都需要设置为 Public，确保报告中的链接可以直接打开。

如果某个官方仓库较大、包含大模型权重、数据集或 Git LFS 文件，也可以为对应题目单独创建轻量整理仓库。轻量整理仓库应包含关键日志、结果记录、复现命令，以及代码修改说明或补丁文件。

如果本地硬件条件不足，可以使用 **Google Colab**、自备服务器或其他自备云计算资源。使用外部资源时，需要在报告中写清资源来源、CPU/GPU 型号、显存、系统环境和是否使用付费资源。Colab 分配到的 GPU/TPU 资源不固定，应以实际运行时记录为准。

两个相关仓库不强制固定目录结构。

两个相关仓库建议使用 `README.md` 或 `SUBMISSION.md` 写明：

- 姓名
- 年级专业
- 对应题目
- 运行环境
- 完成情况
- 复现方式

最终报告只接收 PDF 附件。报告可以使用 Markdown、LaTeX、Word 或其他方式编写，但最后必须导出或编译为 PDF。

报告写作方式不限：

- Word：写完后导出为 PDF；
- Markdown：写完后用编辑器、Pandoc 或其他工具导出为 PDF；
- LaTeX：写完后编译为 PDF。

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

基础题仓库和大题仓库必须设置为 Public，确保评审时无需申请权限即可访问。

报告需要包含：

- 选择的基础题和大题
- 两个题目的主要内容
- 题目链接
- 相关 GitHub 仓库链接
- 基础题和大题的机器环境
- Baseline 如何运行
- Baseline 运行结果
- 优化或工程改进内容
- 优化前后对比
- 正确性验证情况
- 遇到的问题和解决方法
- 对题目的理解
- 后续还可以继续优化的方向

## 五、无效提交情况

以下情况不能视为有效完成：

1. 没有 Baseline，直接报告优化结果。
2. 没有运行命令、日志或结果文件。
3. 只提交截图，没有可复查的文本记录。
4. 没有正确性验证。
5. 输出结果错误但仍宣称优化有效。
6. 一次修改多个变量，却无法说明收益来自哪里。
7. 报告中罗列大量优化名词，但没有实际实验。
8. 仓库内容混乱，无法判断完成的是哪一道题。
9. 运行规模明显降低，但报告中没有说明。
10. 报告内容无法由本人解释。

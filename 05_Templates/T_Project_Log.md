---
date: {{date}}
tags: [experiment, {{type}}]  # type: cfd, code_validation, param_sweep, wind_tunnel
project: "[[{{project_name}}]]"
status: 🔄 running  # 🔄 running → ✅ completed → 📊 analyzed
related_concepts: []  # 链接到被验证的数学/物理概念
---

# {{experiment_title}}

## 🎯 1. 实验目标 (Objective)
> 本次仿真/实验要验证什么假设？回答什么问题？成功标准是什么？

## ⚙️ 2. 配置与参数 (Setup & Parameters)
### 2.1 物理/数学模型
- 控制方程/理论框架：
- 关键假设/简化：

### 2.2 数值/实验设置
| 类别 | 参数 | 值/范围 | 理由 |
|:---|:---|:---|:---|
| 计算域/模型尺寸 | | | |
| 网格/采样 | $N_{cells}$ / $\Delta t$ | | 网格无关性预研 |
| 边界条件 | Inlet/Outlet/Wall | | 物理合理性 |
| 求解器/格式 | Scheme / Relaxation | | 稳定性 vs 精度 |

### 2.3 执行脚本/命令
```bash
# 关键运行命令或入口
$FOAM_RUN/case_name/Allrun
python src/validate_order.py --dx-list 0.1 0.05 0.025
```

## 📈 3. 执行日志 (Execution Log)

|时间|现象/状态|诊断|解决/调整措施|
|---|---|---|---|
|`HH:MM`|残差震荡|松弛因子过大|调整 α=0.7→0.3α=0.7→0.3|
|`HH:MM`|负体积/发散|近壁网格质量差|重构边界层，`checkMesh` 通过|

## 📊 4. 结果与误差分析 (Results & Error Analysis)

### 4.1 关键输出

- **定量指标**：`[CL=0.318, CD=0.012, 残差下降 4 个量级]`
- **核心图表**：
    

### 4.2 误差/不确定性分解

|误差类型|估算值/表现|来源分析|控制策略|
|---|---|---|---|
|离散/截断误差|网格收敛阶 1.92|空间二阶格式|加密网格/验证阶数|
|迭代误差|残差 10−610−6|求解器容差|收紧收敛标准|
|模型误差|与实验偏差 3.5%|湍流模型简化|尝试 SST/RSM 对比|

### 4.3 与理论/文献对比

|指标|本结果|理论/文献值|偏差|原因推断|
|---|---|---|---|---|
|CLCL​|0.318|0.320 (Anderson)|-0.6%|网格分辨率/边界层厚度|

## 🔍 5. 结论与反思 (Conclusions & Reflections)

- **目标达成度**：[✅/⚠️/❌]
- **关键洞察**：_例：近壁 y+<1y+<1 对壁面摩擦阻力预测至关重要。_
- **待改进**：[ ] 尝试更高阶格式（WENO）；[ ] 引入自适应网格（AMR）

## 🔗 6. 知识联结与归档 (KB Links & Deliverables)

- 理论支撑：[[Concept A]], [[Numerical_Scheme_B]]
- 方法复用：此验证流程可迁移至 `[[Next_Project]]`
- **产出物**：
    - 数据：`data/{{date}}_results.csv`
    - 脚本：`src/analysis_plot.py`
    - Git Commit: `feat: validate 2nd-order convergence`
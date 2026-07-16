# MEMS 麦克风阻尼孔与结构优化结果

## 最终方案

- 阻尼孔：单侧 5-3-5 错列分布，孔半径 18 um；相对原 4-3-4 / 20 um 方案，增加泄放路径并减小单孔局部扰动。
- 结构：T_mem=12 um，L_beam=12 um，W_beam=24 um，H_gap=1.8 um，Vbias=8 V。
- 阻尼：频域中采用固体等效损耗因子 eta_s=0.35 表征空气/挤压膜阻尼影响。
- 静电：按准静态平行板偏置场估算电荷输出与拉入裕量；当前参考模型未建立 Maxwell 应力 + 移动网格的强耦合拉入仿真。

## 关键结果

- 一阶模态：34.95 kHz。
- 二阶模态：54.02 kHz，二阶/一阶 = 1.55，二阶没有贴近一阶。
- 20 Hz-20 kHz 频响：相对 1 kHz 范围 -0.01 dB 到 2.90 dB，满足 +/-3 dB。
- 最大 deltaC：0.654 fF/Pa，出现在 20000 Hz。
- 最大 deltaQ：5.234 fC/Pa，Vout 可按 Vout=deltaQ/Cf 换算。
- 1 kHz 标称点：deltaQ=3.750 fC/Pa；Cf=0.3 pF 时理想整机输出约 12.50 mV/Pa，即约 -38.1 dBV/Pa。
- Cf=1 pF 时 1 kHz 仅约 3.75 mV/Pa（-48.5 dBV/Pa）；20 kHz 的 5.23 mV/Pa 是带内最大值，不是标称灵敏度。
- 相对上一版 0.405 fF/Pa，deltaC 最大值提高约 61.5%。
- 静电压力：87.45 Pa；估算静电吸附位移 51.07 nm。
- 拉入裕量：11.75，大于 1，说明 8 V 偏置下工程估算未接近拉入。

## 文件

- COMSOL 模型：mems_microphone_damping_structure_optimized.mph（GitHub 轻量检查版，保留几何、参数、物理场和研究设置，已清除可重建的网格及求解缓存）
- Word 报告：MEMS_microphone_damping_structure_optimized_report_latest.docx
- 数据：eigenfrequencies.csv，frequency_response.csv
- 曲线：frequency_response_displacement.png，frequency_response_deltaC.png，frequency_response_deltaQ.png，frequency_response_flatness_db.png

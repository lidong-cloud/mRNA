#          转录组生信分析

一套针对GEO数据库进行生信分析的分析流程，主要包含数据整理、差异分析、富集分析、相关性分析及差异表达基因的可视化。

## 结果示例

### mRNA_DEG (差异分析)

[Sample_corr_heatmap.pdf](https://github.com/user-attachments/files/33536339/Sample_corr_heatmap.pdf)

[Sample_PCA_correlation.pdf](https://github.com/user-attachments/files/33536342/Sample_PCA_correlation.pdf)

[numbers_of_diff_genes.pdf](https://github.com/user-attachments/files/33536375/numbers_of_diff_genes.pdf)

[volcano_plot.pdf](https://github.com/user-attachments/files/33536379/volcano_plot.pdf)

[heatmap_of_any_diff_genes.pdf](https://github.com/user-attachments/files/33536013/heatmap_of_any_diff_genes.pdf)

[heatmap_of_top_diff_genes.pdf](https://github.com/user-attachments/files/33536386/heatmap_of_top_diff_genes.pdf)

### Volcano & expression (基因表达可视化)

[Normal_VS_Tumor.UBE2C.violin.pdf](https://github.com/user-attachments/files/33537874/Normal_VS_Tumor.UBE2C.violin.pdf)

[Normal_VS_Tumor.TPX2_NEK2_UBE2C_HOXC9_KIF18B.box.pdf](https://github.com/user-attachments/files/33537880/Normal_VS_Tumor.TPX2_NEK2_UBE2C_HOXC9_KIF18B.box.pdf)

### enrich_term & GSEA (富集分析)

[Gene_expr_diff.go.enrich.pdf](https://github.com/user-attachments/files/33537129/Gene_expr_diff.go.enrich.pdf)

[acute_inflammatory_response.GO_0002526.gsea.pdf](https://github.com/user-attachments/files/33537133/acute_inflammatory_response.GO_0002526.gsea.pdf)

### Cor_curce & Cor_point (基因表达相关性)

[Correlation_Ctsk_VS_Spp1_Gm3375.top_0.2.pdf](https://github.com/user-attachments/files/33537521/Correlation_Ctsk_VS_Spp1_Gm3375.top_0.2.pdf)

[Con_VS_Treat.Ctsk_Spp1.correlation.pdf](https://github.com/user-attachments/files/33537529/Con_VS_Treat.Ctsk_Spp1.correlation.pdf)

## 配置环境

大部分脚本为 R 编写，需要安装相应的 R 包。

**基础依赖（所有脚本必需）：**
- R 包：`argparser`

**各脚本所需依赖：**

- **mRNA_DEG**: `stringr`, `ggplot2`, `ComplexHeatmap`, `circle`, `limma`, `dplyr`, `RColorBrewer`
- **Volcano**: `ggplot2`, `stringr`, `dplyr`
- **expression**: `ggplot2`, `rstatix`, `stringr`, `ggforce`, `ggpubr`, `tibble`, `dplyr`
- **enrich_term**: 
  - Python 模块：`multiprocessing`, `argparse`, `time`, `os`, `re`
  - R 包：`ggplot2`, `clusterProfiler`, `ReactomePA`, `dplyr`, `DOSE`, `qs2`
  - 所分析物种的 R 包：`org.Hs.eg.db`, `org.Mm.eg.db`, `org.Rn.eg.db`
- **GSEA**: `clusterProfiler`, `ComplexHeatmap`, `RColorBrewer`, `enrichplot`, `msigdbr`, `ggplot2`, `dplyr`
- **Cor_curve**: `linkcomm`, `reshape2`, `ggplot2`, `ggrepel`, `stringr`, `tibble`, `linkET`, `WGCNA`, `dplyr`
- **Cor_point**: `stringr`, `ggplot2`, `ggpmisc`, `ggpubr`

## 使用方法

1. 所有脚本均需要在 Linux 系统下运行。
2. 给脚本可执行权限：

   ```bash
   chmod 755 mRNA_DEG
3. 查看脚本帮助文档，哪些是脚本必须参数，哪些是可选参数，补全必须参数即可分析。
   
   ```bash
   mRNA_DEG --help
<div align="center">
  <img src="https://github.com/user-attachments/assets/3949e740-d098-47fe-b9ce-8f38745fe015" width="600" alt="运行截图" />
</div>


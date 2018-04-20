# 天津大学本科生毕业论文模版
## 来源
原始版本[tjuthesis](https://code.google.com/archive/p/tjuthesis/)
修改自[xnth97/TJUThesisLatexTemplate](https://github.com/xnth97/TJUThesisLatexTemplate)

## 更新日志
+ 调整了封面校徽的大小使其与Word模版接近
+ 引入了任务书和开题报告
+ 减小目录章节中的空格为两个汉字的宽度
+ 减小了目录中dots的间距
+ 将结论一章改为带编号的普通章节
+ 去掉目录中致谢两字间的空格
+ 汉字使用[思源字体](https://source.typekit.com/source-han-serif/cn/)
+ 调整了公式、图表与文字的间距
+ 参考文献部分全部使用半角符号
+ 将整体代码模块化

## 预览
[天津大学本科生毕业论文](https://github.com/liangzhenduo0608/TJU-thesis-template/blob/master/main.pdf)

## 环境
### macOS
[MacTeX](https://www.tug.org/mactex/) + [Texpad](https://www.texpad.com/)

### Windows
[TexLive](https://www.tug.org/texlive/)

## 基本用法
### 章节
```tex
\chapter{章}
\section{节}
\subsection{小节}
\subsubsection{小小节}
```

### 引用
#### BibTeX
```tex
@article{江泽民1989能源发展趋势及主要节能措施,
  title={能源发展趋势及主要节能措施},
  author={江泽民},
  journal={上海交通大学学报},
  volume={23},
  number={3},
  pages={1--16},
  year={1989},
  language={Chinese}
}
```

#### 上标
```tex
\citeup{江泽民1989能源发展趋势及主要节能措施}
```

#### 行内
```tex
\cite{江泽民2008对中国能源问题的思考}
```

### 图片
```tex
\begin{figure}[htbp!]
	\centering
	\includegraphics[width=0.5\textwidth]{figures/picture.png}
	\caption{图片说明}\label{图片标签}
	\vspace{-1em}
\end{figure}
```

### 表格
```tex
\begin{table}[htbp]
	\caption{表格说明}\label{表格标签}
	\vspace{0.5em}\centering\wuhao
	\begin{tabular}{ccccc}
		\toprule[1.5pt]
		第1列 & 第2列 & 第3列 \\
		\midrule[1pt]
		1.1 & 1.2 & 1.3 \\
		2.1 & 2.2 & 2.3 \\
		3.1 & 3.2 & 3.3 \\
		\bottomrule[1.5pt]
	\end{tabular}
	\vspace{\baselineskip}
\end{table}
```

### 公式
#### 行内公式
```tex
\(G=(V, E)\)
```
#### 行间公式
```tex
$$p_1(v_i, v_j)=\frac{1}{1+\exp(-\overrightarrow{u_i}^T\cdot\overrightarrow{u_j})}$$
```
#### 标号公式
```tex
\begin{align}
	p_2(v_j\mid v_i)=\frac{\exp({\overrightarrow{u_j}'}^T\cdot\overrightarrow{u_i})}{\sum_{k=1}^{|V|}\exp({\overrightarrow{u_k}'^T\cdot\overrightarrow{u_i})}}\label{p2}
\end{align}
```

### 伪代码
```tex
\begin{algorithm}[]
	\SetKwInOut{Input}{输入}
	\SetKwInOut{Output}{输出}
	\caption{\sc DeepWalk\((G, w, d, \gamma, t)\)}\label{DeepWalk}
	\Input{图\(G(V,E)\) \\
		窗大小\(w\) \\
		嵌入维度\(d\) \\
		每个节点游走数\(\gamma\) \\
		游走距离\(t\)
	}
	\Output{节点表征矩阵\(\Phi\in\mathbb{R}^{|V|\times d}\)
	}
	初始化：从\(\mathcal{U}^{|V|\times d}\)采样\(\Phi\) \\
	从\(V\)建立二叉树\(T\) \\
	\For{\(i=0\) to \(\gamma\)}{
		\(\mathcal{O}\) = Shuffle(\(V\)) \\
		\ForEach{\(v_i\in\mathcal{O}\)}{
			\(\mathcal{W}_{v_i}=RandomWalk(G, v_i, t)\) \\
			\(\textsc{SkipGram}(\Phi, \mathcal{W}_{v_i}, w)\)
		}
	}
\end{algorithm}
```

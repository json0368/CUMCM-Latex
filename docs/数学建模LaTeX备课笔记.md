# 数学建模LaTeX备课笔记

## 一、课程概述

### 教学目标
- 让学生掌握数学建模论文的LaTeX排版技能
- 理解LaTeX的基本语法和使用方法
- 熟悉数学建模竞赛论文的格式要求
- 能够独立使用LaTeX完成论文写作

### 课程安排
- **时长**: 2-3课时
- **形式**: 理论讲解 + 实践操作
- **重点**: 模板使用、公式编写、图表制作

---

## 二、LaTeX环境准备

### 1. LaTeX发行版安装
#### Windows系统
- **推荐**: TeXLive（完整版）
- **备选**: MiKTeX
- **在线平台**: Overleaf（无需安装）

#### 其他系统
- **Mac**: MacTeX
- **Linux**: TeXLive

### 2. 编辑器选择
- **TeXstudio** (推荐新手)
- **VSCode** + LaTeX Workshop插件
- **Overleaf** (在线编辑器)

### 3. 编译方式
```bash
# 推荐使用xelatex编译
xelatex filename.tex

# 或使用latexmk自动编译
latexmk -xelatex filename.tex
```

**重要提醒**: 必须使用xelatex，不能用pdflatex！

---

## 三、2025年数学建模模板特点

### 主要变化
1. **取消承诺书**: 不再需要承诺书内容
2. **简化字体设置**: 保证Overleaf等平台直接可用
3. **电子版提交**: 需去掉封面和编号页

### 模板选项
```latex
% 标准版本（带封面）
\documentclass{cumcmthesis}

% 电子版提交（去掉封面和编号页）
\documentclass[withoutpreface,bwprint]{cumcmthesis}
```

---

## 四、模板基本结构详解

### 1. 文档类和基本信息
```latex
\documentclass[withoutpreface,bwprint]{cumcmthesis}

% 论文信息（2025年已不需要填写，但保留结构）
\title{论文标题}
\tihao{A}               % 题号
\baominghao{4321}       % 报名号  
\schoolname{XX大学}
\membera{成员A}
\memberb{成员B} 
\memberc{成员C}
\supervisor{指导老师}
\yearinput{2025}
\monthinput{09}
\dayinput{10}
```

### 2. 摘要部分
```latex
\begin{abstract}
摘要内容...

\keywords{关键词1\quad 关键词2\quad 关键词3}
\end{abstract}
```

### 3. 正文结构
```latex
\section{问题重述}
\section{问题分析}  
\section{模型假设}
\section{符号说明}
\section{模型建立与求解}
\section{模型检验}
\section{结果分析}
\section{模型的推广}
```

---

## 五、重点教学内容

### 1. 数学公式编写

#### 行内公式
```latex
这里有一个行内公式 $E = mc^2$
```

#### 行间公式（无编号）
```latex
\[
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
\]
```

#### 带编号的公式
```latex
\begin{equation}
f(x) = ax^2 + bx + c
\label{eq:quadratic}
\end{equation}

% 引用公式
如式\cref{eq:quadratic}所示...
```

#### 多行公式对齐
```latex
\begin{align}
P &= UI \\
  &= I^2R \\
  &= \frac{U^2}{R}
\end{align}
```

#### 分段函数
```latex
\[
f(x) = \begin{cases}
0 & x < 0 \\
x & 0 \leq x \leq 1 \\
1 & x > 1
\end{cases}
\]
```

#### 矩阵
```latex
\[
\mathbf{A} = \begin{pmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \cdots & a_{mn}
\end{pmatrix}
\]
```

### 2. 图片插入

#### 单图插入
```latex
\begin{figure}[!h]
    \centering
    \includegraphics[width=0.6\textwidth]{图片文件名}
    \caption{图片标题}
    \label{fig:example}
\end{figure}

% 引用图片
如\cref{fig:example}所示...
```

#### 多图并排
```latex
\begin{figure}[!h]
    \centering
    \begin{minipage}[c]{0.45\textwidth}
        \centering
        \includegraphics[width=0.9\textwidth]{图1}
        \subcaption{子图1标题}
        \label{fig:sub1}
    \end{minipage}
    \begin{minipage}[c]{0.45\textwidth}
        \centering
        \includegraphics[width=0.9\textwidth]{图2}
        \subcaption{子图2标题}
        \label{fig:sub2}
    \end{minipage}
    \caption{总标题}
    \label{fig:combined}
\end{figure}
```

**图片使用注意事项**:
- 推荐使用jpg、png格式
- 避免使用bmp格式
- 图片命名用英文，避免中文
- 图片命名要有意义，不要用1,2,3这种

### 3. 表格制作

#### 标准三线表
```latex
\begin{table}[!htbp]
    \caption{表格标题}
    \label{tab:example}
    \centering
    \begin{tabular}{ccc}
        \toprule[1.5pt]
        列标题1 & 列标题2 & 列标题3 \\
        \midrule[1pt]
        数据1,1 & 数据1,2 & 数据1,3 \\
        数据2,1 & 数据2,2 & 数据2,3 \\
        \bottomrule[1.5pt]
    \end{tabular}
\end{table}
```

#### 表格列格式说明
- `c`: 居中对齐
- `l`: 左对齐  
- `r`: 右对齐
- `|`: 添加竖线（一般不建议使用）

### 4. 符号说明表
```latex
\section{符号说明}
\begin{center}
    \begin{tabular}{cc}
        \hline
        \makebox[0.3\textwidth][c]{符号} & \makebox[0.4\textwidth][c]{意义} \\ 
        \hline
        $t$ & 时间变量（s） \\ 
        $v$ & 速度（m/s） \\
        $a$ & 加速度（m/s²） \\
        \hline
    \end{tabular}
\end{center}
```

---

## 六、定理环境使用

模板提供了多种定理环境：

```latex
\begin{definition}
    定义内容
    \label{def:example}
\end{definition}

\begin{theorem}
    定理内容  
    \label{thm:example}
\end{theorem}

\begin{lemma}
    引理内容
    \label{lem:example}  
\end{lemma}

\begin{proof}
    证明过程
\end{proof}

\begin{assumption}
    假设内容
    \label{asu:example}
\end{assumption}
```

---

## 七、参考文献

```latex
\begin{thebibliography}{9}
    \bibitem{ref1}
    作者名. 
    \newblock 文献标题[J].
    \newblock 期刊名, 年份, 卷(期): 页码.
    
    \bibitem{ref2}
    作者名.
    \newblock 书名[M].
    \newblock 出版社, 出版地, 年份.
    
    \bibitem{ref3}
    网址: \url{https://example.com}
\end{thebibliography}
```

引用方法：`\cite{ref1}`

---

## 八、代码展示

### MATLAB代码
```latex
\begin{lstlisting}[language=matlab]
% MATLAB代码示例
function result = myFunction(x, y)
    result = x^2 + y^2;
    plot(x, result);
    title('函数图像');
end
\end{lstlisting}
```

### Python代码  
```latex
\begin{lstlisting}[language=python]
import numpy as np
import matplotlib.pyplot as plt

def solve_equation(a, b, c):
    """求解二次方程"""
    delta = b**2 - 4*a*c
    if delta >= 0:
        x1 = (-b + np.sqrt(delta)) / (2*a)
        x2 = (-b - np.sqrt(delta)) / (2*a)
        return x1, x2
    else:
        return None
\end{lstlisting}
```

---

## 九、常见问题与解决方案

### 1. 编译问题
**问题**: 编译失败或出现乱码
**解决**: 
- 确保使用xelatex编译
- 检查文件编码为UTF-8
- 确保中文字体已安装

### 2. 图片插入问题
**问题**: 图片无法显示
**解决**:
- 检查图片路径是否正确
- 确保图片格式为jpg/png/pdf
- 图片文件名不要包含中文或特殊字符

### 3. 公式编译错误
**问题**: 数学公式报错
**解决**:
- 检查花括号是否配对
- 确保特殊符号前加反斜杠
- 矩阵环境使用正确的分隔符

### 4. 表格格式问题
**问题**: 表格线条不正确
**解决**:
- 使用booktabs包的\toprule, \midrule, \bottomrule
- 避免使用\hline和竖线
- 注意列数与tabular参数匹配

### 5. 中文显示问题
**问题**: 中文无法正常显示
**解决**:
- 确保使用ctex文档类或加载ctex宏包
- 使用xelatex编译器
- 检查系统中文字体

---

## 十、实践演示准备

### 演示内容安排

#### 第一部分：环境搭建（15分钟）
1. 展示Overleaf注册和使用
2. 本地TeXstudio安装演示
3. 模板导入和编译测试

#### 第二部分：基础操作（20分钟）
1. 文档结构解释
2. 摘要和关键词编写
3. 章节组织

#### 第三部分：核心功能（30分钟）
1. 数学公式现场编写
2. 图片插入实操
3. 表格制作演练

#### 第四部分：高级功能（20分钟）  
1. 交叉引用使用
2. 参考文献管理
3. 代码环境使用

#### 第五部分：问题解答（15分钟）
1. 常见错误排查
2. 学生问题解答
3. 额外技巧分享

### 课堂练习题

#### 练习1：基础编写
要求学生编写一个包含以下内容的文档：
- 标题和摘要
- 一个带编号的数学公式
- 一个简单的表格

#### 练习2：综合应用
要求学生完成：
- 插入一张图片并正确引用
- 创建一个符号说明表
- 编写分段函数

#### 练习3：高级功能
要求学生实现：
- 多图并排显示
- 定理环境使用
- 参考文献引用

---

## 十一、课后拓展

### 进阶学习资源
1. **《LaTeX入门》** - 刘海洋著
2. **Overleaf官方文档**: https://www.overleaf.com/learn
3. **LaTeX工作室**: https://www.latexstudio.net
4. **符号查询**: http://detexify.kirelabs.org/

### 建议练习
1. 完成一份完整的数学建模论文模拟
2. 尝试制作复杂的数学公式
3. 学习使用tikz绘图包
4. 掌握BibTeX参考文献管理

### 技巧总结
1. **规范命名**: 文件名、标签名都用英文
2. **版本控制**: 重要修改前备份文件
3. **增量编译**: 经常保存和编译检查错误
4. **模块化**: 长文档可分章节分文件编写

---

## 十二、评价与反馈

### 学习成果检验
- [ ] 能独立安装配置LaTeX环境
- [ ] 掌握基本的LaTeX语法
- [ ] 能编写数学公式和制作表格
- [ ] 会插入图片和管理引用
- [ ] 了解数学建模论文格式要求

### 课程改进方向
1. 根据学生反馈调整教学重点
2. 增加更多实际案例演示
3. 建立课后答疑机制
4. 准备更多练习素材

---

*备注：本备课笔记基于2025年最新数学建模竞赛LaTeX模板制作，请根据实际教学需要进行调整。*

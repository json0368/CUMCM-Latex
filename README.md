# 全国大学生数学建模竞赛论文写作模板（LaTeX版本）

## 编译说明
在当前仓库目录下运行：
```
xelatex --disable-installer -interaction=nonstopmode -halt-on-error -no-shell-escape -file-line-error "aiInstructions.tex"
```
即可生成正文 pdf。

如果 AI 工具使用说明模板，则替换最后的文件名：
```
xelatex --disable-installer -interaction=nonstopmode -halt-on-error -no-shell-escape -file-line-error "example.tex"
```
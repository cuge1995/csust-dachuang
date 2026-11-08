# 长沙理工大学大学生创新训练项目申请书（LaTeX 模板）

## 文件说明

| 文件 | 说明 |
|---|---|
| `dachuang_application.tex` | 主文件，含封面、填写说明、一～八全部栏目 |
| `refs.bib` | 参考文献库（GB/T 7714—2015），含格式示例 |
| `thuthesis-numeric.bst` | 参考文献样式，取自长沙理工大学硕士论文模板 |

## 编译

需要 **XeLaTeX**（不要用 pdfLaTeX），有参考文献时需运行 bibtex：

```bash
xelatex dachuang_application.tex
bibtex  dachuang_application
xelatex dachuang_application.tex
xelatex dachuang_application.tex
```

或一步完成：

```bash
latexmk -xelatex dachuang_application.tex
```

## 环境要求

- TeX Live 2021+ 或较新的 MiKTeX
- 宏包：`ctex`、`fontspec`、`tabularray`、`geometry`、`fancyhdr`、`lastpage`、`xcolor`、`enumitem`、`array`、`natbib`、`tcolorbox`、`url`
- 中文字体：自动检测 macOS（Songti SC 等）或 Windows（SimSun 等），都没有时回退到 TeX Live 自带的 Fandol

修改 `dachuang_application.tex` 第 97 行 `\def\appfontset{auto}` 可强制指定 `windows` / `mac` / `fandol`。

## 填写说明

- **表格字段**：短横线处用 `\blank{内容}`（默认 1.15cm 宽），更短的用 `\sblank{内容}`；指定宽度用 `\blank[3cm]{内容}`。
- **大段正文**：直接替换灰色提示语，或用 `\writingspace{高度}` 留白，写满后可自行删减。
- **隐藏提示语**：定稿时把 `\showhintstrue`（第 159 行）改成 `\showhintsfalse`。
- **参考文献**：条目写进 `refs.bib`，正文用 `\cite{key}` 引用，自动编号；只想列入文献表不引用时用 `\nocite{key}`。
- **注释掉的“年 月 日”**：封面底部如需日期行，取消第 215 行注释即可。

## 注意事项

- `refs.bib` 中前两条是对抗样本主题的示例文献，后三条为格式示例（默认不输出），**提交前请替换为实际文献**。
- 「二、立项依据」使用可跨页长框还原原件，分页处左右框线连续，与 Word 表格跨页效果一致。

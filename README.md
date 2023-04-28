# CCNUthesis
1
## 欢迎使用CCNUthesis（华中师范大学论文模版）

本模版支持华中师范大学数学与统计学学院本硕博毕业论文撰写，基于 [fduthesis](https://github.com/stone-zeng/fduthesis) 编写而成，借助现代 LaTeX 技术，希望达到用户接口简明、内容格式规范和模板样式可定制的统一。

本模板目前支持 XeTeX ，仅支持 UTF-8 编码。

本模版支持在 Windows、Mac、Linux 系统上运行。

在使用 `CCNUthesis` 之前，请阅读 「[lshort-zh-cn](https://ctan.math.illinois.edu/info/lshort/chinese/lshort-zh-cn.pdf)」 学习 LaTeX 基本知识，并仔细阅读模版中的用户手册 `CCNUthesis-doc.pdf` 和 [wiki](https://gitee.com/xkwxdyy/CCNUthesis/wikis/%E7%94%A8%E6%88%B7%E5%BF%85%E8%AF%BB)

## 模版的核心组成

- 核心文档类
  - `CCNUthesis.cls`
- 参考文献格式文件
  - `gb7714-CCNU.bbx`
  - `gb7714-CCNUay.bbx`
  - `gb7714-CCNU.cbx`
- 参考文献数据库
  - `CCNUthesis-main.bib`
- 使用示例
  - `main.tex`

### 使用示例

```latex
% \documentclass[type = bachelor]{CCNUthesis}
% \documentclass[type = master]{CCNUthesis}
% \documentclass[type = master, version = print-master-twoside]{CCNUthesis}
\documentclass[type = doctor]{CCNUthesis}
% \documentclass[type = doctor, version = print-doctor-twoside]{CCNUthesis}


% type
% 学术类型
%   可选选项：bachelor|master|doctor
%     默认：bachelor

% version
% 文档版本
%   可选选项：electronic|print-master-oneside|print-master-twoside|
%           print-doctor-twoside
%     默认：electronic
%     electronic：电子版，无空白页
%     print-master-oneside：打印版，硕士，无空白页，单面打印
%     print-master-twoside：打印版，硕士，有空白页，双面打印
%     print-doctor-twoside：打印版，博士，有空白页，双面打印


% 加载用户的个人信息和论文相关参数设置的配置文件
\input{ccnu-setup.tex}


% 需要的额外宏包可以在此处自行调用
%   关于模版已经载入的宏包请参看手册「宏包依赖情况」
\usepackage{mathtools}



% 需要的命令环境可以自行定义
\newcommand{\upe}{\mathrm{e}}   % 直立的e，用于表示常量，如自然常数      
\newcommand{\upi}{\mathrm{i}}   % 直立的i，用于表示常量，如虚数单位


\begin{document}


% \frontmatter 开启论文前置部分
% 前置部分包含目录、中英文摘要以及符号表等
\frontmatter


% 摘要
%   适用学位类型：【本｜硕｜博】
\input{./front/abstract.tex}


% 符号表
%   适用学位类型：【本｜硕｜博】
%   不需要的话将 \input{./front/notation.tex} 注释掉或删除
\input{./front/notation.tex}



% \mainmatter 进入论文主体部分
\mainmatter


% 主体采用多文件编译的方式
% 即把每一章放进一个单独的 tex 文件里，并在这里用 \input 导入
% 例如 \input{./body/chapter1.tex}
% 表示插入 main.tex 所在目录中的 body 目录下的 chapter1.tex 文件

% 正文
% 适用学位类型：【本｜硕｜博】
\input{./body/chapter1.tex}
\input{./body/chapter2.tex}
\input{./body/chapter3.tex}
\input{./body/chapter4.tex}



% 论文后文部分，参考文献、致谢、附录等
\backmatter


% 参考文献
%********************************************
% 行内引用：\parencite{} or \parencite[]{}，下面两个情况要用行内引用
%    - 去掉这个引用句子结构不完整，比如“定理证明可参看[1]”
%    - 英文文献的引用
% 上标引用：\cite{} or \cite[]{}，下面情况要用上标引用
%    - 去掉这个引用，句子结构完整，比如“作者提到，‘CCNUthesis 真是一个好模版。’^[1]”
%      其中“^[1]” 表示上标引用
%********************************************

% 输出参考文献
%   适用学位类型：【本｜硕｜博】
%   无须用户进行任何操作
%   用户要想正确输出参考文献：
%     1. 在 bib 文件中输入正确的参考文献条目信息
%     2. 在正文中正确地使用 \parencite 或 \cite 引用
%     3. 使用 xelatex-biber-xelatex*2 编译链或 latexmk 方式编译 main.tex 文件
\printbibliography


% 附录
% 【硕｜博】附录在致谢前
\include{./back/appendix.tex}

% 攻读学位期间取得的研究成果（博）
% \include{./back/publications.tex}


% 致谢
\include{./back/acknowledgements.tex}


% 附录
% 【本】附录在致谢后
% \include{./back/appendix.tex}


\end{document}
```


## 重要提醒

1. 本模板未经学校相关部门审核及授权，使用前请务必斟酌。
2. 本模板仍处于开发中，不保证接口的稳定性。在撰写论文的过程中，请慎重考虑是否要同步进行更新。
3. 任何由于使⽤本模板⽽引起的论⽂格式审查问题均与本模板作者⽆关。


## 感谢

- 特别感谢 [hushidong](https://github.com/hushidong) 对 `CCNUthesis.bbx` 和 `CCNUthesis.cbx` 提供的定制帮助！
- 感谢 [zepinglee](https://github.com/zepinglee), [syvshc](https://github.com/syvshc) 在 `CCNUthesis` 编写过程中提供的帮助
- 感谢 [stone-zeng](https://github.com/stone-zeng) 开发的 [fduthesis](https://github.com/stone-zeng/fduthesis)

## 贡献

如果您有任何改进意见或者功能需求，欢迎提交 [issue](https://gitee.com/xkwxdyy/CCNUthesis/issues) 或 [pull request](https://gitee.com/xkwxdyy/CCNUthesis/pulls)。

## 仓库地址

Github：https://github.com/xkwxdyy/CCNUthesis

Gitee：https://gitee.com/xkwxdyy/CCNUthesis

## 参考资料

- 华中师范大学2018级理科毕业论文（设计）排版模式
- 华中师范大学理科毕业论文（设计）LaTeX模版（邓国泰）
- [研究生学位论文规范](http://gs.ccnu.edu.cn/info/1049/1398.htm)

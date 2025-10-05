# QLoRA-Tex

\documentclass{article}
\usepackage[utf8]{inputenc}
\usepackage{amsmath, amssymb}
\usepackage{geometry}
\usepackage{hyperref}
\usepackage{fancyvrb} % For verbatim environment

% Adjust margins for a cleaner look
\geometry{a4paper, margin=1in}
\linespread{1.2}

\title{FormulaFast: An Efficient Multimodal Adapter for Mathematical \texorpdfstring{$\LaTeX$}{} OCR}
\author{Fine-Tuning Qwen2-VL-7B with \texorpdfstring{\textsuperscript{\text{unsloth}}}{}}
\date{\today}

\begin{document}

\maketitle
\thispagestyle{empty}

\section*{Project Description: FormulaFast (Qwen-VL Math OCR Adapter)}

This project details the development of a highly specialized, efficient \textbf{Mathematical OCR} (Optical Character Recognition) model, \texttt{FormulaFast}, based on the open-source \texttt{Qwen2-VL-7B-Instruct} Vision Language Model.

The core objective is to achieve near-perfect conversion of images containing complex mathematical equations directly into accurate \LaTeX\ source code.

\section*{Key Features and Technology}

\begin{tabular}{|p{3cm}|p{8.5cm}|p{4cm}|}
\hline
\textbf{Feature} & \textbf{Description} & \textbf{Performance Goal} \\
\hline
\textbf{Specialized Task} & \textbf{Image-to-LaTeX Code Generation:} Fine-tuned to recognize mathematical structure, symbols, subscripts, and fractions, and output the precise \LaTeX\ string. & $\text{NED} < 0.05$ (Less than 5\% character error rate). \\
\hline
\textbf{Base Model} & \textbf{Qwen2-VL-7B-Instruct (Multimodal):} A powerful open-source model processing both image pixels and textual instructions. & Leverages strong pre-trained understanding. \\
\hline
\textbf{Efficiency Method} & \textbf{\textsuperscript{\text{unsloth}} QLoRA Adaptation:} Uses \texttt{unsloth} with QLoRA (\textbf{4-bit} quantization) for rapid and resource-efficient fine-tuning. & Minimal Memory Usage (T4 GPU), updating only $\sim 1\%$ of weights. \\
\hline
\textbf{Training Data} & \texttt{unsloth/Latex\_OCR} Dataset: Comprehensive dataset of mathematical images paired with correct \LaTeX\ representations. & Maximize accuracy on diverse equation styles. \\
\hline
\end{tabular}

\section*{Current Performance Snapshot}

Based on initial $50$-step training and evaluation on $100$ test samples:

\begin{itemize}
    \item \textbf{Average Normalized Edit Distance (NED):} \textbf{0.1860}
    \item \textbf{Average Character Accuracy:} \textbf{81.40\%}
\end{itemize}

The initial training phase has successfully stabilized the model's core function. The next steps will focus on extending the training run to drastically lower the $\text{NED}$ toward the project goal of production-ready accuracy.

\end{document}

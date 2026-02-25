\documentclass[12pt]{article}
\usepackage{amsmath}
\usepackage{graphicx}
\usepackage{hyperref}
\usepackage{geometry}
\geometry{margin=1in}

\title{COVID-19 vs Normal Chest X-Ray Classification Using Transfer Learning}
\author{Your Name \\ 
B.Tech Electrical and Electronics Engineering \\ 
CGPA: 8.89 \\ 
IITM BS Data Science Foundation Level}
\date{}

\begin{document}

\maketitle

\section{Introduction}

This project focuses on binary classification of chest X-ray images into COVID-19 and Normal categories using deep learning techniques. The primary objective was to implement and understand an end-to-end computer vision pipeline using transfer learning while analyzing model behavior and generalization performance.

\section{Dataset}

The dataset consists of labeled chest X-ray images belonging to two classes:
\begin{itemize}
    \item COVID-19
    \item Normal
\end{itemize}

Images were resized to match model input dimensions and normalized. The dataset was divided into training, validation, and test sets. Data augmentation techniques such as rotation, zoom, and horizontal flipping were applied to improve generalization.

\section{Methodology}

\subsection{Model Architecture}

Transfer learning was implemented using MobileNetV2 pretrained on ImageNet. The base model was loaded without the top classification layers.

The following layers were added:
\begin{itemize}
    \item Global Average Pooling
    \item Dense layer
    \item Dropout layer
    \item Final sigmoid activation layer
\end{itemize}

Initially, the base layers were frozen and only the top layers were trained.

\subsection{Training Configuration}

\begin{itemize}
    \item Loss Function: Binary Crossentropy
    \item Optimizer: Adam
    \item Early Stopping: Based on validation loss
\end{itemize}

\section{Results}

The model achieved a test accuracy of 92.67\%. Performance was evaluated using confusion matrix, precision, recall, and F1-score.

Transfer learning significantly improved performance compared to training from scratch. Overfitting was observed in early experiments and mitigated using dropout and data augmentation.

\section{Discussion}

This project provided practical exposure to:
\begin{itemize}
    \item Transfer learning workflows
    \item Feature extraction in convolutional neural networks
    \item Model evaluation beyond accuracy
    \item Effects of hyperparameter tuning
\end{itemize}

It also strengthened understanding of how pretrained models leverage hierarchical feature representations.

\section{Limitations and Future Work}

\begin{itemize}
    \item Limited dataset size
    \item No interpretability techniques implemented
    \item No clinical validation
\end{itemize}

Future improvements include fine-tuning deeper layers, experimenting with alternative architectures, and implementing Grad-CAM for interpretability.

\end{document}

---
layout: page
title: "Sundries"
crawlertitle: "Sundries"
permalink: /sundries/
---

# Sundries

*"Simplicity is a great virtue but it requires hard work to achieve it and education to appreciate it."* — Edsger W. Dijkstra

This page contains miscellaneous tools, code snippets, and resources that I find useful in my research and daily work.

## Coding Toolbox

### MATLAB Utilities

**Channel Coding Toolbox**
```matlab
function ber = polar_decode_scl(y, N, K, L)
    % Successive Cancellation List decoder for Polar codes
    % y: received signal, N: code length, K: info bits, L: list size
    % Implementation details...
end

function G = polar_generator_matrix(N, frozen_bits)
    % Generate polar code generator matrix
    % N: code length, frozen_bits: indices of frozen bits
    F = [1 0; 1 1];  % Kernel matrix
    G = 1;
    for i = 1:log2(N)
        G = kron(G, F);
    end
end
```

**Signal Processing Snippets**
```matlab
% Kalman Filter implementation
function [x_est, P_est] = kalman_update(x_pred, P_pred, y, H, R)
    S = H * P_pred * H' + R;
    K = P_pred * H' / S;
    x_est = x_pred + K * (y - H * x_pred);
    P_est = (eye(size(K,1)) - K * H) * P_pred;
end

% AWGN channel simulation
function y = awgn_channel(x, snr_db)
    snr_linear = 10^(snr_db/10);
    noise_power = var(x) / snr_linear;
    y = x + sqrt(noise_power) * randn(size(x));
end
```

### Python Tools

**Deep Learning for Communications**
```python
import torch
import torch.nn as nn
import numpy as np

class PolarEncoder(nn.Module):
    """Neural Polar Encoder"""
    def __init__(self, N, K):
        super(PolarEncoder, self).__init__()
        self.N = N
        self.K = K
        self.fc1 = nn.Linear(K, 128)
        self.fc2 = nn.Linear(128, 256)
        self.fc3 = nn.Linear(256, N)
        self.relu = nn.ReLU()
        
    def forward(self, x):
        x = self.relu(self.fc1(x))
        x = self.relu(self.fc2(x))
        x = torch.tanh(self.fc3(x))
        return x

# Usage example
def train_polar_encoder(model, dataloader, epochs=100):
    optimizer = torch.optim.Adam(model.parameters())
    criterion = nn.MSELoss()
    
    for epoch in range(epochs):
        for batch_idx, (data, target) in enumerate(dataloader):
            optimizer.zero_grad()
            output = model(data)
            loss = criterion(output, target)
            loss.backward()
            optimizer.step()
```

**Information Theory Calculations**
```python
def channel_capacity(snr_db):
    """Calculate AWGN channel capacity"""
    snr_linear = 10**(snr_db/10)
    return 0.5 * np.log2(1 + snr_linear)

def mutual_information(X, Y):
    """Estimate mutual information between X and Y"""
    from sklearn.feature_selection import mutual_info_regression
    return mutual_info_regression(X.reshape(-1, 1), Y)[0]

def polar_channel_reliability(N, snr_db):
    """Calculate polar channel reliabilities"""
    # Density evolution for polar codes
    # Implementation details...
    pass
```

## LaTeX Templates

### IEEE Conference Paper Template
```latex
\documentclass[conference]{IEEEtran}
\usepackage{amsmath,amsfonts,amssymb}
\usepackage{algorithm,algorithmic}
\usepackage{graphicx}

\title{Your Paper Title Here}
\author{
    \IEEEauthorblockN{Geon Choi}
    \IEEEauthorblockA{
        Com-X Laboratory, Department of Electrical Engineering\\
        POSTECH, South Korea\\
        Email: geon.choi@postech.ac.kr
    }
}

\begin{document}
\maketitle
\begin{abstract}
Your abstract here.
\end{abstract}
\end{document}
```

### Theorem Environment Setup
```latex
\usepackage{amsthm}
\newtheorem{theorem}{Theorem}
\newtheorem{lemma}[theorem]{Lemma}
\newtheorem{proposition}[theorem]{Proposition}
\newtheorem{corollary}[theorem]{Corollary}
\theoremstyle{definition}
\newtheorem{definition}[theorem]{Definition}
\newtheorem{example}[theorem]{Example}
```

## Research Tools

### Useful Software & Libraries
- **MATLAB**: Signal Processing Toolbox, Communications Toolbox
- **Python**: NumPy, SciPy, PyTorch, TensorFlow, Matplotlib
- **LaTeX**: Overleaf, MiKTeX, TeXstudio
- **Reference Management**: Zotero, Mendeley
- **Version Control**: Git, GitHub

### Online Resources
- [Information Theory Society](https://www.itsoc.org/) - Latest news in information theory
- [IEEE Xplore](https://ieeexplore.ieee.org/) - Academic paper database
- [arXiv](https://arxiv.org/) - Preprint repository
- [MATLAB Central](https://www.mathworks.com/matlabcentral/) - Code sharing platform

## Configuration Files

### VS Code Settings for LaTeX
```json
{
    "latex-workshop.latex.tools": [
        {
            "name": "pdflatex",
            "command": "pdflatex",
            "args": ["-interaction=nonstopmode", "-file-line-error", "%DOC%"]
        }
    ],
    "latex-workshop.latex.recipes": [
        {
            "name": "pdflatex",
            "tools": ["pdflatex"]
        }
    ]
}
```

### Git Configuration
```bash
# Useful Git aliases
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.unstage 'reset HEAD --'
git config --global alias.last 'log -1 HEAD'
git config --global alias.visual '!gitk'
```

## Quick References

### Common Mathematical Notation
- **Channel capacity**: $C = \max_{p(x)} I(X;Y)$
- **Mutual information**: $I(X;Y) = H(X) - H(X|Y)$
- **Entropy**: $H(X) = -\sum_{x} p(x) \log p(x)$
- **SNR conversion**: $\text{SNR}_{\text{dB}} = 10 \log_{10}(\text{SNR}_{\text{linear}})$

### MATLAB Shortcuts
- `Ctrl+I`: Auto-indent selection
- `Ctrl+R`: Comment/uncomment
- `F5`: Run script
- `F9`: Run selection
- `Ctrl+D`: Open/close dock

---

*Last updated: {{ site.time | date: "%B %Y" }}*
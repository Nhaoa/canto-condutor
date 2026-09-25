# O Problema do Canto Condutor: Simulação Interativa e Transposição Informática

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Nhaoa/canto-condutor/blob/main/cantoscondutores.ipynb)
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/Nhaoa/canto-condutor/HEAD?urlpath=voila%2Frender%2Fcantoscondutores.ipynb)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Lab%20%2F%20Lite-orange.svg)](https://jupyter.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Este repositório contém o ambiente didático interativo desenvolvido para o estudo físico e matemático da **Equação de Laplace aplicada a cantos condutores concorrentes** sob ângulo diedro $\beta$[cite: 1, 3]. 

O projeto integra a comunicação científica:  
> **"TRANSPOSIÇÃO INFORMÁTICA E INTELIGÊNCIA ARTIFICIAL NO ENSINO DE FÍSICA: O CANTO CONDUTOR NO JUPYTER LAB"**  
> *Apresentado na 14ª Semana Acadêmica de Castanhal (UEPA 2026).*[cite: 2]

---

## 📌 Visão Geral do Problema

A configuração estuda dois planos condutores mantidos a potencial nulo ($V = 0$) que se intersectam formando um ângulo diedro $\beta$[cite: 1]. A solução analítica da Equação de Laplace ($\nabla^2 \Phi = 0$) em coordenadas polares $(\rho, \phi)$ estabelece que o comportamento do campo elétrico $\vec{E}$ e da densidade superficial de carga $\sigma$ próximo ao vértice ($\rho \to 0$) é governado pelo expoente geométrico de escala[cite: 1]:

$$\gamma(\beta) = \frac{\pi}{\beta} - 1$$

| Regime Geométrico | Ângulo $\beta$ | Expoente $(\pi/\beta) - 1$ | Comportamento ($\rho \to 0$) | Fenómeno Físico |
| :--- | :---: | :---: | :---: | :--- |
| **Canto Convexo** | $\beta < 180^\circ$ | Positivo ($> 0$) | $\vert{}\vec{E}\vert{} \to 0, \sigma \to 0$ | Espalhamento de campo / Blindagem eletrostática[cite: 1, 3] |
| **Superfície Plana** | $\beta = 180^\circ$ | Nulo ($= 0$) | $\vert{}\vec{E}\vert{} = \text{const}, \sigma = \text{const}$ | Campo uniforme (Capacitor de placas paralelas)[cite: 1, 3] |
| **Canto Côncavo** | $\beta > 180^\circ$ | Negativo ($< 0$) | $\vert{}\vec{E}\vert{} \to \infty, \sigma \to \infty$ | Compressão de campo / Efeito para-raios[cite: 1, 3] |
| **Aresta Viva** | $\beta \to 360^\circ$ | $-0.5$ | Singularidade $\rho^{-1/2}$ | Descarga corona extrema em lâmina condutora[cite: 1, 3] |

---

## 🚀 Funcionalidades do Simulador

- **Exploração Dinâmica em Tempo Real:** Variação contínua do ângulo $\beta$ entre $20^\circ$ e $359^\circ$ com resposta gráfica imediata via `ipywidgets`[cite: 3].
- **Visualização de Campo e Potencial:** Traçado das setas do campo vetorial $\vec{E} = -\nabla\Phi$ com mapa perceptual de cores (*plasma*) sobreposto às linhas equipotenciais[cite: 1, 3].
- **Transição Crítica em $\beta = 180^\circ$:** Comutação automática para malha cartesiana no ponto crítico, exibindo linhas de campo paralelas e verticais em direção à placa condutora[cite: 1, 3].
- **Salvaguarda de Singularidades (`mag_safe`):** Estabilização numérica que previne divisões por zero na vizinhança da origem para regimes divergentes[cite: 3, 4].
- **Retroação Didática Responsiva:** Geração dinâmica de descrições textuais explicativas em HTML adaptadas instantaneamente ao valor selecionado de $\beta$[cite: 3].

---

## 🛠️ Como Executar

### 1. Online (Sem necessidade de instalação)
- **Modo Aplicação Web (Voilà via MyBinder - Recomendado):**  
  Clique em [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/Nhaoa/canto-condutor/HEAD?urlpath=voila%2Frender%2Fcantoscondutores.ipynb) para interagir diretamente com o simulador, sem exibição do código-fonte.
- **Modo Caderno Interativo (Google Colaboratory):**  
  Clique em [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Nhaoa/canto-condutor/blob/main/cantoscondutores.ipynb) e execute as células sequencialmente (`Ctrl + F9`).

### 2. Localmente (Terminal / JupyterLab)
```bash
# Clonar o repositório
git clone [https://github.com/Nhaoa/canto-condutor.git](https://github.com/Nhaoa/canto-condutor.git)
cd canto-condutor

# Criar e ativar o ambiente virtual (opcional)
python -m venv venv
source venv/bin/activate  # No Windows: venv\Scripts\activate

# Instalar dependências
pip install -r requirements.txt

# Iniciar o ambiente
jupyter lab

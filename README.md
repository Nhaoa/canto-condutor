# O Problema do Canto Condutor: Simulação Interativa e Transposição Informática

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Nhaoa/canto-condutor/blob/main/cantoscondutores.ipynb)
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/Nhaoa/canto-condutor/main?urlpath=voila%2Frender%2Fcantoscondutores.ipynb)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Lab%20%2F%20Lite-orange.svg)](https://jupyter.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Este repositório contém o ambiente didático interativo desenvolvido para o estudo físico e matemático da **Equação de Laplace aplicada a cantos condutores concorrentes** sob ângulo diedro $\beta$[cite: 1, 3]. 

O projeto é parte do artigo científico:  
> **"TRANSPOSIÇÃO INFORMÁTICA E INTELIGÊNCIA ARTIFICIAL NO ENSINO DE FÍSICA: O CANTO CONDUTOR NO JUPYTER LAB"**  
> *Apresentado na 14ª Semana Acadêmica de Castanhal (UEPA 2026).*[cite: 2]

---

## 📌 Visão Geral do Problema

A configuração estuda dois planos condutores infinitos mantidos a um potencial constante $V$ que se intersectam formando um ângulo $\beta$[cite: 1]. A solução analítica da Equação de Laplace ($\nabla^2 \Phi = 0$) em coordenadas polares $(\rho, \phi)$ revela que o comportamento do campo elétrico $\vec{E}$ e da densidade superficial de carga $\sigma$ próximo ao vértice ($\rho \to 0$) é governado pelo expoente geométrico[cite: 1]:

$$\gamma(\beta) = \frac{\pi}{\beta} - 1$$

| Regime Geométrico | Ângulo $\beta$ | Expoente $(\pi/\beta) - 1$ | Comportamento ($\rho \to 0$) | Fenômeno Físico |
| :--- | :---: | :---: | :---: | :--- |
| **Canto Convexo** | $\beta < 180^\circ$ | Positivo ($> 0$) | $\vert{}\vec{E}\vert{} \to 0, \sigma \to 0$ | Espalhamento de campo / Blindagem de quinas[cite: 1, 3] |
| **Superfície Plana** | $\beta = 180^\circ$ | Nulo ($= 0$) | $\vert{}\vec{E}\vert{} = \text{const}, \sigma = \text{const}$ | Campo homogêneo (Capacitor de placas paralelas)[cite: 1, 3] |
| **Canto Côncavo** | $\beta > 180^\circ$ | Negativo ($< 0$) | $\vert{}\vec{E}\vert{} \to \infty, \sigma \to \infty$ | Compressão de campo / Efeito para-raios[cite: 1, 3] |
| **Aresta Viva** | $\beta \to 360^\circ$ | $-0.5$ | Singularidade $\rho^{-1/2}$ | Descarga corona extrema[cite: 1, 3] |

---

## 🚀 Funcionalidades do Simulador

- **Exploração Dinâmica em Tempo Real:** Variação contínua do ângulo $\beta$ entre $20^\circ$ e $359^\circ$ via controle deslizante (*slider*) ou inserção numérica direta.
- **Visualização de Campo e Potencial:** Traçado dinâmico das setas do campo vetorial $\vec{E} = -\nabla\Phi$ com mapa de cores perceptual (*plasma*) e linhas equipotenciais em sobreposição[cite: 1, 3].
- **Transição Crítica em $\beta = 180^\circ$:** Alternância automática para malha cartesiana retangular na superfície plana, exibindo linhas de campo paralelas e verticais[cite: 1, 3].
- **Salvaguarda de Singularidades (`mag_safe`):** Estabilização algorítmica para evitar divisões por zero nas proximidades do vértice em regimes divergentes[cite: 3, 4].
- **Painel Didático Responsivo:** Geração dinâmica de descrições textuais explicativas em HTML vinculadas instantaneamente ao valor de $\beta$[cite: 3].

---

## 🛠️ Como Executar

### 1. Online (Sem necessidade de instalação)
Você pode executar o simulador diretamente no navegador através de qualquer uma das opções:

- **Via Voilà / MyBinder (Recomendado - Interface limpa de aplicativo):**  
  Clique no selo [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/SEU-USUARIO/SEU-REPOSITORIO/main?urlpath=voila%2Frender%2Fcantoscondutores.ipynb) para abrir a interface pronta sem exibição de células de código.
- **Via Google Colab:**  
  Clique no selo [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SEU-USUARIO/SEU-REPOSITORIO/blob/main/cantoscondutores.ipynb) e execute todas as células (`Ctrl + F9`).

### 2. Localmente (JupyterLab clássico)
Clone o repositório e instale as dependências:

```bash
# Clonar o repositório
git clone https://github.com/Nhaoa/canto-condutor.git
cd canto-condutor

# Criar e ativar o ambiente virtual (opcional)
python -m venv venv
source venv/bin/activate  # No Windows: venv\Scripts\activate

# Instalar as dependências
pip install -r requirements.txt

# Iniciar o JupyterLab
jupyter lab

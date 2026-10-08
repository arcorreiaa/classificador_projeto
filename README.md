# classificador_projeto

*Em partidas de alto elo, dez minutos de jogo já contam uma história — este repositório pergunta se um classificador consegue lê-la antes do fim.*

---

## Contexto acadêmico

Trabalho entregue na disciplina **Machine Learning, Deep Learning e IA Generativa**, componente da especialização em **Engenharia de Software, Inteligência Artificial e IoT** (Faculdade **Esuda**), sob orientação do **Prof. Kelvin Frade**.

**Alysson Rychard**

O enunciado propõe construir, comparar e criticar classificadores supervisionados. O repositório responde a esse pedido com um caso concreto: **inferir o vencedor de uma partida de League of Legends** a partir do retrato estatístico dos primeiros dez minutos — momento em que macro, pressão de mapa e economia já se desenham, mas o resultado ainda está em aberto.

---

## O problema

| Dimensão | Definição |
|----------|-----------|
| **Fonte** | [Diamond Ranked Games (10 min)](https://www.kaggle.com/datasets/bobbyscience/league-of-legends-diamond-ranked-games-10-min) — partidas ranqueadas (Diamond I–Master), via Riot API |
| **Alvo** | `blueWins` — vitória do time azul (1) ou vermelho (0) |
| **Entrada** | Dezenas de sinais numéricos (combates, ouro, visão, objetivos, ritmo por minuto) |
| **Natureza** | Classificação binária balanceada, adequada a métricas clássicas e à leitura de viés treino/teste |

A escolha do domínio é deliberada: e-sport de alta dimensionalidade tática, porém com features tabulares — o tipo de terreno onde modelos interpretáveis e ensembles ainda dialogam com rigor estatístico, antes de se recorrer a arquiteturas profundas.

---

## Abordagem metodológica

O fluxo reproduz o ciclo que se espera em produção de modelos, em escala didática:

1. **Compreensão dos dados** — distribuição de classes, sanidade de intervalos, ausências, tipos.
2. **Partição estratificada** — separação treino/teste para avaliação honesta.
3. **Dois paradigmas** — *Regressão Logística* (fronteira linear, baseline transparente) e *Random Forest* (não linearidade e interações).
4. **Refino** — normalização, PCA (redução de dimensionalidade), *grid search* de hiperparâmetros.
5. **Crítica** — acurácia, precisão, recall, F1, matrizes de confusão e distância entre desempenho em treino e teste (overfitting).

O artefato central é o notebook `classificador_projeto.ipynb`, estruturado conforme o template da disciplina, incluindo reflexões de bônus sobre explicabilidade em deep learning e sobre criação em IA generativa.

---

## Repositório e artefatos

O nome **`classificador_projeto`** é exigência do enunciado (identificador da avaliação, independente do tema LoL).

```
classificador_projeto/
├── classificador_projeto.ipynb   # pipeline completo, visualizações e conclusões
└── README.md
```

O notebook é **autossuficiente**: na primeira execução, obtém o CSV de um espelho público do Kaggle se o arquivo local ainda não existir — pensado para rodar no **Google Colab** sem dependência de caminhos ou máquinas específicas.

---

## Reprodução

**Colab** — abra o notebook, conecte um runtime Python e execute todas as células (*Runtime → Run all*). Na primeira rodada, é necessário acesso à internet para o download dos dados; a busca em grade nos modelos pode levar alguns minutos.

**Local** — ambiente com Python 3.10+, `pandas`, `numpy`, `matplotlib`, `seaborn` e `scikit-learn`; em seguida, abra o `.ipynb` no Jupyter ou VS Code.

A entrega prevê o notebook **já executado**, com saídas e gráficos materializados, versionado neste repositório GitHub.

---

## Referência

*League of Legends Diamond Ranked Games (10 min)* — [Kaggle](https://www.kaggle.com/datasets/bobbyscience/league-of-legends-diamond-ranked-games-10-min). Dados derivados da Riot API; agregação ao décimo minuto de partida; documentação e licença conforme a página do dataset.

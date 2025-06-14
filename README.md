# Dashboard de Vendas – Dados de Assinaturas Xbox

## 📊 Visão Geral
Este projeto demonstra um **dashboard de vendas e assinaturas** construído inteiramente no **Microsoft Excel**. Partindo de dados transacionais brutos, transformamos números em insights visuais interativos que ajudam as equipes a compreender rapidamente tendências de desempenho, comportamento do cliente e alavancas de receita.

> **Objetivo:** Exibir boas práticas de organização de um mini‑projeto de analytics — da matéria‑prima ao painel final — e fornecer instruções claras para qualquer pessoa reproduzir ou expandir o trabalho.

## 📑 Conjunto de Dados
Arquivo: **`DashXbox.xlsx`**  
Abas principais:
| Aba        | Finalidade |
|------------|------------|
| `Bases`    | Dados brutos de assinaturas (uma linha por cliente ou renovação) |
| `Calculos` | Colunas auxiliares & métricas (Ano‑Mês, MRR, flags de churn...) |
| `Dashboard`| Tabelas dinâmicas, segmentações e gráficos organizados para exibição |
| `Planilha3`| (Opcional) Espaço de rascunho |

Campos‑chave:
* **Subscriber ID** – identificador único do cliente
* **Plan** – Core / Standard / Ultimate
* **Subscription Type** – Mensal / Trimestral / Anual
* **Start Date** – data de início da assinatura (dd‑mm‑aaaa)
* **Auto Renewal** – indicador Sim/Não
* **EA Play Season Pass**, **Minecraft Season Pass** – add‑ons (booleanos)
* Colunas monetárias: `Subscription Price`, `… Pass Price`, `Coupon Value`, `Total Value`

> **Dica:** Todas as datas são armazenadas como valores de data reais do Excel, permitindo agrupamento em tabelas dinâmicas.

## 🔧 Como Reproduzir o Dashboard
1. **Clone** o repositório
   ```bash
   git clone https://github.com/<seu‑usuario>/excel‑dashboard‑vendas.git
   cd excel‑dashboard‑vendas
   ```
2. **Abra** `data/DashXbox.xlsx` no Excel 2019 ou Microsoft 365.
3. **Habilite** conteúdo/macros se solicitado (o arquivo não usa VBA, mas a ativação garante total interatividade).
4. **Atualize** as Tabelas Dinâmicas: *Dados ▶ Atualizar Tudo* (ou clique direito em qualquer pivot ▶ *Atualizar*).
5. **Explore** a aba **Dashboard**:
   * Segmentações de *Plan*, *Subscription Type* e *Auto Renewal* filtram todos os gráficos simultaneamente.
   * KPIs no topo (Receita Total, Assinantes Ativos, ARPU, Churn) se ajustam instantaneamente.
   * Gráfico de linha exibe a Receita Recorrente Mensal (MRR).
   * Barras empilhadas mostram penetração de add‑ons (EA Play vs Minecraft) por plano.

## 🔍 Como Funciona (Resumo Técnico)
| Etapa        | Técnica | Detalhes |
|--------------|---------|----------|
| **Prep. Dados** | Tabela + colunas calculadas | Ano‑Mês, MRR, ReceitaAddOns,  etc. criadas na aba `Calculos`. A aba `Bases` é convertida em Tabela (`Ctrl+T`) para intervalo dinâmico. |
| **Modelagem**  | Tabelas Dinâmicas | Uma pivot por visual. Métricas formatadas (#.##0;-#.##0). |
| **Visuais**    | Gráficos Dinâmicos + KPIs | 
| **Interatividade** | Segmentações | Conectadas a todas as pivots para filtro cruzado. |


## 🔄 Atualizando com Novos Dados
1. Acrescente linhas ao final da Tabela **`Bases`** — não quebre o intervalo da Tabela.
2. As colunas derivadas em `Calculos` se autocompletam.
3. *Dados ▶ Atualizar Tudo* — pivots, gráficos e KPIs se renovam.

## 📝 Licença
MIT – use à vontade, mas mencione os autores.

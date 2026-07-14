# Análise de Campanhas de Marketing e Comportamento do Cliente

Projeto desenvolvido no **Microsoft Power BI** para analisar o perfil dos clientes, seus hábitos de consumo e o desempenho de campanhas de marketing.

O relatório foi dividido em quatro páginas, permitindo estudar o cliente sob diferentes perspectivas: perfil, comportamento de compra, resposta às campanhas e padrões de consumo por país.

---

## Objetivo

O dashboard busca responder perguntas como:

- Qual é o perfil dos clientes da empresa?
- Quais canais concentram mais compras?
- Existe relação entre renda e gasto?
- Como filhos, escolaridade e estado civil influenciam o consumo?
- Qual foi o resultado da campanha analisada?
- Quais grupos apresentam maior potencial de conversão?
- Como os gastos variam por categoria, país e ano?

---

## Dados

A base `dados_marketing.csv` contém:

- **2.000 clientes**
- **27 campos**
- **7 países**
- Cadastros realizados entre **2018 e 2023**
- Informações demográficas, financeiras, comportamentais e de campanhas

Entre os campos analisados estão:

- Escolaridade e estado civil
- Salário anual
- Filhos e adolescentes em casa
- Gastos por categoria
- Compras por canal
- Visitas ao site
- Participação em campanhas
- Resultado final da campanha
- País do cliente

---

## Metodologia

O projeto foi desenvolvido nas seguintes etapas:

1. Importação do arquivo CSV
2. Validação dos tipos de dados
3. Análise da qualidade da base
4. Criação da medida de gasto total
5. Definição das perguntas de negócio
6. Escolha dos visuais adequados
7. Construção das quatro páginas do relatório
8. Validação das agregações e interações

### Medida principal

O gasto total consolida as seis categorias de consumo:

```DAX
TotalGasto =
    SUM(DadosMarketing[Gasto com Eletronicos]) +
    SUM(DadosMarketing[Gasto com Brinquedos]) +
    SUM(DadosMarketing[Gasto com Moveis]) +
    SUM(DadosMarketing[Gasto com Utilidades]) +
    SUM(DadosMarketing[Gasto com Alimentos]) +
    SUM(DadosMarketing[Gasto com Vestuario])
```

---

## Páginas do dashboard

### 1. Visão Cliente

<img width="929" height="545" alt="Captura de tela 2026-07-14 151514" src="https://github.com/user-attachments/assets/e9df54e8-3631-4592-a899-ae49631b24b3" />

Apresenta:

- Total de clientes
- Salário médio anual
- Compras em loja, web, catálogo e com desconto
- Clientes por escolaridade
- Clientes por estado civil
- Filtro por país

Essa página oferece uma visão geral do público atendido e dos canais de compra mais utilizados.

### 2. Visão Comportamento

<img width="927" height="532" alt="Captura de tela 2026-07-14 151551" src="https://github.com/user-attachments/assets/c365bb7d-0437-49e0-8bd2-77a69b7486e5" />

Analisa:

- Relação entre salário anual e gasto total
- Gasto total por quantidade de filhos
- Gasto total por adolescentes em casa
- Decomposição do gasto por escolaridade e estado civil

O objetivo é identificar fatores associados ao comportamento de consumo.

### 3. Visão Campanhas

<img width="928" height="536" alt="Captura de tela 2026-07-14 151615" src="https://github.com/user-attachments/assets/5298663a-ba0c-46e5-abcf-2e4362dc7d97" />

Apresenta:

- Resultado da campanha
- Salário médio de quem comprou e de quem não comprou
- Visitas ao site por perfil de cliente
- Relação entre filhos e resposta à campanha
- Detalhamento por escolaridade, estado civil e país

Essa página ajuda a reconhecer grupos com maior potencial de resposta.

### 4. Visão Pontos de Venda

<img width="927" height="537" alt="Captura de tela 2026-07-14 151651" src="https://github.com/user-attachments/assets/79f51b83-e108-48a6-afce-66a337201230" />

Compara:

- Gastos por categoria e país
- Quantidade de clientes por país
- Evolução do gasto total por ano
- Diferenças de consumo entre mercados

---

## Principais indicadores

| Indicador | Resultado |
|---|---:|
| Clientes | 2.000 |
| Conversão da campanha | 16% |
| Gasto total | 1.204.871 |
| Gasto médio por cliente | 602,44 |
| Salário médio anual | 52.290,85 |
| Compras em loja | 11.595 |
| Compras na web | 8.150 |
| Compras via catálogo | 5.271 |
| Compras com desconto | 4.665 |

---

## Insights encontrados

- **320 clientes responderam positivamente à campanha**, correspondendo a uma taxa de conversão de 16%.
- Clientes que compraram apresentaram gasto médio de aproximadamente **969**, enquanto os demais tiveram média próxima de **533**.
- O salário médio dos clientes convertidos foi de aproximadamente **59,5 mil**, superior aos **50,9 mil** dos não convertidos.
- A maior parte dos gastos está concentrada em **eletrônicos** e **móveis**.
- As compras em lojas físicas superaram web, catálogo e compras com desconto.
- Clientes sem filhos em casa apresentaram gasto médio superior aos clientes com um ou dois filhos.
- Os Estados Unidos concentram a maior quantidade de clientes da base.

---

## Qualidade e limitações dos dados

Durante a análise, identifiquei pontos que precisam ser considerados:

- 19 registros sem salário anual
- Anos de nascimento atípicos, como 1893 e 1899
- Um valor de salário anual muito superior aos demais
- A variável `Comprou` registra apenas o resultado final, sem informar o valor financeiro gerado pela conversão
- A base possui uma única tabela, sem modelo dimensional

Esses pontos não impedem explorar, mas acredito que devem ser investigados antes de utilizar o relatório em uma decisão real.

---

## Como você pode visualizar

1. Baixe o arquivo `CampanhaDeMarketing.pbix`
2. Abra no Microsoft Power BI Desktop
3. Navegue pelas quatro páginas do relatório
4. Utilize o filtro de país e interaja com os gráficos

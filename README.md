# Análise de Dados no Mercado de Trabalho: Da Coleta à Decisão Estratégica

Bem-vindo(a)! Esta oficina foi projetada para ser sua porta de entrada ao universo dos dados. Aqui, você aprenderá na prática os conceitos fundamentais que movem o mercado de trabalho, passando pelas áreas de Engenharia, Ciência e Análise de Dados.

Ao final desta jornada, você terá compreendido o ciclo de vida de um projeto de dados: desde a modelagem e tratamento do dado bruto com código PySpark até a construção de um dashboard interativo e funcional no Power BI.

## Nosso Ponto de Partida: O Dataset

Os dados utilizados em toda a oficina foram extraídos a partir de um dataset público cadastrado no Kaggle. No entanto, fizemos algumas mudanças em alguns arquivos para tornar a oficina mais dinâmica e conseguir extrair um potencial maior das ferramentas utilizadas.

- Para o download do banco de dados original, é possível acessar o link: [https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).
- Para o download dos dados modificados, é possível acessar os arquivos na pasta `/content`.

## Estágio Inicial: Preparação dos dados

Para conseguir fazer um dashboard performático, é crucial o corte de colunas e linhas "inúteis" para a aplicação final, além de manter as informações bem estruturadas e com tipagem adequada.

Para fazer nosso dashboard, optamos em estruturar os dados seguindo o modelo [Star Schema](https://www.databricks.com/glossary/star-schema), onde separamos o dado em dois tipos de tabela: fato e dimensão.

### Diferenciando uma tabela fato de uma tabela dimensão

O modelo que é implementado desde a década de 1990 assume esses dois tipos de tabela para ter uma informação com as informações "base" e outra com todas as demais informações úteis.

- **Dimensão (Quem, O Quê, Onde)**: Modelo de tabela responsável por armazenar as informações básicas e descritivas das aplicações. No contexto de e-commerce, por exemplo, seria uma tabela com as informações dos produtos, clientes, fornecedores, métodos de pagamento, etc. São dados que não são modificados com tanta recorrência.
- **Fato (O Que Aconteceu)**: Tabela com todas as informações de todas as atualizações que são feitas dentro do negócio. Por exemplo, uma tabela de transações, pedidos, movimentações de estoque, etc.

![Star Schema - Exemplo Databricks](assets/star_schema_databricks.png)
fonte: Databricks

<hr>

Para essa oficina, foram criadas cinco tabelas, que serão conectadas no BI:

| Tabela               | Tipo     | Descrição                                        |
| -------------------- | -------- | ------------------------------------------------ |
| `dim_clientes`       | Dimensão | Informações sobre cada cliente.                  |
| `dim_fornecedores`   | Dimensão | Informações sobre cada vendedor (seller).        |
| `dim_geolocalizacao` | Dimensão | Dados de nomes das cidades de cada CEP.          |
| `dim_produtos`       | Dimensão | Detalhes e categorias de cada produto.           |
| `ft_pedidos`         | Fato     | Registro central de todos os pedidos realizados. |

### Tratamento com PySpark

Para transformar nossos dados brutos em tabelas limpas e estruturadas, usaremos PySpark, a API de Python para Apache Spark.

#### Por que o PySpark?

- Sintaxe Amigável: É fácil de aprender para quem já conhece Python e SQL.
- Alta Performance: Processa grandes volumes de dados de forma distribuída e paralela, otimizando a execução do código automaticamente.
- Padrão de Mercado: É uma das ferramentas mais requisitadas em Engenharia de Dados.

Trabalharemos na plataforma [Google Colab](https://colab.research.google.com/). Para agilizar, preparamos um notebook documentado com toda a estrutura base.

- Acesse o template aqui: `assets/notebook_base.ipynb`.

## Criação do Dashboard

Para a criação do dashboard, é necessário apenas o download do Power BI e os arquivos `.csv`.

### Passo-a-passo Para Iniciar a Criação dos Gráficos

- Abra o Power BI e, na tela inicial, crie um `Relatório em branco`.
  ![Relatório em Branco](assets/criacao-bi/relatorio-em-branco.png)
- Vá para a guia Página Inicial e clique em `Transformar dados`. Isso abrirá o editor do Power Query.
  ![Selecionar Transformar Dados](assets/criacao-bi/selecionar-transformar-dados.png)
- No Power Query, clique com o botão direito na área de `Consultas` > `Nova Consulta` > `Texto/CSV`.
  ![Transformar Dados](assets/criacao-bi/transformar-dados.png)
- Após importar todas as tabelas, clique em `Fechar e Aplicar` no canto superior esquerdo.
  ![Fechar e Aplicar](assets/criacao-bi/fechar-aplicar.png)
- Vá para a `Exibição de modelo` (o terceiro ícone na barra vertical esquerda) para verificar se o Power BI criou os relacionamentos entre a tabela fato e as dimensões corretamente. Ajuste se necessário.
  ![Exibição Modelo Semântico](assets/criacao-bi/exibicao-modelo-semantico.png)

# Organizadores

- **Jean Lucas Hoffelder**

  - Estudante de Análise e Desenvolvimento de Sistemas no IFRS - Feliz.
  - Desenvolvedor de TI na Tramontina Multi S.A.
  - **Instagram:** [@jeanlucashoffelder](https://www.instagram.com/jeanlucashoffelder)

- **Otávio João Maldaner**
  - Estudante de Análise e Desenvolvimento de Sistemas no IFRS - Feliz.
  - Desenvolvedor de TI na Tramontina Multi S.A.
  - **Instagram:** [@otavio.maldaner](https://www.instagram.com/otavio.maldaner)

<hr>
Bom Princípio - RS | 09/08/2025

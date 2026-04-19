
# SEÇÃO 2: TRANSFORMAÇÃO/TRATAMENTO DOS DADOS

Nessa seção detalharei as ferramentas utilizadas no tratamento e manutenção dos dados, antes de enviar ao banco de dados.

## 1. Visualização do Documento

O principal trabalho e, provavelmente, o maior desafio, é a manutenção e tratamento dos dados. Isso garante a integridade e legibilidade dos dados. 

Como demonstrado na seção 1 no tópico de imagens, as tabelas do Bacen apresentam um padrão bastante característico: 
- A tabela é em formato horizontal.
- Existem títulos e subtítulos. 


Caso já tenha familiaridade com banco de dados ou construção de Dashboards, provavelmente detectou o principal problema desses dados: legibilidade.

Normalmente, para garantir uma leitura e manipulação dos dados de forma coesa, as tabelas são verticais.

Vejamos um exemplo:

*TABELA HORIZONTAL*

| Nome  | João      | Maria      | Helena  |
|-------|-----------|------------|---------|
| Idade | 25        | 30         | 26      |
| Cargo | Atendente | Cozinheira | Gerente |

*TABELA VERTICAL*

| Nome   | Idade | Cargo      |
|--------|-------|------------|
| João   | 25    | Atendente  |
| Maria  | 30    | Cozinheira |
| Helena | 26    | Gerente    |

Comparando ambas, a horizontal pode parecer mais atrativa a olho nú. Contudo, para legibilidade e manutenção dos dados, a vertical é mais adequada. Isso porque, os softwares tendem a compreender melhor dados dispostos de forma verticial do que horizontal.

Tendo identificado isso, podemos seguir para o tratamento.

## 2. Manutenção via PowerQuery
Provavelmente, é a parte mais trabalhosa e cansativa do projeto. Isso porque, decide trabalhar com o arquivo em formato csv, sendo assim, tive que salvar as tabelas em arquivos diferentes e tratá-las individualmente. *O csv não permite várias abas em um mesmo arquivo.*

Além disso, é relevante salientar a escolhe de utilizar o PowerQuery ao invés de efetuar uma edição manual. No trabalho diário, é comum que existam outras entradas além das existentes, com isso, o Query garante que qualquer nova entrada esteja com a modelação que foi estruturada.

Enfim, vou citar as funções que utilizei para transformar os dados disso:

![Cartão de Crédito por parcelamento e Quantidade](./Imagens/Banco-Dados2.png)

Para isso:

![Cartão de Crédito por parcelamento e Quantidade](./Imagens/Dados-Limpos2.png)

### Funções:

-  **UNPIVOT**: Essa função transforma colunas horizontais em veticais. 
- **FUNÇÕES TABLE DA LINGUAGEM M**: Por se tratar de uma manutenção em toda a tabela, utilizei o editor avançado e as funções *Table*, algumas foram: Table.RenameColumns; Table.TransformColumnTypes; dentre outros.
-  **SPLIT BY DELIMITER**: É possível fazer tanto na Liguagem M ou ir nas opções da aba *Página Inicial*.

## Ferramentas Utilizadas
![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
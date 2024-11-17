# Relatório - CAPSTONE

Este relatório é sobre as aplicações do CRISP-DM em um conjunto de dados sobre as ODS, que são os Objetivos de Desenvolvimento Sustentáveis do governo. Nesse caso, eu escolhi a ODS 4, que aborda educação e qualidade. Os dados foram retirados do site: [TCE - Dados Abertos](https://dadosabertos.tce.go.gov.br/).  

O tema dos meus dados são sobre o índice de alfabetização no Brasil, e tem como objetivo, o aumento de pessoas alfabetizadas com o passar dos anos.

## Compreensão do Projeto

Este é um projeto semestral da matéria banco de dados na universidade FEI (Fundação Educacional Inaciana Padre Sabóia de Medeiros), nessa atividade realizarei uma análise de dados no meu data-set, onde aborda o índice de alfabetização no Brasil, nele será realizado o método de CRISP-DM. 

## Definição do Problema

O obejtivo do meu trabalho é a aplicação correta do CRISP-DM em meu conjunto de dados.

O conjunto de dados para este projeto é do repositório [TCE - Dados Abertos](https://dadosabertos.tce.go.gov.br/dataset/taxa-de-alfabetizacao-de-pessoas-de-15-anos-ou-mais-de-idade). Ele contém informações sobre o índice de alfabetização no Brasil, baseado em dados sobre a ODS 4 onde fala sobre a educação e qualidade.  

## Escopo

- O escopo dessa amostra é criar um conjunto de dados sólidos com base no modelo CRISP-DM, que possa ser bem compreendido por todos.
- Executei a importação dos dados, compreensão, entendimento, preparção, modelagem, validação e por final a conclusão dos dados.
- Métodos ultilizados: limpeza de dados, label enconding, implementação de dados através da média da coluna, regressão linear, criação de gráficos no Power BI.

## Plano 

O meu conjunto de dados tem como plano de prever um aumento na porcentagem brasileira de alfabetizados durante o passar dos anos, e tem como foco atingir mais de 95% de sua população alfabetizada até 2025.


![image](https://github.com/user-attachments/assets/a9d38bf0-fd90-427f-9655-ea2d8860477e)

## 2. Compreensão dos Dados

Esses dados foram extraídos do banco de dados do [TCE - Dados Abertos](https://dadosabertos.tce.go.gov.br/).

Há um total de 7 colunas e 364 linhas, após a realização do CRISP-DM.

CARACTERÍSTICAS: Granularidade Geográfica, Categoria, Localidade, UF, Ano, Valor, Indicador.

## 3. Modelagem

### Processo ETL

**Limpeza de dados**: Removi linhas e colunas que não foram úteis, que ajuda na compreensão dos meu dados, facilitando a sua vizualição.

Colunas removidas: Filtro, Estado, Tipo Valor.

**Implementação de Dados e Substituição**: Na coluna localidade, tinha alguma linhas onde não estavam preenchidas como estado, apenas estava escrito região ou Brasil, para uma compreensão melhor, substitui a região por Brasil, tendo assim uma melhor correlação de dados. Após isso implementei dados na coluna UF, em que todas as linhas que estava em braco eu coloquei a abreviação de Brasil (BR), onde ajuda uma melhor visualização dos dados.

**Label Enconding**: o Label Enoconding é um método que atribui cada categoria a um número inteiro único, nesse caso apliquei essa forma nas minhas colunas categoria e localidade.

- Coluna categoria: Total = 0

- Coluna Localidade: Brasil = 0, Estado = 1.

**Média para Substituição**: Na coluna Valor, onde é apresentado os dados da porcentagem de alfabetização, tinhas valores nulos em 2020 e em 2021, então eu fiz a média dos valores dos anos anteriores e preenchi as linhas em branco de 2020, após isso refiz o mesmo processo já com as linhas de 2020 preenchidas e depois preenchi as linhas de 2021.

- Código para 2020:  =MÉDIA(F1:F298)
- Código para 2021:  =MÉDIA(F1:F332)

**Regressão Linear**: Regressão é um método estatístico que permite modelar relações entre uma variável dependente e uma ou mais variáveis ​​independentes. Uma análise de regressão permite inferir ou prever outra variável com base em uma ou mais variáveis.

Aplicação: Foram aplicadas a regressão linear na coluna F e na Coluna E.

- Intervalo y : Coluna F, onde apresenta a taxa de alfabetização dos estudantes brasileiros.
- Intervalo x: Coluna E, apresenta os anos.


























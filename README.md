Teste de Aptidão para a vaga de Analista de Sistemas - Solution Delivery
===

## Sumário

- [Observações Gerais](#observações-gerais)
- [Estrutura do projeto](#estrutura-do-projeto)
- [Sobre o Teste](#sobre-o-teste)
- [Observações](#observações)

A Neoway está com uma vaga para Analista de Sistemas para atuar em Floripa.
A equipe de Solution Delivery da Neoway trabalha na construção de ferramentas e soluções que facilitam a gestão e execução dos processos dos nossos clientes, agregando valor aos seus negócios.
Utilizamos principalmente banco de dados relacional (PostgreSql) no nosso dia-a-dia.
Além disto, trabalhamos também com o desenvolvimento de soluções utilizando tecnologias web para oferecer dados via APIs e WebApps. Por isso, o candidato que tiver em seus skills o domínio de golang, mongodb, docker, elastic search, nodejs, javascript terá um plus em seu processo de triagem.

## Observações Gerais

O candidato terá que acessar este repositório, clonar a estrutura do projeto, para então realizar a construção do mesmo em sua máquina local.
Ao término do teste o candidato terá que subir o projeto em seu perfil no github e enviar o link para marcos.alessandro@neoway.com.br.
O candidato terá 3 dias para realizar o teste, contados a partir do contato com nosso RH. 

Serão analisados 4 pontos para avaliar a aptidão do candidato a vaga
- A capacidade do candidato na interpretação e desenvolvimento do que foi solicitado;
- Manipulação dos dados;
- Percepção de qual o melhor tipo de modelagem para o problema proposto;
- Entrega dos arquivos gerados como output.

## Estrutura do projeto

```
teste_sd
    └───files
         ├───outputs
         └───spreadsheets
```

**files**

Pasta para servir como repositório dos arquivos. Nela temos as pastas:
- outputs -> receberá os arquivos gerados nos itens 1,2 e 3.
- spreadsheets -> possuí as bases que disponibilizamos para o teste;

## Sobre o Teste

Disponibilizamos algumas bases de dados (em formato .csv), para que o candidato possa realizar o seu trabalho de análise dos dados neles contidos e em seguida traçar uma estratégia de modelagem e apresentação. Estas bases estao em teste_sd\files\spreadsheets\
Nesta pasta temos uma base de dados cadastrais de 10.000 empresas, dados de lat e long, qtd veículos, flags, setores, ramos de atividade, CNAES, etc.
- O candidato terá que pegar todos os arquivos e importá-los em um banco de dados relacional (de preferência o PostgreSql). O intuito disto é verificar o conhecimento e estratégia do candidato ao escolher como realizar a importação dos arquivos. Este procedimento é requisito obrigatório para o teste (Dica: preferimos código às facilidades fornecidas pelas ferramentas clientes de banco de dados);

1 - (Obrigatório) Precisamos das seguintes análises em um arquivo EXCEL (quando for o caso, separar em outra aba):

    - Total Geral de empresas;
    - Total de empresas matrizes;
    - Total de empresas filiais;
    - Total de empresas optantes pelo simples e simei;
    - Total de empresas públicas;
    - Total de empresas privadas;
    - Total de empresas ativas;
    - Total de empresas baixadas;
    - Total de empresas mistas;
    - Total de Empresas por UF;
    - Total de Empresas por Município;
    - Total de Empresas por faixa de veículos (leves + pesados) -> 0 a 5, 6 a 10, 11 a 15, 16 a 30, 31 a 50, > 50;
    - Total de Empresas por nível e atividade;
    - Total de Empresas por data de abertura;
    - Total de Empresas por Ramos de Atividade (do arquivo Setores e Ramos de Atividade);
    - Total de Empresas por CNAE Principal (tabela, onde CNAE principal tem número de ordem = 0)

2 - (Obrigatório) Com as importações realizadas, precisamos também das seguintes informações em um CSV (apenas empresas ATIVAS):
    
    - CNPJ
    - Razão Social
    - Matriz (sim/não)
    - Data de Abertura
    - CNAE Principal
    - Descrição CNAE Principal
    - CNAE Secundário 1
    - Descrição CNAE Secundário 1
    - CNAE Secundário 2
    - Descrição CNAE Secundário 2
    - CNAE Secundário 3
    - Descrição CNAE Secundário 3
    - Ramo de Atividade (do arquivo Setores e Ramos de Atividade);
    - Saúde Tributária
    - Nível de Atividade
    - Total de Veículos (leves + pesados)

3 - (Não é obrigatório mas um grande diferencial) Ainda precisamos de um arquivo CSV contendo todos os CNPJs que estão a um raio de 15 Km da empresa "JRM COMERCIO DE ARTIGOS DO VESTUARIO LTDA ME" e suas respectivas distâncias.

4 - (Não é obrigatório mas um grande diferencial) Precisamos de uma API onde possamos passar um CNPJ e a Data de Abertura de uma empresa e como resposta obter um JSON com as seguintes informações:

    - CNPJ
    - Razão Social
    - Matriz (sim/não)
    - Data de Abertura
    - CNAE Principal
    - Descrição CNAE Principal
    - CNAEs Secundários
    - Saúde Tributária
    - Nível de Atividade
    - Latitude
    - Longitude
  
  Os requisitos da API são:
- Código em Golang;
- MongoDB - O candidato terá que importar os arquivos necessários, cada um para uma collection no mongoDB;
- Docker (um ou mais containers);
- Incluir a API no github do candidato, na mesma estrutura dos outros itens.

## Observações
	
- É recomendada a utilização de código SQL para a etapa de ETL;
- O arquivo CNAE apresenta 3 campos multivalorados, ou seja, possui mais de um valor em uma coluna. Devido a isto, o candidato deverá realizar o tratamento destes campos, fazendo com que estes campos deixem de ser multivalorados;
- Dúvidas podem ser tiradas por e-mail.

### Aos cadidatos, tenham um ótimo teste :D ### 

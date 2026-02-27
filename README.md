# MetodoAWS-problema-farmac-utico-
Projeto em andamento.

# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

**Data:** 27 de Fevereiro de 2026  
**Empresa:** Abstergo Industries  
**Responsável:** Juhani Otso Berg (Diretor de Operações da Divisão de Pesquisa Histórica)

---

## Introdução

Este relatório apresenta o processo de implementação de ferramentas na empresa Abstergo Industries, realizado por Juhani Otso Berg. O objetivo do projeto foi elencar 3 serviços AWS, com a finalidade de realizar diminuição de custos imediatos na hospedagem e operação do nosso **Sistema de Rastreamento de Artefatos (SRA)**, desenvolvido em **Java/Spring Boot**.

---

## Descrição do Projeto

O projeto de implementação de ferramentas foi dividido em 3 etapas, focando na:

- Conteinerização da API Spring Boot  
- Otimização do Banco de Dados Relacional  
- Armazenamento inteligente de arquivos de pesquisa  

A seguir, serão descritas as etapas do projeto:

---

## Etapa 1 — Amazon EC2 (Instâncias Spot) com Auto Scaling

**Foco da ferramenta:**  
Redução drástica de custos computacionais (até 90% de desconto).

**Descrição do caso de uso:**  
Nossa API em Spring Boot processa grandes lotes de dados de memórias genéticas extraídas do Animus. Como esses processamentos em lote são flexíveis e podem ser interrompidos e retomados, utilizaremos instâncias EC2 Spot para rodar os contêineres Java.

O Auto Scaling garantirá que as máquinas só rodem quando houver dados na fila para serem processados.

**Benefícios principais:**

- Redução extrema de custos computacionais  
- Escalabilidade automática  
- Uso eficiente de recursos  

---

## Etapa 2 — Amazon Aurora Serverless v2 (PostgreSQL)

**Foco da ferramenta:**  
Otimização de custos de banco de dados e escalabilidade sob demanda.

**Descrição do caso de uso:**  
Utilizado como o Banco de Dados principal do nosso backend Java para armazenar:

- Coordenadas de localização dos Fragmentos do Éden  
- Registros de agentes  

Como as buscas por artefatos têm picos imprevisíveis, o Aurora Serverless ajusta a capacidade do banco em milissegundos, fazendo a Abstergo pagar apenas pela capacidade consumida.

**Benefícios principais:**

- Pagamento sob demanda  
- Escalabilidade automática  
- Eliminação de custos com servidores ociosos  

---

## Etapa 3 — Amazon S3 com Intelligent-Tiering

**Foco da ferramenta:**  
Redução de custos de armazenamento de longo prazo.

**Descrição do caso de uso:**  
A API Spring Boot faz upload de:

- Manuscritos antigos  
- Fotos  
- Relatórios de campo em PDF  

O S3 Intelligent-Tiering monitora automaticamente o padrão de acesso e move arquivos não utilizados para camadas de armazenamento mais baratas, como o S3 Glacier.

**Benefícios principais:**

- Redução automática de custos  
- Armazenamento otimizado  
- Sem necessidade de gerenciamento manual  

---

## Conclusão

A implementação das ferramentas AWS na empresa Abstergo Industries proporcionará:

- Redução estimada de **45% nos custos operacionais de TI**
- Modelo de pagamento sob demanda (Serverless)
- Armazenamento inteligente e automatizado
- Maior eficiência operacional

Recomenda-se a continuidade da utilização das ferramentas implementadas e a avaliação constante de novas tecnologias para melhoria contínua dos processos.

---

## Anexos

- Diagrama de Arquitetura AWS (Spring Boot + EC2 + Aurora + S3)
- Planilha de estimativa de custos (AWS Pricing Calculator)
- Documentação da API Swagger (Endpoints de rastreamento de artefatos)

---

## Assinatura do Responsável pelo Projeto

**Juhani Otso Berg**  
Diretor de Operações  
Divisão de Pesquisa Histórica  
Abstergo Industries

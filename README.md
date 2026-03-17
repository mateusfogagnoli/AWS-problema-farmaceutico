# ☣️ BioHazard Monitoring System (BMS)
### **Property of Umbrella Corporation - Research & Development Division**
**Project Classification: TOP SECRET / LEVEL 4 CLEARANCE**

---

## 📝 Introdução

O **BioHazard Monitoring System (BMS)** é uma plataforma centralizada de monitoramento e controle de bioagentes, desenvolvida para gerenciar o ciclo de vida de pesquisas virais, incidentes laboratoriais e documentação científica da **Umbrella Corporation**.

O sistema foi projetado para substituir infraestruturas legadas, focando em **alta disponibilidade**, **segurança de dados** e **otimização de custos operacionais** através de uma arquitetura nativa em nuvem (AWS).

> [!WARNING]  
> O acesso a este repositório é restrito. Qualquer tentativa de acesso não autorizado disparará automaticamente o protocolo de contenção da Red Queen.

---

## 🛠️ Stack Tecnológica

O BMS utiliza tecnologias de ponta para garantir que o monitoramento de bioagentes seja ininterrupto:

* **Linguagem:** Java 21
* **Framework:** Spring Boot 3.x
* **Gerenciador de Dependências:** Maven
* **Banco de Dados:** PostgreSQL (Amazon Aurora)
* **Ambiente de Desenvolvimento:** Ubuntu 24.04 LTS (Noble Numbat)
* **IDE:** Intellij

---

## ☁️ Implementação de Serviços AWS

Para viabilizar as operações globais, o projeto implementa três serviços estratégicos focados em eficiência e redução de custos:

### 1. Amazon EC2 (Instâncias Spot) + Auto Scaling
* **Finalidade:** Processamento de sequenciamento genético e simulações de mutação em larga escala (T-Virus e variantes).
* **Benefício:** Redução de até **90%** nos custos computacionais, utilizando a capacidade ociosa da AWS para processamentos em lote (Batch).

### 2. Amazon Aurora Serverless v2 (PostgreSQL)
* **Finalidade:** Persistência de registros críticos de amostras, dados de laboratórios e logs de incidentes biológicos.
* **Benefício:** Ajuste automático de capacidade conforme a demanda (ex: picos durante auditorias ou contenções), garantindo pagamento apenas pelo que é consumido.

### 3. Amazon S3 (Intelligent-Tiering)
* **Finalidade:** Armazenamento de relatórios científicos, imagens microscópicas e evidências de campo (PDFs e mídias).
* **Benefício:** Gerenciamento automático do ciclo de vida dos arquivos, movendo dados antigos de incidentes (ex: Arquivos de Raccoon City) para camadas de arquivamento de baixo custo.

---

## 🗄️ Modelagem de Dados

A base de dados PostgreSQL é estruturada para garantir a rastreabilidade total de cada experimento:

| Tabela | Função |
| :--- | :--- |
| **Virus** | Cadastro de cepas virais, níveis de risco e descrição. |
| **Laboratorio** | Identificação de instalações e níveis de segurança (Biohazard Level). |
| **Pesquisador** | Registro de cientistas e vinculação a centros de pesquisa. |
| **Experimento** | Log de testes realizados, resultados e status da pesquisa. |
| **Relatório** | Documentação final com referência segura para arquivos no S3. |

---

## 🚀 API Endpoints (Preview)

A API segue o padrão RESTful para integração com sistemas de campo:

* `POST /api/v1/virus` - Registra uma nova amostra viral.
* `GET /api/v1/laboratorios` - Lista as instalações ativas.
* `POST /api/v1/experimentos` - Inicia um novo protocolo de teste biológico.
* `GET /api/v1/relatorios/download/{id}` - Recupera documentação segura do S3.

---

## 🔧 Configuração e Execução

1. **Requisitos:** Java 21, Maven e PostgreSQL instalados.
2. **Configuração:** Edite o `src/main/resources/application.properties` com suas credenciais AWS e DB.
3. **Build:**
   ```bash
   mvn clean install

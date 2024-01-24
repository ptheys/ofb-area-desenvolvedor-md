[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17370567)

## **Visão geral**

A API Customers permite a consulta aos dados cadastrais de clientes, incluindo também dados de qualificação e de relacionamento financeiro.

## **Identificação pessoa natural **: (*GET */customers/v1/personal/identifications)

Obtém os registros de identificação da pessoa natural.

Esta especificação inclui todos os itens relevantes que permitam a ação e o efeito de identificar de forma única a pessoa natural através de seus dados cadastrais.

### Visão de alto nível das estruturas de dados
![att17370653](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/TLD_Personal_Identification-e45ae8d0.png)
### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

![att17370626](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/DER_Personal-b3b3472b.png)

- DER Lógico

![att17370650](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/DER_Personal_Identification-638481f8.png)

### **Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetPersonalIdentifications_v1.csv)

[Fazer download dos exemplos](https://openbankingbrasil.atlassian.net/wiki/download/attachments/6127799/examples_personal_identification.csv?version=1&amp;modificationDate=1630935173381&amp;cacheVersion=1&amp;api=v2&amp;download=true)

## **Identificação pessoa jurídica **: (*GET */customers/v1/business/identifications)

Obtém os registros de identificação da pessoa jurídica.

Esta especificação inclui todos os itens relevantes que permitam a ação e o efeito de identificar de forma única a pessoa jurídica através de seus dados cadastrais.

### Visão de alto nível das estruturas de dados
![att17370647](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/TLD_Business_Identification_v3-b494d90f.png)
### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

![att17370617](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/DER_Business.v1-9078d6c8.png)

- DER Lógico

![att17370644](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/DER_Busines_Identification.v1-65c3e452.png)

### Dicionário de dados

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetBusinessIdentifications_v1.csv)

[Fazer download dos exemplos](https://openbankingbrasil.atlassian.net/wiki/download/attachments/6127799/examples_business_identification.csv?version=1&amp;modificationDate=1630935244501&amp;cacheVersion=1&amp;api=v2&amp;download=true)

## **Qualificação pessoa natural **: (*GET */customers/v1/personal/qualifications)

Obtém os registros de qualificação da pessoa natural.

Esta especificação inclui todos os itens relevantes, que permitam as instituições apreciar, avaliar, caracterizar e classificar o cliente com a finalidade de conhecer o seu perfil de risco e sua capacidade econômico-financeira.

### Visão de alto nível das estruturas de dados
![att17370641](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/TLD_Personal_Qualification-35e5512a.png)
### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

![att17370626](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/DER_Personal-b3b3472b.png)

- DER Lógico

![att17370638](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/DER_Personal_Qualification-599a52d7.png)

### Dicionário de dados

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetPersonalQualifications_v1.csv)

[Fazer download dos exemplos](https://openbankingbrasil.atlassian.net/wiki/download/attachments/6127799/examples_personal_qualification.csv?version=1&amp;modificationDate=1630935313511&amp;cacheVersion=1&amp;api=v2&amp;download=true)

## **Qualificação pessoa jurídica **: (*GET */customers/v1/business/qualifications)

Obtém os registros de qualificação da pessoa jurídica.

Esta especificação inclui todos os itens relevantes, que permitam as instituições apreciar, avaliar, caracterizar e classificar o cliente com a finalidade de conhecer o seu perfil de risco e sua capacidade econômico-financeira.

### Visão de alto nível das estruturas de dados
![att17370635](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/TLD_Business_Qualification_v3-b2372f2a.png)
### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

![att17370617](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/DER_Business.v1-9078d6c8.png)

- DER Lógico

![att17370632](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/DER_Business_Qualification.v1-07c2d32e.png)

### Dicionário de dados

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetBusinessQualifications_v1.csv)

[Fazer download dos exemplos](https://openbankingbrasil.atlassian.net/wiki/download/attachments/6127799/examples_business_qualification.csv?version=1&amp;modificationDate=1630935479511&amp;cacheVersion=1&amp;api=v2&amp;download=true)

## **Relacionamento pessoa natural **: (*GET */customers/v1/personal/financial-relations)

Obtém os registros de relacionamentos com a instituição financeira e de representantes da pessoa natural.

Considera-se relacionamento as informações que permitam conhecer desde quando a pessoa consultada é cliente da instituição, bem como um indicador dos produtos e serviços que ela consome atualmente.

### Visão de alto nível das estruturas de dados
![att17370629](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/TLD_Personal_Financial_Relation-b682e5ec.png)
### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

![att17370626](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/DER_Personal-b3b3472b.png)

- DER Lógico

![att17370623](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/DER_Personal_FinancialRelation-a515c8c7.png)

### Dicionário de dados

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetPersonalFinancialRelations_v1.csv)

[Fazer download dos exemplos](https://openbankingbrasil.atlassian.net/wiki/download/attachments/6127799/examples_personal_financial_relation.csv?version=1&amp;modificationDate=1630935683522&amp;cacheVersion=1&amp;api=v2&amp;download=true)

## **Relacionamento pessoa jurídica **: (*GET */customers/v1/business/financial-relations)

Obtém os registros de relacionamentos com a instituição financeira e de representantes da pessoa jurídica.

Considera-se relacionamento as informações que permitam conhecer desde quando a pessoa consultada é cliente da instituição, bem como um indicador dos produtos e serviços que ela consome atualmente

### Visão de alto nível das estruturas de dados
![att17370620](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/TLD_Business_Financial_Relation_v3-b682e5ec.png)
### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

![att17370617](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/DER_Business.v1-9078d6c8.png)

- DER Lógico

![att17370614](Informa%c3%a7%c3%b5es%20Gerais%20-%20Dados%20Cadastrais%20-%20V1.0.3/attachments/DER_Business_FinancialRelation.v1-0e82ab78.png)

### Dicionário de dados

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetBusinessFinancialRelations_v1.csv)

[Fazer download dos exemplos](https://openbankingbrasil.atlassian.net/wiki/download/attachments/6127799/examples_business_financial_relation.csv?version=1&amp;modificationDate=1630935734130&amp;cacheVersion=1&amp;api=v2&amp;download=true)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17370567)
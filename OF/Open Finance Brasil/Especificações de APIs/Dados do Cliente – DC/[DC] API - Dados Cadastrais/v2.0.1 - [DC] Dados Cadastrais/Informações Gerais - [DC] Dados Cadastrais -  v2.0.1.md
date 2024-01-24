[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17370207)

## **Visão geral**

A API Customers permite a consulta aos dados cadastrais de clientes, incluindo também dados de qualificação e de relacionamento financeiro.

## **Identificação pessoa natural **: (*GET */customers/v2/personal/identifications)

Obtém os registros de identificação da pessoa natural.

Esta especificação inclui todos os itens relevantes que permitam a ação e o efeito de identificar de forma única a pessoa natural através de seus dados cadastrais.

### Visão de alto nível das estruturas de dados
![att17370305](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/TLD_Personal_Identification-e45ae8d0.png)
### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

![att17370278](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/DER_Personal-b3b3472b.png)

- DER Lógico

![att17370302](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/DER_Personal_Identification-638481f8.png)

### **Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetPersonalIdentifications_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9797638/personal_identifications.csv?api=v2&amp;download=true)

## **Identificação pessoa jurídica **: (*GET */customers/v2/business/identifications)

Obtém os registros de identificação da pessoa jurídica.

Esta especificação inclui todos os itens relevantes que permitam a ação e o efeito de identificar de forma única a pessoa jurídica através de seus dados cadastrais.

### Visão de alto nível das estruturas de dados
![att17370299](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/TLD_Business_Identification_v3-b494d90f.png)
### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

![att17370269](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/DER_Business.v1-9078d6c8.png)

- DER Lógico

![att17370296](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/DER_Busines_Identification.v1-65c3e452.png)

### Dicionário de dados

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetBusinessIdentifications_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9797638/business_identifications.csv?api=v2&amp;download=true)

## **Qualificação pessoa natural **: (*GET */customers/v2/personal/qualifications)

Obtém os registros de qualificação da pessoa natural.

Esta especificação inclui todos os itens relevantes, que permitam as instituições apreciar, avaliar, caracterizar e classificar o cliente com a finalidade de conhecer o seu perfil de risco e sua capacidade econômico-financeira.

### Visão de alto nível das estruturas de dados
![att17370293](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/TLD_Personal_Qualification-35e5512a.png)
### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

![att17370278](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/DER_Personal-b3b3472b.png)

- DER Lógico

![att17370290](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/DER_Personal_Qualification-599a52d7.png)

### Dicionário de dados

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetPersonalQualifications_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9797638/personal_qualifications.csv?api=v2&amp;download=true)

## **Qualificação pessoa jurídica **: (*GET */customers/v2/business/qualifications)

Obtém os registros de qualificação da pessoa jurídica.

Esta especificação inclui todos os itens relevantes, que permitam as instituições apreciar, avaliar, caracterizar e classificar o cliente com a finalidade de conhecer o seu perfil de risco e sua capacidade econômico-financeira.

### Visão de alto nível das estruturas de dados
![att17370287](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/TLD_Business_Qualification_v3-b2372f2a.png)
### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

![att17370269](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/DER_Business.v1-9078d6c8.png)

- DER Lógico

![att17370284](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/DER_Business_Qualification.v1-07c2d32e.png)

### Dicionário de dados

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetBusinessQualifications_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9797638/business_qualifications.csv?api=v2&amp;download=true)

## **Relacionamento pessoa natural **: (*GET */customers/v2/personal/financial-relations)

Obtém os registros de relacionamentos com a instituição financeira e de representantes da pessoa natural.

Considera-se relacionamento as informações que permitam conhecer desde quando a pessoa consultada é cliente da instituição, bem como um indicador dos produtos e serviços que ela consome atualmente.

### Visão de alto nível das estruturas de dados
![att17370281](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/TLD_Personal_Financial_Relation-b682e5ec.png)
### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

![att17370278](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/DER_Personal-b3b3472b.png)

- DER Lógico

![att17370275](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/DER_Personal_FinancialRelation-a515c8c7.png)

### Dicionário de dados

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetPersonalFinancialRelations_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9797638/personal_financial_relations.csv?api=v2&amp;download=true)

## **Relacionamento pessoa jurídica **: (*GET */customers/v2/business/financial-relations)

Obtém os registros de relacionamentos com a instituição financeira e de representantes da pessoa jurídica.

Considera-se relacionamento as informações que permitam conhecer desde quando a pessoa consultada é cliente da instituição, bem como um indicador dos produtos e serviços que ela consome atualmente

### Visão de alto nível das estruturas de dados
![att17370272](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/TLD_Business_Financial_Relation_v3-b682e5ec.png)
### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

![att17370269](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/DER_Business.v1-9078d6c8.png)

- DER Lógico

![att17370266](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Dados%20Cadastrais%20-%20%20v2.0.1/attachments/DER_Business_FinancialRelation.v1-0e82ab78.png)

### Dicionário de dados

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetBusinessFinancialRelations_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9797638/business_financial_relations.csv?api=v2&amp;download=true)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17370207)
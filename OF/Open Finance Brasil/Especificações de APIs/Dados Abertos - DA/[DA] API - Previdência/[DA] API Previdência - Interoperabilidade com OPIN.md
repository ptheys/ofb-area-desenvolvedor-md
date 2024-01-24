[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/86835201)

## **Tabela de correspondência das APIs de previdência do Open Finance e Open Insurance**

Essa especificação inclui todos artefatos relevantes para a especificação de APIs de previdência no que toca ao relacionamento entre os diretórios do OPIN e do OFB, apontando a correspondência direta entre cada um dos campos listados nos swaggers.

| **&gt;&gt;&gt;&gt;&gt; OFB &lt;&lt;&lt;&lt;&lt;** | **&gt;&gt;&gt;&gt;&gt; OPIN &lt;&lt;&lt;&lt;&lt;** |
| --- | --- |
| APIs | APIs |
| API pension (v1.0.0), endpoint /risk-coverages | API pension-plan (v1.1.0) |
| API pension (v1.0.0), endpoint /survival-coverages | API life-pension (1.3.0) |

## De/Para de campos

| **API Previdência (Open Finance)** | **API Pension Plan (Open Insurance)** | **Observação** |
| --- | --- | --- |
| ***Endpoint /risk-coverage*** | ***Endpoint /pension-plan*** |  |
| **-** | requestTime |  |
| **-** | data |  |
| **-** | brand |  |
| data/participant/brand | - |  |
| data/participant/name | **-** |  |
| data/participant/cnpjNumber | **-** |  |
| data/participant/urlComplementaryList | **-** |  |
| data/society/name | brand/companies/name |  |
| data/society/cnpjNumber | brand/companies/cnpjNumber |  |
| - | brand/companies/products/ |  |
| data/name | brand/companies/products/name |  |
| data/code | brand/companies/products/code |  |
| data/modality | brand/companies/products/coverages/modality | Na versão 1.0.2 da API Pension Plan do OPIN o caminho do campo correspondente é brand/companies/products/modality, na versão 1.1.0 da API o campo correspondente é brand/companies/products/coverages/modality |
| data/modality/DESEMPREGO\_PERDA\_RENDA | brand/companies/products/coverages/modality/RENDA |  |
| data/coverages/type | brand/companies/products/coverages/coverage |  |
| data/coverages/typeAdditionalInfos | - |  |
| data/coverages/atributes | brand/companies/products/coverages/coveragesAttributes/ |  |
| data/coverages/attributes/indemnityPaymentMethods | brand/companies/products/coverages/coveragesAttributes/indenizationPaymentMethod |  |
| data/coverages/attributes/indemnityPaymentMethods/UNICO | brand/companies/products/coverages/coveragesAttributes/indenizationPaymentMethod /PAGAMENTO\_UNICO |  |
| data/coverages/attributes/indemnityPaymentMethods/SOB\_FORMA\_RENDA | brand/companies/products/coverages/coveragesAttributes/indenizationPaymentMethod /FORMA\_RENDA |  |
| data/coverages/attributes/minValue/amount | brand/companies/products/coverages/coveragesAttributes/minValue/amount |  |
| data/coverages/attributes/minValue/currency | brand/companies/products/coverages/coveragesAttributes/currency |  |
| **-** | brand/companies/products/coverages/coveragesAttributes/minValue/unit/code |  |
| **-** | brand/companies/products/coverages/coveragesAttributes/minValue/unit/code |  |
| data/coverages/attributes/maxValue/amount | brand/companies/products/coverages/coveragesAttributes/maxValue/amount |  |
| data/coverages/attributes/maxValue/amount | brand/companies/products/coverages/coveragesAttributes/currency |  |
| **-** | brand/companies/products/coverages/coveragesAttributes/maxValue/unit/code |  |
| **-** | brand/companies/products/coverages/coveragesAttributes/maxValue/unit/description |  |
| data/coverages/attributes/indemnifiablePeriods | brand/companies/products/coverages/coveragesAttributes/indemnifiablePeriod |  |
| data/coverages/attributes/indemnifiablePeriods/QUANTIDADE\_DETERMINAD A\_PARCELAS | brand/companies/products/coverages/coveragesAttributes/indemnifiablePeriod/PRAZO |  |
| data/coverages/attributes/indemnifiablePeriods/FIM\_CICLO\_DETERMINADO | brand/companies/products/coverages/coveragesAttributes/indemnifiablePeriod/ATE\_FI M\_CICLO\_DETERMINADO |  |
| data/coverages/attributes/indemnifiableDeadline | brand/companies/products/coverages/coveragesAttributes/indemnifiableDeadline |  |
| data/coverages/attributes/excludedRisks | brand/companies/products/coverages/coveragesAttribu tes/excludedRisk |  |
| data/coverages/attributes/excludedRisksURL | brand/companies/products/coverages/coveragesAttributes/excludedRiskURL |  |
| data/coverages/attributes/gracePeriod | brand/companies/products/coverages/coveragesAttributes/gracePeriod |  |
| data/coverages/attributes/gracePeriod/amount | brand/companies/products/coverages/coveragesAttributes/gracePeriod/amount |  |
| data/coverages/attributes/gracePeriod/unit | brand/companies/products/coverages/coveragesAttributes/gracePeriod/unit |  |
| - | brand/companies/products/coverages/coveragePeriod |  |
| data/additionals | brand/companies/products/additional |  |
| - | brand/companies/products/additionalOthers |  |
| data/assistanceTypes | brand/companies/products/assistanceType |  |
| data/assistanceTypes/VITIMA | brand/companies/products/assistanceType/VITIMAS |  |
| data/assistanceTypes/SAUDE\_BEM\_ESTAR | brand/companies/products/assistanceType/SAUDE\_BEMESTAR |  |
| data/assistanceTypes/SUSTENTAVEL\_DESCARTE\_ECOLOGICO | brand/companies/products/assistanceType/SUSTENTAVEL\_(DESCARTE\_ECOLOGICO) |  |
| data/assistanceTypes/SAQUE\_COACAO | brand/companies/products/assistanceType/SAQUE\_SOB\_COACAO |  |
| data/assistanceTypes/RETORNO\_MENORES\_SEGURADO | brand/companies/products/assistanceType/RETORNO\_MENORES\_E\_OU\_SEGURADO |  |
| data/assistanceTypes/PROTECAO\_DADOS | brand/companies/products/assistanceType/PROTECAO\_DE\_DADOS |  |
| data/assistanceTypes/PRORROGACAO\_ESTADIA | brand/companies/products/assistanceType/PRORROGACAO\_DE\_ESTADIA |  |
| data/assistanceTypes/MEDICA\_ACIDENTE\_DOENCA | brand/companies/products/assistanceType/MEDICA\_POR\_ACIDENTE\_OU\_DOENCA |  |
| data/assistanceTypes/MAIS\_VIDA | brand/companies/products/assistanceType/MAIS\_EM\_VIDA |  |
| data/assistanceTypes/INTERRUPCAO\_VIAGEM | brand/companies/products/assistanceType/INTERRUPCAO\_DA\_VIAGEM |  |
| data/assistanceTypes/HOSPEDAGEM\_ACOMPANHANTE | brand/companies/products/assistanceType/HOSPEDAGEM\_DE\_ACOMPANHANTE |  |
| data/assistanceTypes/FIANCAS\_DESPESAS\_LEGAIS | brand/companies/products/assistanceType/FIANCAS\_E\_DESPESAS\_LEGAIS |  |
| data/assistanceTypes/DECESSO | brand/companies/products/assistanceType/DECESSO\_FAMILIAR\_E\_OU\_INDIVIDUAL |  |
| data/assistanceTypes/CLUBE\_VANTAGENS\_BENEFICIOS | brand/companies/products/assistanceType/CLUBE\_DE\_VANTAGENS\_BENEFICIOS |  |
| data/assistanceTypesAdditionalInfos | brand/companies/products/assistanceTypeOthers |  |
| data/termsAndConditions | brand/companies/products/termAndCondition |  |
| data/termsAndConditions/susepProcessNumber | brand/companies/products/termAndCondition/susepProcessNumber |  |
| data/termsAndConditions/detail | brand/companies/products/termAndCondition/definition |  |
| data/pmbacRemuneration | brand/companies/products/updatePMBaC |  |
| data/pmbacRemuneration/interestRate | brand/companies/products/updatePMBaC/interestRate |  |
| data/pmbacRemuneration/updateIndexes | brand/companies/products/updatePMBaC/updateIndex |  |
| /data/premiumUpdateIndex | brand/companies/products/premiumUpdateIndex |  |
| data/ageAdjustment | brand/companies/products/ageReframing |  |
| data/ageAdjustment/criterias | brand/companies/products/ageReframing/reframingCriterion |  |
| data/ageAdjustment/frequency | brand/companies/products/ageReframing/reframingPeriodicity |  |
| data/financialRegimeContractTypes | brand/companies/products/financialRegimeContractType |  |
| data/reclaim/table | brand/companies/products/reclaim/reclaimTable |  |
| data/reclaim/table/initialMonthRange | brand/companies/products/reclaim/reclaimTable/initialMonthRange |  |
| data/reclaim/table/finalMonthRange | brand/companies/products/reclaim/reclaimTable/finalMonthRange |  |
| data/reclaim/table/percentage | brand/companies/products/reclaim/reclaimTable/percentage |  |
| data/reclaim/differenciatedPercentage | rand/companies/products/reclaim/differentiatedPercentage |  |
| data/reclaim/gracePeriod/amount | brand/companies/products/reclaim/gracePeriod | O campo data/reclaim/gracePeriod/amount deve ser preenchido com o valor do campo brand/companies/products/reclaim/gracePeriod do OPIN quando este vier expresso como número. Quando vier com o valor "Não se aplica" deve-se preencher o campo data/reclaim/gracePeriod/amount com o número zero. |
| data/reclaim/gracePeriod/unit | brand/companies/products/reclaim/gracePeriod | O campo data/reclaim/gracePeriod/unit deve ser sempre preenchido com o valor "DIAS" quando o valor do campo brand/companies/products/reclaim/gracePeriod do OPIN for um número inteiro. Quando vier "Não se aplica", deve-se preencher o campo data/reclaim/gracePeriod/unit com o valor "NAO\_APLICA" |
| data/otherGuaranteedValues | brand/companies/products/otherGuarateedValues |  |
| data/coverages/attributes/profitModality | brand/companies/products/coverages/coveragesAttibutes/profitModality |  |
| /data/contributionPayment | brand/companies/products/contributionPayment |  |
| data/contributionPayment/contributionPaymentMethod | brand/companies/products/contributionPayment/contributionPayme ntMethod |  |
| data/contributionPayment/contributionPeriodicity | brand/companies/products/contributionPayment/contributionPeriodicity |  |
| - | brand/companies/products/contributionTax |  |
| data/minimumRequirement | brand/companies/products/minimumRequirements |  |
| data/minimumRequirement/contractType | brand/companies/products/minimumRequirements/minRequirementsContractType |  |
| data/minimumRequirement/contractingMinRequirement | brand/companies/products/minimumRequirements/minRequirementsContract |  |
| data/targetAudience | brand/companies/products/targetAudience |  |
| links/self | linksPaginated/self |  |
| links/first | linksPaginated/first |  |
| links/prev | linksPaginated/prev |  |
| links/next | linksPaginated/next |  |
| links/last | linksPaginated/last |  |
| meta/totalRecords | metaPaginated/totalRecords |  |
| meta/totalPages | metaPaginated/totalPages |  |

## De/Para dos Parâmetros

| **API Previdência (Open Finance)** | **API Pension Plan (Open Insurance)** | **Observação** |
| --- | --- | --- |
| ***Endpoint /risk-coverage*** | ***Endpoint /pension-plan*** |  |
| parameters/page | parameters/page |  |
| parameters/page-size | parameters/page-size |  |
| - | parameters/cache-control |  |
| - | parameters/Content-Security-Policy |  |
| - | parameters/content-Type |  |
| - | parameters/Strict-Transport-Security |  |
| - | parameters/X-Content-Type-Options |  |
| - | parameters/X-Frame-Options |  |

## De/Para dos status code

| **API Previdência (Open Finance)** | **API Pension Plan (Open Insurance)** | **Observação** |
| --- | --- | --- |
| ***Endpoint /risk-coverage*** | ***Endpoint /pension-plan*** |  |
| **-** | Status code 201 |  |
| **-** | Status code 204 |  |
| **-** | Status code 401 |  |
| **-** | Status code 403 |  |
| **-** | Status code 406 |  |
| **-** | Status code 422 |  |
| **-** | Status code default |  |
| **-** | 400 404 405 429 500 /errors/requestDateTime |  |

## De/Para de campos

| **API Previdência (Open Finance)** | **API Life-pension **  <br>**(Open Insurance)** | **Observação** |
| --- | --- | --- |
| ***Endpoint /survival-coverage*** | ***Endpoint /life-pension*** |  |
| data/participant/brand | - |  |
| 200/data/participant/name | - |  |
| 200/data/participant/cnpjNumber | - | Na versão 1.2.0 da API Life Pension do OPIN o caminho do campo correspondente é /identification/cnpjNumber, na versão 1.3.0 da API o campo foi movido para /data/companies/cnpjNumber |
| 200/data/participant/urlComplementaryList | - |  |
| 200/data/society/name | /data/companies/name | Na versão 1.2.0 da API Life Pension do OPIN o caminho  <br>do campo correspondente é  <br>/identification/societyName, na versão 1.3.0 da API o  <br>campo foi movido para /data/companies/name |
| 200/data/society/cnpjNumber | /data/companies/cnpjNumber |  |
| 200/data/name | /products/name |  |
| 200/data/code | /products/code |  |
| 200/data/segment | /products/segment |  |
| 200/data/type | /products/type |  |
| 200/data/additionalInfo | /products/optionalCoverage |  |
| 200/data/modality | /products/modality |  |
| 200/data/termsAndConditions/susepProcessNumber | products/productDetails/susepProcessNumber |  |
| 200/data/termsAndConditions/detail | /products/productDetails/contractTermsConditions |  |
| 200/data/defferalPeriod | /products/productDetails/defferalPeriod |  |
| 200/data/defferalPeriod/interestRate | /products/productDetails/defferalPeriod/interestRate |  |
| 200/data/defferalPeriod/updateIndex | /products/productDetails/defferalPeriod/updateIndex |  |
| 200/data/defferalPeriod/updateIndex/IGP\_M | /products/productDetails/defferalPeriod/updateIndex/IGP-M |  |
| 200/data/defferalPeriod/otherMinimumPerformanceGara  <br>ntees | /products/productDetails/defferalPeriod/otherMinimumPerforman  <br>ceGarantees |  |
| 200/data/defferalPeriod/reversalFinancialResults | /products/productDetails/defferalPeriod/reversalFinancialResults |  |
| 200/data/defferalPeriod/minimumPremiums | /products/productDetails/defferalPeriod/minimumPremiumAmount |  |
| 200/data/defferalPeriod/minimumPremiums/amount | /products/productDetails/defferalPeriod/minimumPremiumAmoun  <br>t/minimumPremiumAmountValue |  |
| 200/data/defferalPeriod/minimumPremiums/currency | - |  |
| 200/data/defferalPeriod/minimumPremiums/periodicity | /products/productDetails/defferalPeriod/minimumPremiumAmoun  <br>t/minimumPremiumAmountDescription |  |
| 200/data/defferalPeriod/premiumPaymentMethods | /products/productDetails/defferalPeriod/premiumPaymentMethod |  |
| 200/data/defferalPeriod/permissionExtraordinaryContrib  <br>utions | /products/productDetails/defferalPeriod/permissionExtraordinary  <br>Contributions |  |
| 200/data/defferalPeriod/permissionScheduledFinancialPay  <br>ments | /products/productDetails/defferalPeriod/permissonScheduledFinanci  <br>alPayments |  |
| 200/data/defferalPeriod/gracePeriod/redemption | /products/productDetails/defferalPeriod/gracePeriodRedemption |  |
| 200/data/defferalPeriod/gracePeriod/betweenRedemption  <br>Requests | /products/productDetails/defferalPeriod/gracePeriodBetweenRedem  <br>ptionRequests |  |
| 200/data/defferalPeriod/gracePeriod/portability | /products/productDetails/defferalPeriod/gracePeriodPortability |  |
| 200/data/defferalPeriod/redemptionPaymentTerm | /products/productDetails/defferalPeriod/redemptionPaymentTerm |  |
| 200/data/defferalPeriod/gracePeriod/betweenPortabilityRe  <br>quests | /products/productDetails/defferalPeriod/gracePeriodBetweenPortabi  <br>lityRequests |  |
| 200/data/defferalPeriod/portabilityPaymentTerm | /products/productDetails/defferalPeriod/portabilityPaymentTerm |  |
| 200/data/defferalPeriod/investmentFunds/cnpjNumber | /products/productDetails/defferalPeriod/investimentFunds/cnpjNum  <br>ber |  |
| 200/data/defferalPeriod/investmentFunds/name | /products/productDetails/defferalPeriod/investimentFunds/company  <br>Name |  |
| 200/data/defferalPeriod/investmentFunds/maximumAdmin  <br>istrationFee | /products/productDetails/defferalPeriod/investimentFunds/maximu  <br>mAdministrationFee |  |
| 200/data/defferalPeriod/investmentFunds/typePerformanc  <br>eFee | /products/productDetails/defferalPeriod/investimentFunds/typePerf  <br>ormanceFee | O campo typePerformanceFee no OPIN retorna  <br>uma lista. O primeiro item da lista retornada  <br>deverá ser atribuído ao campo  <br>/data/defferalPeriod/investmentFunds/typePerfo  <br>rmanceFee. |
| 200/data/defferalPeriod/investmentFunds/maximumP  <br>erformanceFee | /products/productDetails/defferalPeriod/investimentFunds/ma  <br>ximumPerformanceFee | Os campos possuem tipos de dado diferentes. É necessário converter  <br>Number(Open Insurance)~String(Open Finance), respeitando os  <br>padrões de apresentação de valores monetários no OFB |
| 200/data/defferalPeriod/investmentFunds/eligibilityRul  <br>e | /products/productDetails/defferalPeriod/investimentFunds/eli  <br>gibilityRule |  |
| 200/data/defferalPeriod/investmentFunds/minimumCo  <br>ntributionAmount | /products/productDetails/defferalPeriod/investimentFunds/mi  <br>nimumContributionAmount | Os campos possuem tipos de dado diferentes. É necessário converter  <br>Number(Open Insurance)~String(Open Finance), respeitando os  <br>padrões de apresentação de valores monetários no OFB |
| - | /products/productDetails/defferalPeriod/investimentFunds/mi  <br>nimumContributionValue |  |
| 200/data/defferalPeriod/investmentFunds/minimumMa  <br>thematicalProvisionAmount | /products/productDetails/defferalPeriod/investimentFunds/mi  <br>nimumMathematicalProvisionAmount | Os campos possuem tipos de dado diferentes. É necessário converter  <br>Number(Open Insurance)~String(Open Finance), respeitando os  <br>padrões de apresentação de valores monetários no OFB |
| 200/data/defferalPeriod/investmentFunds/currency | - |  |
| 200/data/grantPeriodBenefit | /products/productDetails/grantPeriodBenefit |  |
| 200/data/grantPeriodBenefit/incomeModalities | /products/productDetails/grantPeriodBenefit/incomeModality |  |
| 200/data/grantPeriodBenefit/biometricTable | /products/productDetails/grantPeriodBenefit/biometricTable |  |
| 200/data/grantPeriodBenefit/interestRate | /products/productDetails/grantPeriodBenefit/interestRate | Os campos possuem tipos de dado diferentes. É necessário converter  <br>Number(Open Insurance)~String(Open Finance), respeitando os  <br>padrões de apresentação de valores monetários no OFB |
| 200/data/grantPeriodBenefit/updateIndex | /products/productDetails/grantPeriodBenefit/updateIndex |  |
| 200/data/grantPeriodBenefit/updateIndex/IGP\_M | /products/productDetails/grantPeriodBenefit/updateIndex/IGP -M |  |
| 200/data/grantPeriodBenefit/reversalFinancialResults | /products/productDetails/grantPeriodBenefit/reversalResultsFina  <br>ncial | Os campos possuem tipos de dado diferentes. É necessário  <br>converter Number(Open Insurance)~String(Open Finance),  <br>respeitando os padrões de apresentação de valores monetários no  <br>OFB |
| 200/data/grantPeriodBenefit/investmentFunds/cnpjNumbe  <br>r | /products/productDetails/grantPeriodBenefit/investimentFunds/  <br>cnpjNumber | No OPIN é aplicada uma máscara de CNPJ no valor do campo. No  <br>Open Finance deve-se ter apenas os números do CNPJ, sem  <br>máscara. |
| 200/data/grantPeriodBenefit/investmentFunds/name | /products/productDetails/grantPeriodBenefit/investimentFunds/  <br>companyName |  |
| 200/data/grantPeriodBenefit/investmentFunds/maximumA  <br>dministrationFee | /products/productDetails/grantPeriodBenefit/investimentFunds/  <br>maximumAdministrationFee | Os campos possuem tipos de dado diferentes. É necessário  <br>converter Number(Open Insurance)~String(Open Finance),  <br>respeitando os padrões de apresentação de valores monetários no  <br>OFB |
| 200/data/grantPeriodBenefit/investmentFunds/typePerfor  <br>manceFee | /products/productDetails/grantPeriodBenefit/investimentFunds/t  <br>ypePerformanceFee | O campo typePerformanceFee no OPIN retorna uma lista. O  <br>primeiro item da lista retornada deverá ser atribuído ao campo  <br>/data/grantPeriodBenefit/investmentFunds/typePerformanceFee. |
| 200/data/grantPeriodBenefit/investmentFunds/maximumP  <br>erformanceFe | /products/productDetails/grantPeriodBenefit/investimentFunds/  <br>maximumPerformanceFee | Os campos possuem tipos de dado diferentes. É necessário  <br>converter Number(Open Insurance)~String(Open Finance),  <br>respeitando os padrões de apresentação de valores monetários no  <br>OFB |
| 200/data/grantPeriodBenefit/investmentFunds/eligibilityR  <br>ule | /products/productDetails/grantPeriodBenefit/investimentFunds/  <br>eligibilityRule |  |
| 200/data/grantPeriodBenefit/investmentFunds/minimumC  <br>ontributionAmount | /products/productDetails/grantPeriodBenefit/investimentFunds/  <br>minimumContributionAmoun | Os campos possuem tipos de dado diferentes. É necessário  <br>converter Number(Open Insurance)~String(Open Finance),  <br>respeitando os padrões de apresentação de valores monetários no  <br>OFB |
| - | /products/productDetails/grantPeriodBenefit/investimentFunds/m  <br>inimumContributionValue |  |
| 200/data/grantPeriodBenefit/investmentFunds/minimu  <br>mMathematicalProvisionAmount | /products/productDetails/grantPeriodBenefit/investimentFunds/m  <br>inimumMathematicalProvisionAmount | Os campos possuem tipos de dado diferentes. É  <br>necessário converter Number(Open  <br>Insurance)~String(Open Finance), respeitando  <br>os padrões de apresentação de valores  <br>monetários no OFB |
| 200/data/grantPeriodBenefit/investmentFunds/currency | - |  |
| 200/data/costs | /products/productDetails/costs |  |
| 200/data/costs/loadingAntecipated/minValue | /products/productDetails/costs/loadingAntecipated/minValue | Os campos possuem tipos de dado diferentes. É  <br>necessário converter Number(Open  <br>Insurance)~String(Open Finance), respeitando  <br>os padrões de apresentação de valores  <br>monetários no OFB |
| 200/data/costs/loadingAntecipated/maxValue | products/productDetails/costs/loadingAntecipated/maxValue | Os campos possuem tipos de dado diferentes. É  <br>necessário converter Number(Open  <br>Insurance)~String(Open Finance), respeitando  <br>os padrões de apresentação de valores  <br>monetários no OFB |
| 200/data/costs/loadingLate/minValue | /products/productDetails/costs/loadingLate/minValue | Os campos possuem tipos de dado diferentes. É necessário  <br>converter Number(Open Insurance)~String(Open Finance),  <br>respeitando os padrões de apresentação de valores monetários  <br>no OFB |
| 200/data/costs/loadingLate/maxValue | /products/productDetails/costs/loadingLate/maxValue | Os campos possuem tipos de dado diferentes. É necessário  <br>converter Number(Open Insurance)~String(Open Finance),  <br>respeitando os padrões de apresentação de valores monetários  <br>no OFB |
| 200/data/minimumRequirement | /products/minimumRequirements |  |
| 200/data/minimumRequirement/contractType | /products/minimumRequirements/contractType |  |
| 200/data/minimumRequirement/participantQualified | /products/minimumRequirements/participantQualified |  |
| 200/data/minimumRequirement/contractingMinRequirement | products/minimumRequirements/minRequirementsContract |  |
| 200/data/targetAudience | /products/targetAudience |  |
| /links/self | /links/self |  |
| /links/first | /links/first |  |
| /links/prev | /links/prev |  |
| /links/next | /links/next |  |
| /links/last | /links/last |  |
| /meta/totalRecords | /meta/totalRecords |  |
| /meta/totalPages | /meta/totalPages |  |

## De/Para dos Parâmetros

| **API Previdência (Open Finance)** | **API Life-pension **  <br>**(Open Insurance)** | **Observação** |
| --- | --- | --- |
| ***Endpoint /survival-coverage*** | ***Endpoint /life-pension*** |  |
| parameters/page | parameters/page |  |
| parameters/page-size | parameters/page-size |  |
| **-** | parameters/cache-control |  |
| **-** | parameters/Content-Security-Policy |  |
| **-** | parameters/content-Type |  |
| **-** | parameters/Strict-Transport-Security |  |
| **-** | parameters/X-Content-Type-Options |  |
| **-** | parameters/X-Frame-Options |  |

## De/Para dos Status code

| **API Previdência (Open Finance)** | **API Life-pension **  <br>**(Open Insurance)** | **Observação** |
| --- | --- | --- |
| ***Endpoint /survival-coverage*** | ***Endpoint /life-pension*** |  |
| **-** | Status code 401 |  |
| **-** | Status code 403 |  |
| **-** | Status code 406 |  |
| **-** | Status code default |  |
| **-** | 400 404 405 429 500 /errors/requestDateTime |  |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/86835201)
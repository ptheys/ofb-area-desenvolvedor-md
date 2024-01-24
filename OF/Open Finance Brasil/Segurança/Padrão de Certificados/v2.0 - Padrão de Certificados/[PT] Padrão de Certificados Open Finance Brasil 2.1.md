[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/245694518)

## Prefácio

This document is also available in [English](file:///C:/wiki/spaces/DraftOF/pages/76710230).

A Estrutura Inicial do Open Finance Brasil (EIOFB) é responsável por criar os padrões e especificações necessários para atender aos requisitos e obrigações da Legislação do Open Finance do Brasil, conforme originalmente delineado pelo [Banco Central do Brasil](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). É possível que alguns dos elementos deste documento estejam sujeitos a direitos de patente. A Estrutura Inicial do Open Finance Brasil não se responsabiliza pela identificação de qualquer ou todos os direitos de patente.

## Objetivo

Especificar o conjunto de certificados necessários que devem ser utilizados pelas entidades participantes do Open Finance Brasil para garantir interoperabilidade para autenticação, confidencialidade, integridade e não repúdio entre os participantes, bem como para os usuários e consumidores destas entidades. O público desta especificação são entidades participantes do Open Finance Brasil que necessitam fazer a emissão de certificados para se autenticar junto a outras entidades, bem como oferecer a seus clientes um canal de autenticação seguro.

## Convenções Notacionais

As palavras-chave "deve" (shall), "não deve" (shall not), "deveria" (should), "não deveria" (should not) e "pode" (may) presentes nesse documento devem ser interpretadas conforme as diretrizes descritas em [ISO Directive Part 2][ISODIR2] observando seguinte equivalência:

- "deve" =&gt; equivalente ao termo "shall" e expressa um requerimento definido no documento (nas traduções é similar ao termo "must", que pode denotar um requerimento externo ao documento);
- "não deve" =&gt; equivalente ao termo "shall not" e também expressa um requerimento definido no documento;
- "deveria" e "não deveria"=&gt; equivalente ao termo "should" e "should not" e expressa uma recomendação
- "pode" =&gt; equivalente ao termo "may" indica uma permissão

Estas palavras-chave não são usadas como termos de dicionário, de modo que qualquer ocorrência deles deve ser interpretada como palavras-chave e não devem ser interpretados com seus significados de linguagem natural.

## 1. Escopo

Este documento especifica os tipos de certificados necessários para:

- Autenticar mutuamente (MTLS - Mutual TLS) as aplicações dos participantes;
- Assinatura de Mensagens (JWS - JSON Web Signature) de aplicações para garantir a autenticidade e não repúdio de mensagens entre os participantes;
- Apresentar um canal seguro e confiável para clientes do Open Finance Brasil;
- Autenticar participantes no Diretório de participantes do Open Finance Brasil.

## 2. Referências Normativas

Os seguintes documentos referenciados são indispensáveis para a aplicação deste documento. Para referências datadas, apenas a edição citada se aplica. Para referências não datadas, a última edição do documento referenciado (incluindo quaisquer emendas) se aplica.

- [ISODIR2] - ISO/IEC Directives Part 2 [ISODIR2]: [https://www.iso.org/sites/directives/current/part2/index.xhtml](https://www.iso.org/sites/directives/current/part2/index.xhtml)
- [RFC5280] - Internet X.509 Public Key Infrastructure Certificate and Certificate Revocation List (CRL) Profile: [https://datatracker.ietf.org/doc/html/rfc5280](https://datatracker.ietf.org/doc/html/rfc5280)
- [RFC7519] - JSON Web Token (JWT) [RFC7519]:[https://tools.ietf.org/html/rfc7519](https://tools.ietf.org/html/rfc7519)
- [RFC7515] - JSON Web Signature (JWS) [RFC7515] :[https://datatracker.ietf.org/doc/html/rfc7515](https://datatracker.ietf.org/doc/html/rfc7515)
- [RFC7591] - OAuth 2.0 Dynamic Client Registration Protocol [RFC7591]:[https://tools.ietf.org/html/rfc7591](https://tools.ietf.org/html/rfc7591)
- [RFC7592] - OAuth 2.0 Dynamic Client Registration Management Protocol [RFC7592]:[https://tools.ietf.org/html/rfc7592](https://tools.ietf.org/html/rfc7592)
- [BCP195] - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS) [BCP195]: [https://tools.ietf.org/html/bcp195](https://tools.ietf.org/html/bcp195)
- [RFC8705] - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens [RFC8705]: [https://tools.ietf.org/html/rfc8705](https://tools.ietf.org/html/rfc8705)
- [OFB-FAPI] - Open Finance Brasil Financial-grade API Security Profile 1.0 [OFB-FAPI]: [\[PT\] Open Finance Brasil Financial-grade API Security Profile 1.0 Implementers Draft 3](../../../../../OF/Open%20Finance%20Brasil/Seguran%c3%a7a/Perfil%20de%20Seguran%c3%a7a%20do%20Open%20Finance%20Brasil/v2.0-RC1%20-%20Perfil%20de%20Seguran%c3%a7a%20do%20Open%20Finance%20Brasil/[PT]%20Open%20Finance%20Brasil%20Financial-grade%20API%20Security%20Profile%201.0%20Implementers%20Draft%203)
- [OFB-FAPI-DCR] - Open Finance Brasil Financial-grade API Dynamic Client Registration Profile 1.0 [OFB-FAPI-DCR]: [\[PT\] Open Finance Brasil Financial-grade API Dynamic Client Registration 1.0 Implementers Draft 3](https://openfinancebrasil.atlassian.net/wiki/pages/createpage.action?spaceKey=OF&amp;title=%5BPT%5D%20%20Open%20Finance%20Brasil%20Financial-grade%20API%20Dynamic%20Client%20Registration%201.0%20Implementers%20Draft%203)
- [DOC-ICP-01] - DECLARAÇÃO DE PRÁTICAS DE CERTIFICAÇÃO DA AUTORIDADE CERTIFICADORA RAIZ DA ICP-BRASIL: [https://www.gov.br/iti/pt-br/centrais-de-conteudo/doc-icp-01-v-5-2-dpc-da-ac-raiz-da-icp-brasil-pdf](https://www.gov.br/iti/pt-br/centrais-de-conteudo/doc-icp-01-v-5-2-dpc-da-ac-raiz-da-icp-brasil-pdf)
- [DOC-ICP-04] - REQUISITOS MÍNIMOS PARA AS POLÍTICAS DE CERTIFICADO NA ICP-BRASIL: [https://www.gov.br/iti/pt-br/assuntos/legislacao/resolucoes/resolucoes-old/resolucao179_doc-icp-04_compilada.pdf](https://www.gov.br/iti/pt-br/assuntos/legislacao/resolucoes/resolucoes-old/resolucao179_doc-icp-04_compilada.pdf)
- [RFC6749] - The OAuth 2.0 Authorization Framework [RFC6749]: [https://tools.ietf.org/html/rfc6749](https://tools.ietf.org/html/rfc6749)
- [BCB-IN134] - Manual de Segurança do Open Finance: [https://www.in.gov.br/web/dou/-/instrucao-normativa-bcb-n-134-de-22-de-julho-de-2021-3345585364](https://www.in.gov.br/web/dou/-/instrucao-normativa-bcb-n-134-de-22-de-julho-de-2021-3345585364)
- [RFC2818] - HTTP Over TLS: [https://datatracker.ietf.org/doc/html/rfc2818](https://datatracker.ietf.org/doc/html/rfc2818)
- [RFC5246] - The Transport Layer Security (TLS) Protocol Version 1.2 [https://www.rfc-editor.org/rfc/rfc5246.txt](https://www.rfc-editor.org/rfc/rfc5246.txt)

## 3. Termos e Definições

Para o propósito deste documento os termos definidos na [RFC5280], [BCP195], [RFC8705], e ISO29100 são aplicáveis.

## 4. Glossário

- **API **- Application Programming Interface
- **DCR **- Dynamic Client Registration
- **HTTP **- Hyper Text Transfer Protocol
- **ICP **- Infraestrutura de Chave Públicas Brasileira
- **SS **- Software Statement
- **SSA **- Software Statement Assertion
- **TLS **- Transport Layer Security
- **mTLS **- Mutual Transport Layer Security
- **subjectDN **– Subject Distinguished Name
- **RDN **– Relative Distinguished Name

## 5. Padrão de Certificados Open Finance Brasil

### 5.1. Introdução

O ecossistema do Open Finance Brasil faz uso de cadeias de certificados e protocolo TLS para garantir a confidencialidade, autenticação e integridade do canal de comunicação utilizado pelas APIs das instituições participantes, bem como dos clientes de cada um dos participantes.

Os certificados utilizados pelo Open Finance Brasil também são necessários para autenticar as aplicações através do private\_key\_jwt, além de também servirem para realizar a assinatura de payload pelo uso de JWS. Outra atribuição importante dos certificados é autenticar e apresentar um canal seguro para o usuário final no ato de autenticação e uso dos serviços prestados pela entidade participante.

### 5.2. Certificados ICP-Brasil

Os certificados emitidos pelas Autoridades Certificadoras autorizadas pelo ICP-Brasil são utilizados apenas na comunicação entre as entidades participantes do ecossistema do Open Finance Brasil.

Os processos de emissão e revogação dos certificados são de responsabilidade das próprias Autoridades Certificadores, sendo regulamentados por Declarações de Prática de Certificação, e supervisionadas pelo Comitê Gestor da Infraestrutura de Chaves Públicas Brasileira.

As práticas, processos, disponibilização e valores praticados pelas Autoridades Certificadoras não são de responsabilidade do Estrutura Inicial do Open Finance Brasil.

Restrição de nomes

Apesar do suporte ao UTF8 pelos atributos do certificado, este padrão seguirá as restrições de nomes conforme documento: “REQUISITOS MÍNIMOS PARA AS POLÍTICAS DE CERTIFICADO NA ICP-BRASIL”, item 7.1.5, estabelecendo as seguintes restrições para os nomes, aplicáveis a todos os certificados ICP-BRASIL:

- não deverão ser utilizados sinais de acentuação, tremas ou cedilhas; e
- além dos caracteres alfanuméricos, poderão ser utilizados somente os seguintes caracteres especiais:

| **Caractere** | **Código NBR9611 (hexadecimal)** | **Caractere** | **Código NBR9611 (hexadecimal)** |
| --- | --- | --- | --- |
| branco | 20 | + | 2B |
| ! | 21 | , | 2C |
| “ | 22 | - | 2D |
| # | 23 | . | 2E |
| $ | 24 | / | 2F |
| % | 25 | : | 3A |
| & | 26 | ; | 3B |
| ‘ | 27 | = | 3D |
| ( | 28 | ? | 3F |
| ) | 29 | @ | 40 |
| \* | 2A | \ | 5C |

Algoritmos

Todos os certificados emitidos junto ao ICP-Brasil devem possuir as seguintes características:

- Tipo A do ICP-Brasil;
- Algoritmo de Chaves: RSA 2048 bits;
- Message Digest: SHA 256 bits.

#### 5.2.1. Certificado Servidor

O Certificado Servidor deve ser emitido para proteger e autenticar o canal TLS utilizado pelas APIs que serão consumidas pelas aplicações cliente de entidades participantes do Open Finance.

O padrão de certificado utilizado deve seguir as práticas de emissão de certificados existentes de "CERTIFICADO PARA SERVIDOR WEB - ICP-Brasil".

O certificado de servidor precisa ser enviado com a cadeia intermediária, conforme [RFC5246](https://openbanking-brasil.github.io/specs-seguranca/itens%207.4.2).

#### 5.2.2. Certificado Cliente

Os Certificados de Aplicação Cliente (Transporte) são utilizados para autenticar o canal mTLS e para realizar a autenticação da aplicação cliente através de private\_key\_jwt, de acordo com o cadastro da aplicação realizado pelo processo de Dynamic Client Registration junto à entidade transmissora. Sobre o mTLS, o certificado cliente precisa ser enviado com a cadeia intermediária, conforme [RFC5246](https://openbanking-brasil.github.io/specs-seguranca/itens%207.4.2%20e%207.4.6).

Para emissão de Certificado Cliente é necessário que a instituição participante do Open Finance Brasil tenha realizado o cadastro da aplicação no Serviço de Diretório, através do processo de emissão de Software Statement Assertion, e com isso já tenha obtido o valor de Software Statement ID.

##### 5.2.2.1. Atributos Open Finance Brasil

- serialNumber: Cadastro Nacional de Pessoal Jurídica (CNPJ) da pessoa jurídica titular do certificado e associado ao atributo UID e Software Statement ID, durante validação junto ao Serviço de Diretório do Open Finance Brasil;
- organizationIdentifier: Código de Participante associado ao CNPJ listado no Serviço de Diretório do Open Finance Brasil; Para certificados emitidos até 31 de Agosto de 2022 o campo utilizado para essa informação era o organizationalUnitName.
- UID: Software Statement ID cadastrado no Serviço de Diretório do Open Finance Brasil e pertencente ao CNPJ e Código de Participante.

O Certificado Cliente deve ser emitido através de cadeia V10, e deve obrigatoriamente conter os seguintes atributos:

**Distinguished Name, conforme sequência abaixo, para maiores detalhes, consulte a seção: 9.2**

- **businessCategory (OID 2.5.4.15): Tipo de categoria comercial, devendo conter:** "Private Organization" ou "Government Entity" ou "Business Entity" ou "Non-Commercial Entity"
- **jurisdictionCountryName (OID: 1.3.6.1.4.1.311.60.2.1.3):** BR
- **serialNumber (OID 2.5.4.5): **CNPJ
- **countryName (OID 2.5.4.6):** BR
- **organizationName (OID 2.5.4.10): **Razão Social
- **stateOrProvinceName (OID 2.5.4.8): **Unidade da federação do endereço físico do titular do certificado
- **localityName (OID 2.5.4.7): **Cidade do endereço físico do titular
- **organizationIdentifier (OID 2.5.4.97): **Código de Participante associado ao CNPJ listado no Serviço de Diretório do Open Finance Brasil. Para certificados emitidos até 31 Agosto de 2022: organizationalUnitName (OID 2.5.4.11): Código de Participante associado ao CNPJ listado no Serviço de Diretório do Open Finance Brasil
- **UID (OID 0.9.2342.19200300.100.1.1):** Software Statement ID gerado pelo Diretório do Open Finance Brasil
- **commonName (OID 2.5.4.3): **FQDN ou Wildcard

**Certificate Extensions**

- **keyUsage:** critical,digitalSignature,keyEncipherment
- **extendedKeyUsage:** clientAuth

Subject Alternative Name

**DNSName:** FQDN ou Wildcard

#### 5.2.3. Certificado de Assinatura

Os Certificados de Assinatura são utilizados para realizar assinatura do payload através do uso de JWS (JSON Web Signature).

##### 5.2.3.1. Atributos Open Finance Brasil Presentes no Certificado

- **UID: **Código de Participante associado ao CNPJ listado no Serviço de Diretório do Open Finance Brasil;
- **commonName: **Razão Social cadastrado no Serviço de Diretório do Open Finance Brasil e pertencente ao CNPJ e Código de Participante.

O Certificado de Assinatura deve ser emitido através de cadeia V5, e deve obrigatoriamente conter os seguintes atributos:

**Distinguished Name**

- **UID (OID 0.9.2342.19200300.100.1.1): **Código de Participante associado ao CNPJ listado no Serviço de Diretório do Open Finance Brasil
- **countryName (OID 2.5.4.6): **BR
- **organizationName (OID 2.5.4.10): **ICP-Brasil
- **organizationalUnitName (OID 2.5.4.11): **Nome da Autoridade Certificadora
- **organizationalUnitName (OID 2.5.4.11): **CNPJ da Autoridade de Registro
- **organizationalUnitName (OID 2.5.4.11): **Tipo de identificação utilizada (presencial, videoconferência ou certificado digital)
- **commonName (OID 2.5.4.3): **Nome da Razão Social

**Certificate Extensions**

**keyUsage: **critical,digitalSignature,nonRepudiation

**Subject Alternative Name**

- **otherName (OID 2.16.76.1.3.2 - ICP-Brasil):** Nome do responsável pelo certificado
- **otherName (OID 2.16.76.1.3.3 - ICP-Brasil): **Cadastro Nacional de Pessoa Jurídica (CNPJ) da pessoa jurídica titular do certificado;
- **otherName (OID 2.16.76.1.3.4 - ICP-Brasil): **Responsável pelo certificado de pessoa jurídica titular do certificado (data de nascimento, CPF, PIS/PASEP/CI, RG);
- **otherName (OID 2.16.76.1.3.7 - ICP-Brasil): **Número do Cadastro Especifico do INSS (CEI) da pessoa jurídica titular do certificado.

#### Autoridades Certificadoras Participantes

As seguintes autoridades certificadoras realizaram o processo de integração ao Open Finance Brasil e estão habilitadas para realizar a emissão de certificados do Open Finance Brasil utilizando para tal os certificados nível 1 aqui listados:

- [CertiSign](https://www.gov.br/iti/pt-br/assuntos/repositorio/ac-certisign) (Cadeia v5 e v10)
- [Serasa](https://www.gov.br/iti/pt-br/assuntos/repositorio/ac-serasa-acp) (Cadeia v5 e v10)
- [Serpro](https://www.gov.br/iti/pt-br/assuntos/repositorio/ac-serpro-de-1deg-nivel) (Cadeia v5 e v10)
- [Soluti](https://www.gov.br/iti/pt-br/assuntos/repositorio/ac-soluti) (Cadeia v5 e v10)

Apenas deverá ser aceito certificados indicados com "Situação: válido" nestes repositórios do ITI acima referenciados que são de Cadeia ICP-Brasil v5 e v10.

#### 5.2.4. Certificado para Front-End

Os certificados para Front-End são utilizados para disponibilizar serviços, em geral páginas Web, com uso de TLS, que são acessados pelo usuário final. Dado a sua finalidade, e para garantir maior interoperabilidade, os certificados devem ser do tipo EV (Extended Validation) e devem ser ser gerados através de uma autoridade certificadora válida, seguindo as regras definidas na RFC 5280 e RFC 2818, em conformidade com os princípios e critérios WebTrust.

#### 5.2.5. Sobre certificados para troca de informações entre instituições autorizadas e parceiros

De acordo com a seção IV da Resolução Conjunta nº 1 de 4 de maio de 2020, o estabelecimento de parcerias bilaterais entre instituições autorizadas e parceiros é um arranjo previsto na regulação e que deve observar, no que couber, inclusive os mesmos padrões e certificados de segurança que são aplicáveis para a troca de informações entre as instituições participantes.

Em consonância com o §2º do Art. 10 da Medida Provisória 2.200-2 de 24 de agosto de 2001 e com o disposto no item 3.12 na Instrução Normativa BCB Nº 134, para a comunicação bilateral entre as instituições e parceiros fica autorizado o uso, em comum acordo entre as partes, de uma PKI privada desde que observados os requisitos deste perfil para os certificados segurança, o que inclui sua formatação, os algoritmos e os atributos estabelecidos.

Os valores para o preenchimento dos atributos exigidos nessa especificação, mas não aplicáveis ao parceiro, deveriam ser definidos em comum acordo entre a instituição autorizada e o parceiro, o que não isenta da instituição autorizada a responsabilidade pelo preenchimento.

## 6. Reconhecimento

Agradecemos a todos que estabeleceram as bases para o compartilhamento seguro e seguro de dados por meio da formação do Grupo de Trabalho FAPI da OpenID Foundation, o GT-Segurança do Open Finance Brasil e aos pioneiros que ficarão em seus ombros.

As seguintes pessoas contribuíram para este documento:

- João Rodolfo Vieira (Itaú)
- José Michael Dias (Grupo Pan)
- Marcos Rodrigues (Itaú)
- Nic Marcondes (Quanto)
- Ralph Bragg (Raidiam)

## 7. Informativo

Copyright (c) 2023 Estrutura Inicial do Open Finance Brasil.

A Estrutura Inicial do Open Finance Brasil (EIOFB) concede a qualquer Colaborador, desenvolvedor, implementador ou outra parte interessada uma licença de direitos autorais mundial não exclusiva, livre de royalties para reproduzir, preparar trabalhos derivados, distribuir, executar e exibir, estes Implementadores Rascunho ou Especificação Final exclusivamente para fins de (i) desenvolver especificações e (ii) implementar Rascunhos de Implementações e Especificações Finais com base em tais documentos, desde que a atribuição seja feita ao EIOFB como a fonte do material, mas que tal atribuição o faça não indica endosso do EIOFB.

A tecnologia descrita nesta especificação foi disponibilizada a partir de contribuições de várias fontes, incluindo membros da OpenID Foundation, do GT-Segurança do Open Finance Brasil e outros. Embora a Estrutura Inicial do Open Finance Brasil tenha tomado medidas para ajudar a garantir que a tecnologia esteja disponível para distribuição, ela não toma posição quanto à validade ou escopo de qualquer propriedade intelectual ou outros direitos que possam ser reivindicados como pertencentes à implementação ou uso do tecnologia descrita nesta especificação ou até que ponto qualquer licença sob tais direitos pode ou não estar disponível; nem representa que fez qualquer esforço independente para identificar tais direitos. A Estrutura Inicial do Open Finance Brasil e os contribuidores desta especificação não oferecem (e por meio deste expressamente se isentam de quaisquer) garantias (expressas, implícitas ou de outra forma), incluindo garantias implícitas de comercialização, não violação, adequação a uma finalidade específica ou título, relacionados a esta especificação, e todo o risco quanto à implementação desta especificação é assumido pelo implementador. A política de Direitos de Propriedade Intelectual do Open Finance Brasil exige que os contribuidores ofereçam uma promessa de patente de não fazer valer certas reivindicações de patentes contra outros contribuidores e implementadores. A Estrutura Inicial do Open Finance Brasil convida qualquer parte interessada a trazer à sua atenção quaisquer direitos autorais, patentes, pedidos de patentes ou outros direitos de propriedade que possam abranger a tecnologia que possa ser necessária para praticar esta especificação.

## 8. Apêndice

### 8.1. Modelo de Configuração de Certificado Cliente - OpenSSL \*Para certificados emitidos até 31 Agosto de 2022

    [req]
    default_bits = 2048
    default_md = sha256
    encrypt_key = yes
    prompt = no
    string_mask = utf8
    distinguished_name = client_distinguished_name
    req_extensions = req_cert_extensions
    
    [ client_distinguished_name ]
    businessCategory = <tipo de entidade>
    jurisdictionCountryName = BR
    serialNumber = <CNPJ>
    countryName = BR
    organizationName = <Razao Social>
    stateOrProvinceName = <UF>
    localityName = <Cidade>
    organizationalUnitName = <Código de Participante>
    UID = <Software Statement ID emitido pelo diretório>
    commonName = <FQDN|Wildcard>
    
    [ req_cert_extensions ]
    basicConstraints = CA:FALSE
    subjectAltName = @alt_name
    keyUsage = critical,digitalSignature,keyEncipherment
    extendedKeyUsage = clientAuth
    
    [ alt_name ]
    DNS = <FQDN|Wildcard>

### 8.2. Modelo de Configuração de Certificado Cliente - OpenSSL \*Para certificados emitidos após 31 Agosto 2022

    oid_section = OIDs
    [req]
    default_bits = 2048
    default_md = sha256
    encrypt_key = yes
    prompt = no
    string_mask = nombstr
    distinguished_name = client_distinguished_name
    req_extensions = req_cert_extensions
    
    [ OIDs ]
    organizationIdentifier = 2.5.4.97
    [ client_distinguished_name ]
    businessCategory = <tipo de entidade>
    jurisdictionCountryName = BR
    serialNumber = <CNPJ>
    countryName = BR
    organizationName = <Razao Social>
    stateOrProvinceName = <UF>
    localityName = <Cidade>
    organizationIdentifier = OFBBR-<Código de Participante>
    UID = <Software Statement ID emitido pelo diretório>
    commonName = <FQDN|Wildcard>
    
    [ req_cert_extensions ]
    basicConstraints = CA:FALSE
    subjectAltName = @alt_name
    keyUsage = critical,digitalSignature,keyEncipherment
    extendedKeyUsage = clientAuth
    
    [ alt_name ]
    DNS = <FQDN|Wildcard>

### 8.3. Modelo de Configuração de Certificado de Assinatura

    [req]
    default_bits = 2048
    default_md = sha256
    encrypt_key = yes
    prompt = no
    string_mask = nombstr
    distinguished_name = client_distinguished_name
    req_extensions = req_cert_extensions
    
    [ client_distinguished_name ]
    UID = <Código de Participante>
    countryName = BR
    organizationName = ICP-Brasil
    0.organizationalUnitName = <Autoridade Certificadora>
    1.organizationalUnitName = <CNPJ da Autoridade Registradora>
    2.organizationalUnitName = <Tipo de validação>
    commonName = <Razão Social>
    
    [ req_cert_extensions ]
    basicConstraints = CA:FALSE
    subjectAltName = @alt_name
    keyUsage = critical,digitalSignature,nonRepudiation
    
    [ alt_name ]
    otherName.0 = 2.16.76.1.3.2;PRINTABLESTRING:<Nome da pessoal responsável pela entidade>#CNPJ
    otherName.1 = 2.16.76.1.3.3;PRINTABLESTRING:<CNPJ>
    otherName.2 = 2.16.76.1.3.4;PRINTABLESTRING:<CPF/PIS/RF da Pessoa responsável>
    otherName.3 = 2.16.76.1.3.7;PRINTABLESTRING:<Número de INSS>

### 8.4. Tabela com Endpoints vs Tipo de Certificado e mTLS

Abaixo apresentamos quais endpoints podem ser publicados utilizando certificado EV como autenticação do consentimento e os endpoints de autenticação de APIs privadas/negócios que devem ser publicadas usando certificado ICP. Você também poderá verificar quais endpoints devem proteger suas conexões utilizando mTLS.

Fica a critério da instituição a escolha do certificado que deve ser adotado para os endpoints de Dados Abertos, os quais, por natureza, são de acesso público.

| **Fase** | **Grupo** | **API** | **Certificado** | **mTLS** |
| --- | --- | --- | --- | --- |
| NA | OIDC | .well-known/openid-configuration | EV ou ICP WEB SSL | Não se aplica |
| NA | OIDC | jwks\_uri | EV ou ICP WEB SSL | Não se aplica |
| NA | OIDC | authorization\_endpoint | EV | Não se aplica |
| NA | OIDC | token\_endpoint | ICP WEB SSL | Obrigatório |
| NA | OIDC | userinfo\_endpoint | ICP WEB SSL | Obrigatório |
| NA | OIDC | pushed\_authorization\_request\_endpoint | ICP WEB SSL | Obrigatório |
| NA | DCR | registration\_endpoint | ICP WEB SSL | Obrigatório |
| NA | OIDC | revocation\_endpoint | ICP WEB SSL | Obrigatório |
| 2 | Consentimentos | /consents/\* | ICP WEB SSL | Obrigatório |
| 2 | Resources | /resources/\* | ICP WEB SSL | Obrigatório |
| 2 | Dados | /customers/\* | ICP WEB SSL | Obrigatório |
| 2 | Cartão | /credit-cards-accounts/\* | ICP WEB SSL | Obrigatório |
| 2 | Contas | /accounts/\* | ICP WEB SSL | Obrigatório |
| 2 | Empréstimos | /loans/\* | ICP WEB SSL | Obrigatório |
| 2 | Financiamentos | /financings/\* | ICP WEB SSL | Obrigatório |
| 2 | Adiantamento | /unarranged-accounts-overdraft/\* | ICP WEB SSL | Obrigatório |
| 2 | Direitos Creditórios | /invoice-financings/\* | ICP WEB SSL | Obrigatório |
| 3 | Pagamentos | /payments/\* | ICP WEB SSL | Obrigatório |
| 3 | Pagamentos Automáticos | /automatic-payments/\* | ICP WEB SSL | Obrigatório |
| 3 | Webhook | /webhook/\* | ICP WEB SSL | Obrigatório |
| 4 | Câmbio | /exchanges/\* | ICP WEB SSL | Obrigatório |
| 4 | Investimentos | /credit-fixed-incomes/\* | ICP WEB SSL | Obrigatório |

## 9. Padrão do Subject DN do Certificado Cliente Open Finance - Após 19 de janeiro de 2023 {#subjectDNtemplates}

Em 19 de Janeiro de 2023 foi padronizado a sequência e codificação do Subject DN utilizado nos Certificados Open Finance Cliente. Abaixo é determinado a sequência e codificação de como os atributos dos certificados devem ser apresentados no Subject DN.

Deve ser considerado o período de coexistência entre os diferentes tipos de Subject DN, desta forma os participantes do ecossistema não devem implantar controles de bloqueio que limitem o uso apenas de certificados com o Subject DN padronizado abaixo. Os participantes devem garantir que os outros padrões de DN já utilizados continuem funcionando até o final do período de coexistência, data este ainda a ser determinada.

É necessário atenção especial dos participantes durante o processo de geração do Subject DN, pois abaixo são apresentados formatos de Subject DN e RDN. O Ecossistema espera o uso de RDN em conformidade com a RFC4514.

Em caso de dúvida:

- consulte o JWKS do seu aplicativo software-id
- verifique qual é o KID do certificado que deseja o Subject DN, customize a URL e acesse: [https://keystore.directory.openbankingbrasil.org.br/&lt;org-id&gt;/&lt;software-ID&gt;/transport.jwks](https://keystore.directory.openbankingbrasil.org.br/%3corg-id%3e/%3csoftware-ID%3e/transport.jwks)

### Exemplo:

### 9.1. 1. JWKS com informações do certificado:

Exemplo: [<u>https://keystore.directory.openbankingbrasil.org.br/d7384bd0-842f-43c5-be02-9d2b2d5efc2c/bc97b8f0-cae0-4f2f-9978-d93f0e56a833/transport.jwks</u>](https://keystore.directory.openbankingbrasil.org.br/d7384bd0-842f-43c5-be02-9d2b2d5efc2c/bc97b8f0-cae0-4f2f-9978-d93f0e56a833/transport.jwks)

### 9.1. 2. Chave Pública de Certificado Exemplo:

[https://keystore.directory.openbankingbrasil.org.br/d7384bd0-842f-43c5-be02-9d2b2d5efc2c/bc97b8f0-cae0-4f2f-9978-d93f0e56a833/dr-yip0g21Iv233K5AcuRLGABFQIcEzQZnWnC3vhFtg.pem](https://keystore.directory.openbankingbrasil.org.br/d7384bd0-842f-43c5-be02-9d2b2d5efc2c/bc97b8f0-cae0-4f2f-9978-d93f0e56a833/dr-yip0g21Iv233K5AcuRLGABFQIcEzQZnWnC3vhFtg.pem)

**9.1. 1. Exemplo da Claim X5DN:**

    "x5dn":"CN=web.conftpp.directory.openbankingbrasil.org.br,UID=bc97b8f0-cae0-4f2f-9978-d93f0e56a833,2.5.4.97=#0c2a4f464242522d64373338346264302d383432662d343363352d626530322d396432623264356566633263,L=Sao Paulo,ST=SP,O=Chicago Advisory Partners,C=BR,2.5.4.5=#130e3433313432363636303030313937,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#0c1450726976617465204f7267616e697a6174696f6e"}

### 9.2. Exemplo Subject Distinguished Name do Certificado - Legível para Humanos:

    subject=businessCategory = Private Organization, jurisdictionC = BR, serialNumber = 43142666000197, C = BR, O = Chicago Advisory Partners, ST = SP, L = Sao Paulo, organizationIdentifier = OFBBR-d7384bd0-842f-43c5-be02-9d2b2d5efc2c, UID = bc97b8f0-cae0-4f2f-9978-d93f0e56a833, CN = web.conftpp.directory.openbankingbrasil.org.br

### 9.3. Relative Distinguished Name (RDN) - Legível para Humanos

    subject=CN=web.conftpp.directory.openbankingbrasil.org.br,UID=bc97b8f0-cae0-4f2f-9978-d93f0e56a833,organizationIdentifier=OFBBR-d7384bd0-842f-43c5-be02-9d2b2d5efc2c,L=Sao Paulo,ST=SP,O=Chicago Advisory Partners,C=BR,serialNumber=43142666000197,jurisdictionC=BR,businessCategory=Private Organization

### 9.4. Relative Distinguished Name (RDN) usando OID - ANS.1:

    subject=2.5.4.3=#0C2E7765622E636F6E667470702E6469726563746F72792E6F70656E62616E6B696E6762726173696C2E6F72672E6272,0.9.2342.19200300.100.1.1=#0C2462633937623866302D636165302D346632662D393937382D643933663065353661383333,2.5.4.97=#0C2A4F464242522D64373338346264302D383432662D343363352D626530322D396432623264356566633263,2.5.4.7=#0C0953616F205061756C6F,2.5.4.8=#0C025350,2.5.4.10=#0C194368696361676F2041647669736F727920506172746E657273,2.5.4.6=#13024252,2.5.4.5=#130E3433313432363636303030313937,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#0C1450726976617465204F7267616E697A6174696F6E 

### 9.5. Subject DN em RDN - Conforme RFC4514 - Padrão do Ecossistema Open Finance Brasil:

    CN=web.conftpp.directory.openbankingbrasil.org.br,UID=bc97b8f0-cae0-4f2f-9978-d93f0e56a833,2.5.4.97=#0c2a4f464242522d64373338346264302d383432662d343363352d626530322d396432623264356566633263,L=Sao Paulo,ST=SP,O=Chicago Advisory Partners,C=BR,2.5.4.5=#130e3433313432363636303030313937,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#0c1450726976617465204f7267616e697a6174696f6e

### 9.6. Tabela com RDN e detalhamento dos OIDs e Codificações.

### Atenção, a tabela abaixo apresenta a sequência conforme item 9.5 em Relative Distinguished Name, se você precisa entender a ordem sequencial subjectDN, verifique os itens 9.2 e 5.2.2.1.

| **Ordem no RDN** | **OID** | **Atributo** | **ASN.1 - Bit String** | **Codificação** |
| --- | --- | --- | --- | --- |
| 1 | 2.5.4.3 | CN | #0C | UTF8 |
| 2 | 0.9.2342.19200300.100.1.1 | UID | #0C | UTF8 |
| 3 | 2.5.4.97 | organizationIdentifier | #0C | UTF8 |
| 4 | 2.5.4.7 | L | #0C | UTF8 |
| 5 | 2.5.4.8 | ST | #0C | UTF8 |
| 6 | 2.5.4.10 | O | #0C | UTF8 |
| 7 | 2.5.4.6 | C | #13 | PrintableString |
| 8 | 2.5.4.5 | serialNumber | #13 | PrintableString |
| 9 | 1.3.6.1.4.1.311.60.2.1.3 | jurisdictionCountryName | #13 | PrintableString |
| 10 | 2.5.4.15 | businessCategory | #0C | UTF8 |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/245694518)
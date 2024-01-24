[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/240649543)

## Prefácio

The normative version in [English](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76709980/EN+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3)

A Estrutura Inicial do Open Finance Brasil (EIOFB) é responsável por criar os padrões e especificações necessários para atender aos requisitos e obrigações da Legislação do Open Finance do Brasil, conforme originalmente delineado pelo [Banco Central do Brasil](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). É possível que alguns dos elementos deste documento estejam sujeitos a direitos de patente. O EIOFB não se responsabiliza pela identificação de qualquer ou todos os direitos de patente.

O Perfil de Segurança Financial-grade API 1.0 do Open Finance Brasil consiste nas seguintes partes:

O Perfil de Segurança Financial-grade API 1.0 do Open Finance Brasil consiste nas seguintes partes:

- [Open Finance Brasil Financial-grade API Security Profile 1.0](/wiki/spaces/DraftOF/pages/76251182)
- Open Finance Brasil Dynamic Client Registration Profile 1.0

Essas partes devem ser usadas com [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OIDC](https://openid.net/specs/openid-connect-core-1_0.html), [OIDR](https://openid.net/specs/openid-connect-registration-1_0.html), [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592), [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) e [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html)

## Introdução

O Perfil de Registro de Cliente Dinâmico (DCR - *Dynamic Client Registration*) do Financal-grade API (FAPI) do Open Finance Brasil é um perfil de [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592) e [OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) que visa fornecer diretrizes de implementação específicas para segurança e interoperabilidade que podem ser aplicadas à identificação, registro e gerenciamento de *Clients OAuth* operando no ecossistema Open Finance Brasil.[¶](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID3-ptbr.html#section-note.2-1)

Embora seja possível codificar um *OpenID Provider* e *Relying Party* desde o princípio usando esta especificação, o principal público para esta especificação são as partes que já possuem uma implementação certificada do [OpenID Connect](https://openid.net/specs/openid-connect-core-1_0.html) e desejam obter a certificação para o Open Finance Brasil.

## Convenções Notacionais

As palavras-chave "*deve*" (shall), "*não deve*" (shall not), "*deveria*" (should), "*não deveria*" (should not) e "*pode*" (may) presentes nesse documento devem ser interpretadas conforme as diretrizes descritas em [ISO Directive Part 2](https://www.iso.org/sites/directives/current/part2/index.xhtml) observando seguinte equivalência:

- "deve" =&gt; equivalente ao termo "shall" e expressa um requerimento definido no documento (nas traduções é similar ao termo "must", que pode denotar um requerimento externo ao documento);
- "não deve" =&gt; equivalente ao termo "shall not" e também expressa um requerimento definido no documento;
- "deveria" e "não deveria"=&gt; equivalente ao termo "should" e "should not" e expressa uma recomendação
- "pode" =&gt; equivalente ao termo "may" indica uma permissão

Estas palavras-chave não são usadas como termos de dicionário, de modo que qualquer ocorrência deles deve ser interpretada como palavras-chave e não devem ser interpretados com seus significados de linguagem natural.

## 1. Escopo

Este documento especifica o método de

- aplicativos cadastrados no [Diretorio de Participantes do Open Finance](https://web.directory.openbankingbrasil.org.br/) para descobrir OpenID Providers que oferecem serviços no ecossistema Open Finance Brasil;
- aplicativos para usar o [OpenID Connect Registration](https://openid.net/specs/openid-connect-registration-1_0.html) para integrar seus aplicativos com OpenID Providers dos bancos; e
- aplicativos para usar [OAuth 2.0 Dynamic Client Registration Management Protocol](https://tools.ietf.org/html/rfc7592) para gerenciar seus aplicativos com OpenID Providers;

Este documento é aplicável a todos os participantes do Open Finance no Brasil.

## 2. Referências normativas

Os seguintes documentos referenciados são indispensáveis para a aplicação deste documento. Para referências datadas, apenas a edição citada se aplica. Para referências não datadas, a última edição do documento referenciado (incluindo quaisquer emendas) se aplica.

[ISODIR2](https://www.iso.org/sites/directives/current/part2/index.xhtml) - ISO/IEC Directives Part 2

[RFC6749](https://tools.ietf.org/html/rfc6749) - The OAuth 2.0 Authorization Framework

[RFC6750](https://tools.ietf.org/html/rfc6750) - The OAuth 2.0 Authorization Framework: Bearer Token Usage

[RFC7636](https://tools.ietf.org/html/rfc7636) - Proof Key for Code Exchange by OAuth Public Clients

[RFC6819](https://tools.ietf.org/html/rfc6819) - OAuth 2.0 Threat Model and Security Considerations

[RFC7519](https://tools.ietf.org/html/rfc7519) - JSON Web Token (JWT)

[RFC7591](https://tools.ietf.org/html/rfc7591) - OAuth 2.0 Dynamic Client Registration Protocol

[RFC7592](https://tools.ietf.org/html/rfc7592) - OAuth 2.0 Dynamic Client Registration Management Protocol

[BCP195](https://tools.ietf.org/html/bcp195) - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS)

[OIDC](https://openid.net/specs/openid-connect-core-1_0.html) - OpenID Connect Core 1.0 incorporating errata set 1

[FAPI-CIBA](https://bitbucket.org/openid/fapi/src/master/Financial_API_WD_CIBA.md) - Financial-grade API: Client Initiated Backchannel Authentication Profile

[RFC4514](https://www.rfc-editor.org/rfc/rfc4514) - Lightweight Directory Access Protocol (LDAP): String Representation of Distinguished Names

[RFC4517](https://www.rfc-editor.org/rfc/rfc4517) - Lightweight Directory Access Protocol (LDAP): Syntaxes and Matching Rules

[OIDD](https://openid.net/specs/openid-connect-discovery-1_0.html) - OpenID Connect Discovery 1.0 incorporating errata set 1

[OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) - OpenID Connect Registration 1.0 incorporating errata set 1

[RFC8705](https://tools.ietf.org/html/rfc8705) - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens

[JARM](https://bitbucket.org/openid/fapi/src/master/Financial_API_JWT_Secured_Authorization_Response_Mode.md) - Financial-grade API: JWT Secured Authorization Response Mode for OAuth 2.0 (JARM)

[PAR](https://tools.ietf.org/html/draft-ietf-oauth-par) - OAuth 2.0 Pushed Authorization Requests

[JAR](https://tools.ietf.org/html/draft-ietf-oauth-jwsreq) - OAuth 2.0 JWT Secured Authorization Request

[FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) - Financial-grade API Security Profile 1.0 - Part 1: Baseline

[FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) - Financial-grade API Security Profile 1.0 - Part 2: Advanced

[OFB-FAPI](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-financial-api-1_ID3.html) - Open Finance Brasil Financial-grade API Security Profile 1.0

[OFB-Cert-Standards](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-certificate-standards-1_ID1.html) - Open Finance Brasil x.509 Certificate Standards

[OFB-DCR/DCM-Swagger](https://raw.githubusercontent.com/OpenBanking-Brasil/specs-seguranca/main/dcr_review/dcr-dcm-swagger.yaml) - DCR & DCM Swagger

## 3. Termos e definições

Para efeitos deste documento, aplicam-se os termos definidos em [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html) e ISO29100.

## 4. Símbolos e Termos abreviados

- **API** - Application Programming Interface (Interface de Programação da Aplicação)
- **DCR** - Dynamic Client Registration (Registro de Cliente Dinâmico)
- **FAPI** - Financial-grade API
- **HTTP** - Hyper Text Transfer Protocol
- **OIDF** - OpenID Foundation
- **REST** - Representational State Transfer
- **SS** - Software Statement (Declaração de Software)
- **SSA** - Software Statement Assertion (Afirmação de Declaração de Software)
- **TLS** - Transport Layer Security

## 5. Introdução

O ecossistema Open Finance Brasil apoia-se em um provedor de confiança ou *diretório de participantes* como a fonte mais valiosa de informações sobre participantes credenciados e softwares que estão autorizados a participar do ecossistema Open Finance Brasil.

Os serviços do Diretório incluem:

- Registro e gerenciamento de software
- Registro e gerenciamento de credenciais de software usando certificados ICP
- Geração de Software Statement Assertion (SSA)

Os participantes do ecossistema devem aproveitar esses serviços para facilitar o registro de cliente OAuth orientado por API usando o processo descrito na cláusula 3.1.1 do [RFC7591](https://tools.ietf.org/html/rfc7591) com metadados adicionais necessários para oferecer suporte ao OpenID Connect definido em [OpenID Connect Registration](https://openid.net/specs/openid-connect-registration-1_0.html).

É importante reforçar que o payload de registro de clientes possui a maior parte de seus atributos não obrigatórios, e que os atributos cujos valores conflitem com os presentes no software statement assertion *serão sobrepostos pelos valores do próprio software statement assertion emitido pelo diretório central*. Nem todos os metadados que um cliente deseja fornecer podem estar contidos em um *software statement*, por exemplo, alternativa [Metadata Languages and Script values](https://openid.net/specs/openid-connect-registration-1_0.html#LanguagesAndScripts). Há casos ainda de metadados de cliente que são um subconjunto dos valores existentes no SSA, como por exemplo os redirect\_URIs.

## 6. Provisionamentos do OpenID Connect Discovery do Open Finance Brasil

### 6.1. Servidor de Autorização

O servidor de autorização deve suportar [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) conforme exigido pelo [Financial-grade API Security Profile 1.0 - Part 1: Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html). Este suporte deve estar explicito tanto na forma como o Servidor de Autorização está registrado no Diretório de Participantes quanto na declaração dos seus atributos no arquivo de Discovery (well-known), respeitando os mecanismos de autenticação certificados pela institição através dos testes de conformidade do Open Finance Brasil.

Adicionalmente, o Servidor de Autorização:

1. deve anunciar sua presença no ecossistema Open Finance Brasil, sendo listada no Diretório de Participantes;
2. deve anunciar todos os recursos API REST do Open Finance Brasil protegidos pelo Provedor OpenID no Diretório de Participantes;
3. deve anunciar suporte para todos os mecanismos de assinatura, criptografia, autenticação e padrões necessários para suportar o [Open Finance Brasil Financial API](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-financial-api-1_ID3.html);
4. deve anunciar suporte para [OpenID Dynamic Client Registration](https://openid.net/specs/openid-connect-registration-1_0.html);
5. pode anunciar `mtls_endpoint_aliases` de acordo com a cláusula [5 RFC 8705 OAuth 2.0 Mutual-TLS Client Authentication e Certificate-Bound Access Tokens](https://tools.ietf.org/html/rfc8705) o `token_endpoint`, `registration_endpoint` e `userinfo_endpoint`;
6. se suportar [OAuth 2.0 Pushed Authorisation Requests](https://tools.ietf.org/html/draft-ietf-oauth-par), deve anunciar por meio de [OIDD](https://openid.net/specs/openid-connect-discovery-1_0.html) `mtls_endpoint_aliases` o `push_authorization_request_endpoint`;
7. se suportar [Financial API - Client Initiated Back Channel Authentication](https://bitbucket.org/openid/fapi/src/master/Financial_API_WD_CIBA.md), deve anunciar através de [OIDD](https://openid.net/specs/openid-connect-discovery-1_0.html) `mtls_endpoint_aliases` o `backchannel_authentication_endpoint`;

### 6.2. Cliente

O cliente deve suportar [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) conforme exigido pelo [Financial-grade API Security Profile 1.0 - Part 1: Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html).

Além disso, o Cliente

1. deve contar com serviços de descoberta do ecossistemas fornecidos apenas pelo Diretório de Participantes;
2. deve derivar os metadados necessários do Authorization Server somente por meio do serviço OpenID Connect Discovery dos Authorization Servers;
3. quando presente, deve usar endpoints anunciados em `mtls_endpoint_aliases` conforme a cláusula 5 [RFC 8705 OAuth 2.0 Mutual-TLS Client Authentication e Certificate-Bound Access Tokens](https://tools.ietf.org/html/rfc8705);

## 7. Provisionamento de registro OpenID Connect do Open Finance Brasil

### 7.1. Servidor de Autorização

O servidor de autorização deve suportar as RFCs de Dynamic Client Registration (DCR) [RFC7591](https://tools.ietf.org/html/rfc7591), Dynamic Client Management (DCM) [RFC7592](https://tools.ietf.org/html/rfc7592) e [OpenID Registration](https://openid.net/specs/openid-connect-registration-1_0.html)

Além disso, o servidor de autorização

1. deve rejeitar as solicitações de registro de cliente dinâmico não realizadas em uma conexão protegida com mTLS usando certificados emitidos pelo Brasil ICP (produção) ou o Diretório de Participantes (sandbox);
2. deve validar que a solicitação contém *software\_statement* JWT assinado usando o algoritmo `PS256` emitido pelo Diretório de Participantes do Open Finance Brasil;
3. deve validar que o *software\_statement* foi emitido (iat - *issued at*) não mais de 5 minutos antes do pedido ser recebido;
4. deve validar que um atributo `jwks` (definida por valor) **não** foi incluído, e sim declarado como referência no atributo `jwks_uri`;
5. deve, quando informado, validar que o `jwks_uri` corresponda ao `software_jwks_uri` fornecido na declaração do software;
6. deve exigir e validar que o `redirect_uris` corresponda ou contenha um subconjunto dos valores de `software_redirect_uris` fornecidos no *software\_statement*;
7. deve exigir e validar que todos os mecanismos de autenticação de cliente cumpram os requisitos definidos nas [RFC7591](https://tools.ietf.org/html/rfc7591) e [RFC7592](https://tools.ietf.org/html/rfc7592), através da validação do `registration_access_token` e, como conexão segura, da cadeia de certificados confiáveis ICP-Brasil.
8. *removido*;
9. deve validar se os escopos solicitados são adequados para as permissões regulatórias autorizadas da instituição e contidas no \_software\_statement. A relação de permissões regulatórias e os escopos correspondentes está descrita nas seções a seguir.
10. deve, sempre que possível, validar os metadados declarados pelo cliente em relação aos metadados fornecidos no *software\_statement*, adotando os valores presentes no SSA com precedência.
11. deve aceitar todos os nomes x.500 AttributeType definidas no *Distinguished Name* dos Perfis de Certificado x.509 definidos em [Open Finance Brasil x.509 Certificate Standards](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76710230/EN+Padr+o+de+Certificados+Open+Finance+Brasil+1.0);
12. se for compatível com o mecanismo de autenticação do cliente `tls_client_auth`, conforme definido em [RFC8705](https://tools.ietf.org/html/rfc8705), somente deve aceitar `tls_client_auth_subject_dn` como uma indicação do valor do atributo *subject* do certificado, conforme definido na cláusula 2.1.2 [RFC8705](https://tools.ietf.org/html/rfc8705);
13. O valor do campo *UID* do certificado deve coincidir com o enviado no SSA, onde o campo *UID* deve conter o valor do campo *software\_id* do SSA.
14. O campo *organizationIdentifier* será encontrado no subject\_DN em formato ASN.1 e deverá ser decodificado respeitando o string enconding correspondente. O valor do campo *organizationIdentifier* do certificado que deve conter o prefixo correspondente ao Registration Reference *OFBBR-* seguido do valor do campo *org\_id* do SSA. Deve-se converter os valores do campo OID 2.5.4.97 do formato ASN.1 para texto legível para humanos. Para certificados emitidos até 31 de Agosto de 2022: o valor do campo *OU* do certificado deve conter o valor do campo *org\_id* do SSA.
15. deve, durante o processo de handshake TLS, usar a regra `distinguishedNameMatch` para comparar os valores DN conforme definido na [RFC4517](https://www.rfc-editor.org/rfc/rfc4517).[¶](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID3-ptbr.html#section-7.1-3.15)
16. deve ser garantido a todos, após os mesmos atos de consentimentos permanentes, para que também sejam alterados para instituições receptoras de dados transparentes (TPP).
17. deve realizar recertificação FAPI e DCR OIDF após eventuais alterações sistêmicas.
18. O valor do atributo software\_api\_webhook\_uris contido como atributo no JWS em software\_statement deverá ser comparado com o campo webhook\_uris. Caso os valores não sejam exatamente iguais, deve-se retornar o erro, com HTTP status code setado para 400, `error` preenchido como `invalid_webhook_uris` e `error_description` preenchido com `The content of the webhook_uris field differs from what was registered in the software_statement observed through the JWS field's software_api_webhook_uris`.
19. Se o campo webhook\_uris não for declarado no payload, a funcionalidade webhook deverá ser considerado como desativado para o client em questão.

Estas disposições aplicam-se igualmente ao processamento de pedidos [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592) e [OpenID Registration](https://openid.net/specs/openid-connect-registration-1_0.html)

#### 7.1.1. Aplicando Server Defaults

Quando as propriedades de uma solicitação DCR não estão incluídas e não são obrigatórias na especificação, o Authorization Server deve aplicar os padrões do cliente da seguinte maneira:

1. deve selecionar e aplicar o algoritmo de criptografia e a escolha da cifra a partir dos conjuntos mais recomendados de cifra da IANA que são suportados pelo Servidor de Autorização;
2. deve preencher *defaults* a partir de valores da afirmação de *software\_statement*, sempre que possível;
3. deve conceder ao cliente permissão para o conjunto completo de escopos potenciais com base nas permissões regulatórias de softwares incluídas no *software\_statement*;

#### 7.1.2. Análise do Distinguished Name do Certificado

A cláusula 3 do [Lightweight Directory Access Protocol (LDAP): String Representation of Distinguished Names](https://www.rfc-editor.org/rfc/rfc4514) define os OIDs obrigatórios cujas as *strings* do AttributeType (descritores) devem ser reconhecidos pelos implementadores. Esta lista obrigatória não inclui vários dos OIDs definidos em [Open Finance Brasil x.509 Certificate Standards](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76710230/EN+Padr+o+de+Certificados+Open+Finance+Brasil+1.0), nem existe um mecanismo definido para os Servidores de Autorização publicarem informações sobre o formato que eles esperam de uma Solicitação Dinâmica de Registro do Cliente (*Dynamic Client Registrarion*) que inclui um `tls_client_auth_subject_dn`.

Para resolver essa ambiguidade, o Servidor de Autorização deve aceitar exclusivamente os AttributeType (descritores) definidas no último parágrafo da cláusula 3 [RFC4514](https://www.rfc-editor.org/rfc/rfc4514) em formato string,  também deve aceitar em formato OID, com seus valores em ASN.1, todos os AttributeTypes definidos no Distinguished Name [Open Finance Brasil x.509 Certificate Standards](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76710230/EN+Padr+o+de+Certificados+Open+Finance+Brasil+1.0) ou adicionados pela Autoridade Certificadora.

Em caso de não atendimento destes requisitos o Servidor de Autorização deverá rejeitar o registro.

Segue na tabela abaixo como deve ser feita a decodificação:

- Obtenha na ordem reversa os atributos do certificado
- Concatene cada RDN (RelativeDistinguishedName) com uma virgula (',')
- Use as strings da RFC (CN, L, ST, O, OU, C, Street, DC, UID) com o valor dos seus atributos legível para humanos
- Use os OIDs dos atributos definidos nesta especificação para uso no OFB (businessCategory = OID 2.5.4.15, jurisdictionCountryName = OID 1.3.6.1.4.1.311.60.2.1.3, serialNumber = OID 2.5.4.5, organizationIdentifier = OID 2.5.4.97) com o valor dos seus atributos em formato ASN.1 seguindo a RFC4514, sendo que:

    - Os nomes dos atributos devem ser definidos seguindo a notação ponto-decimal, sem adição de prefixo "OID", ex. "2.5.4.15", seguido dos sinais de ('=#') mais o valor hexadecimal do atributo, exemplo final: 2.5.4.15=#0C1450726976617465204F7267616E697A6174696F6E
    - Não há qualquer restrição para as codificações/formatações utilizadas nos valores dos atributos. Deve ser respeitado o uso em hexadecimal apresentado na codificação utilizada no atributo do certificado (PrintableString, UTF8String, etc). Este item atende à opcionalidade do formato já estabelecido pela AC frente aos normativos ICP e ao itens 2.3, 2.4 e 5.2 da RFC4514. -Para atender ao padrão DCR, converta os valores ASN.1 do OID 2.5.4.97 organizationIdentifier para texto legível para humanos, utilize recursos do seu API gateway ou uma biblioteca padrão do tipo ASN.1 ou se necessário ainda desenvolva manualmente. Para isso recupere o valor completo do OID 2.5.4.97 contido no subject\_DN. Remova a notação ponto-decimal (2.5.4.97). Remova os sinais de ('=#'). Converta o valor de hexadecimal para texto. Aplique um filtro usando expressão regular para recuperar o org\_id após ('OFBBR-'), por exemplo: 2.5.4.97=#132A4F464242522D36376335373838322D303433622D313165632D396130332D303234326163313330303033. Remova a notação ponto-decimal e sinais ('=#'): 2.5.4.97=#. Converta o valor hexadecimal 132A4F464242522D36376335373838322D303433622D313165632D396130332D303234326163313330303033 para texto: \*\*OFBBR-67c57882-043b-11ec-9a03-0242ac130003. Aplique a expressão regular e recupere o org\_id que está contido após 'OFBBR-':67c57882-043b-11ec-9a03-0242ac130003.

Seguem abaixo exemplos para os atributos obrigatórios das ACs ativas até 31 de Agosto de 2022:

| [*Table 1*](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID3-ptbr.html#table-1) |  |
| subject\_dn | Issuer |
| --- | --- |
| UID=67c57882-043b-11ec-9a03-0242ac130003,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#131450726976617465204f7267616e697a6174696f6e,2.5.4.5=#130e3133333533323336303030313839,CN= [mycn.bank.gov.br](http://mycn.bank.gov.br/),OU=497e1ffe-b2a2-4a4e-8ef0-70633fd11b59,O=My Public Bank,L=BRASILIA,ST=DF,C=BR | issuer=CN=Open Banking SANDBOX Issuing CA - G1,OU=Open Banking,O=Open Banking Brasil,C=BR |
| UID=67c57882-043b-11ec-9a03-0242ac130003,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#0C0F427573696E65737320456E74697479,[CN=mycn.bank.gov.br](http://cn%3Dmycn.bank.gov.br/),2.5.4.5=#130e3133333533323336303030313839,OU=497e1ffe-b2a2-4a4e-8ef0-70633fd11b59,O=My Public Bank,L=BRASILIA,ST=DF,C=BR | issuer=CN=Autoridade Certificadora do SERPRO SSLv1,OU=Autoridade Certificadora Raiz Brasileira v10,O=ICP-Brasil,C=BR |
| 1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#131450726976617465204f7267616e697a6174696f6e,UID=67c57882-043b-11ec-9a03-0242ac130003,[CN=openbanking.mybank.com.br](http://cn%3Dopenbanking.mybank.com.br/),2.5.4.5=#130e3133333533323336303030313839,OU=497e1ffe-b2a2-4a4e-8ef0-70633fd11b59,L=Goiania,ST=GO,O=MyBank SA,C=BR | issuer=CN=AC SOLUTI SSL EV,OU=Autoridade Certificadora Raiz Brasileira v10,O=ICP-Brasil,C=BR |
| [CN=mycn.bank.com.br](http://cn%3Dmycn.bank.com.br/),UID=67c57882-043b-11ec-9a03-0242ac130003,OU=497e1ffe-b2a2-4a4e-8ef0-70633fd11b59,L=Sao Paulo,ST=SP,O=MyBank SA,C=BR,2.5.4.5=#130e3133333533323336303030313839,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#0C0F427573696E65737320456E74697479 | issuer=CN=AC SERASA SSL EV,OU=Autoridade Certificadora Raiz Brasileira v10,O=ICP-Brasil,C=BR |

Seguem abaixo exemplos para os atributos obrigatórios das ACs ativas após 31 de Agosto de 2022:

| [*Table 2*](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID3-ptbr.html#table-2) |  |
| subject\_dn | Issuer |
| --- | --- |
| UID=67c57882-043b-11ec-9a03-0242ac130003,2.5.4.97=#0C2A4F464242522D36376335373838322D303433622D313165632D396130332D303234326163313330303033,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#131450726976617465204f7267616e697a6174696f6e,2.5.4.5=#130e3133333533323336303030313839,CN= [mycn.bank.gov.br](http://mycn.bank.gov.br/),OU=497e1ffe-b2a2-4a4e-8ef0-70633fd11b59,O=My Public Bank,L= BRASILIA,ST=DF,C=BR | issuer=CN=AC SERASA SSL EV,OU=Autoridade Certificadora Raiz Brasileira v10,O=ICP-Brasil,C=BR |
| UID=67c57882-043b-11ec-9a03-0242ac130003,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#131450726976617465204f7267616e697a6174696f6e,[CN=mycn.bank.gov.br](http://cn%3Dmycn.bank.gov.br/),2.5.4.5=#130e3133333533323336303030313839,2.5.4.97=#132A4F464242522D36376335373838322D303433622D313165632D396130332D303234326163313330303033,O=My Public Bank,L=BRASILIA,ST=DF,C=BR |  |

### 7.2. Funções regulatórias para mapeamentos OpenID e OAuth 2.0

Para participar do ecossistema do Open Finance, as instituições credenciadas devem se cadastrar no Diretório de Participantes de acordo com seus papéis regulatórios. Essas funções refletem a autorização do Banco Central para as instituições e, consequentemente, as APIs que podem utilizar.

A tabela a seguir descreve as funções regulatórias do Open Finance e o mapeamento de escopos do OAuth 2.0 relacionado. Se os escopos forem omitidos durante o processo de DCR, o Servidor de Autorização deve conceder o conjunto completo de escopos potenciais com base nas funções regulatórias registradas para o banco, conforme descrito na seção Server Defaults.

| Papel Regulador | Descrição | Escopos Permitidos | Fase-alvo |
| --- | --- | --- | --- |
| DADOS | Instituição transmissora / receptora de dados (AISP) | openid<br><br>accounts<br><br>credit-cards-accounts<br><br>consents<br><br>customers<br><br>invoice-financings<br><br>financings<br><br>loans<br><br>unarranged-accounts-overdraft<br><br>resources<br><br>credit-fixed-incomes<br><br>exchanges | Fase 2 e Fase 4 |
| PAGTO | Instituição prestadora de serviço de iniciação de pagamentos (PISP) | openid<br><br>payments | Fase 3 |
| CONTA | Instituição detentora de conta (ASPSP) | openid | Fase 3 |
| CCORR | Correspondente de crédito | openid | Fase 3\* |

É necessário validar as roles ativas no *software\_statement* da aplicação. Na validação dessa informação deve ser utilizado o campo \_software\_statement\_roles, e deve ser verificado se as roles listadas estão ativas.

### 7.3. Registro do Cliente

Deve-se ser respeitada a seção 4.2.11 da RFC 4517 (caseIgnoreMatch). No processo de registro do cliente, utilizando-se o método de autenticação *tls\_client\_auth*, o cliente deve encaminhar o campo \_tls\_client\_auth\_subject\_dn\_ com os AttibuteTypes(Descritores) em formato definido no item Análise do Distinguished Name do Certificado. Em caso de não aderencia a este padrão o registro será rejeitado.

## 8. Declaração de Software

Uma declaração de software (*software\_statement*) é um JSON Web Token (JWT) [RFC7519](https://tools.ietf.org/html/rfc7519) que afirma valores de metadados sobre o software cliente como um todo. Na estrutura do Open Finance Brasil, esse *software\_statement* é assinado pelo Diretório de Participantes, e sua assinatura DEVE ser validada pelos Servidores de Autorizacao usando as chaves públicas disponíveis na seção a seguir.

### 8.1. Atributos da Declaração de Software (Claims)

O exemplo a seguir contém todos os atributos atualmente incluídos em um *software\_statement*:

| {<br>      "software_mode": "Live",<br>      "software_redirect_uris": [<br>        "https://www.raidiam.com/accounting/cb"<br>      ],<br>      "software_api_webhook_uris": ["https://www.myitp.com/mykong3"],<br>      "software_statement_roles": [<br>        {<br>          "role": "DADOS",<br>          "authorisation_domain": "Open Banking",<br>          "status": "Active"<br>        },<br>        {<br>          "role": "PAGTO",<br>          "authorisation_domain": "Open Banking",<br>          "status": "Active"<br>        }<br>      ],<br>      "software_client_name": "Raidiam Accounting",<br>      "org_status": "Active",<br>      "software_client_id": "Cki1EbvjwyhPB12NGLlz2",<br>      "iss": "Open Banking Open Banking Brasil prod SSA issuer",<br>      "software_tos_uri": "https://www.raidiam.com/accounting/tos.html",<br>      "software_client_description": "Raidiam Accounting leverage cutting edge open banking access to bring you real time up to date views of your finances",<br>      "software_jwks_uri": "https://keystore.directory.openbankingbrasil.org.br/b961c4eb-509d-4edf-afeb-35642b38185d/25556d5a-b9dd-4e27-aa1a-cce732fe74de/application.jwks",<br>      "software_policy_uri": "https://www.raidiam.com/accounting/policy.html",<br>      "software_id": "25556d5a-b9dd-4e27-aa1a-cce732fe74de",<br>      "software_client_uri": "https://www.raidiam.com/accounting.html",<br>      "software_jwks_inactive_uri": "https://keystore.directory.openbankingbrasil.org.br/b961c4eb-509d-4edf-afeb-35642b38185d/25556d5a-b9dd-4e27-aa1a-cce732fe74de/inactive/application.jwks",<br>      "software_jwks_transport_inactive_uri": "https://keystore.directory.openbankingbrasil.org.br/b961c4eb-509d-4edf-afeb-35642b38185d/25556d5a-b9dd-4e27-aa1a-cce732fe74de/inactive/transport.jwks",<br>      "software_jwks_transport_uri": "https://keystore.directory.openbankingbrasil.org.br/b961c4eb-509d-4edf-afeb-35642b38185d/25556d5a-b9dd-4e27-aa1a-cce732fe74de/transport.jwks",<br>      "software_logo_uri": "https://www.raidiam.com/accounting/logo.png",<br>      "org_id": "b961c4eb-509d-4edf-afeb-35642b38185d",<br>      "org_number": "112233445566",<br>      "software_environment": "production",<br>      "software_version": "1.1",<br>      "software_roles": [<br>        "DADOS",<br>        "PAGTO"<br>      ],<br>      "org_name": "Open Banking Brasil",<br>      "iat": 1620060821,<br>      "organisation_competent_authority_claims": [<br>        {<br>          "authorisation_domain": "Open Banking",<br>          "authorisations": [],<br>          "registration_id": "13353236-OBB-CONTA",<br>          "authority_id": "687a1c94-b360-4e04-9589-0fa5cb16451b",<br>          "authority_name": "Banco Central",<br>          "authorisation_role": "CONTA",<br>          "authority_code": "BCB",<br>          "status": "Active"<br>        },<br>        {<br>          "authorisation_domain": "Open Banking",<br>          "authorisations": [],<br>          "registration_id": "13353236-OBB-DADOS",<br>          "authority_id": "687a1c94-b360-4e04-9589-0fa5cb16451b",<br>          "authority_name": "Banco Central",<br>          "authorisation_role": "DADOS",<br>          "authority_code": "BCB",<br>          "status": "Active"<br>        },<br>        {<br>          "authorisation_domain": "Open Banking",<br>          "authorisations": [],<br>          "registration_id": "13353236-OBB-PAGTO",<br>          "authority_id": "687a1c94-b360-4e04-9589-0fa5cb16451b",<br>          "authority_name": "Banco Central",<br>          "authorisation_role": "PAGTO",<br>          "authority_code": "BCB",<br>          "status": "Active"<br>        }<br>      ]<br>    } |
| --- |

## 9. Processamento de solicitação de registro de cliente dinâmico
![att240649642]([PT]%20Open%20Finance%20Brasil%20Financial-grade%20API%20Dynamic%20Client%20Registration%201.0%20Implementers%20Draft%203/attachments/image-20230328-193430.png_version=5&modificationDate=1692203977372&cacheVersion=1&api=v2&width=544&height=448)
Os passos do processo de extração do subject\_DN estão descritos na seção Análise do Distinguished Name do Certificado.
![att240649639]([PT]%20Open%20Finance%20Brasil%20Financial-grade%20API%20Dynamic%20Client%20Registration%201.0%20Implementers%20Draft%203/attachments/image-20230328-193534.png_version=4&modificationDate=1689882803940&cacheVersion=1&api=v2)

O exemplo de código Javascript para extração do subject\_DN e o respectivo certificado teste.pem utilizado neste exemplo estão descritos abaixo.

| const {X509Certificate} = require('crypto')<br>    const fs = require('fs')<br>     <br>    const x509 = new X509Certificate(fs.readFileSync('teste.pem'))<br>    const sub = x509.subject<br>    var array = sub.split(/\r?\n|\r|\n/g)<br>     <br>    function hexa(x){<br>            var res = ''<br>            for (var i=0; i < x.length ; i++) { res += x.charCodeAt(i).toString(16) }<br>            return res<br>    }<br>     <br>    function retornaMatch(palavra, filtro){<br>            let match = palavra.match(filtro)<br>            if(match){ return match[0] }<br>    }<br>     <br>    var array1 = /organizationIdentifier=[o|O][f|F][b|B]{2}[r|R][-].*[,]/<br>    var novaArray1 = retornaMatch(String(array),array1)<br>    novaArray1 = String(novaArray1).split('=')<br>    novaArray1[1] = novaArray1[1].replace(/,(\s+)?$/, '')<br>     <br>    var array2 = /jurisdictionC=[a-z|A-Z]{2},/<br>    var novaArray2 = retornaMatch(String(array),array2)<br>    novaArray2 = String(novaArray2).split('=')<br>    novaArray2[1] = novaArray2[1].replace(/,(\s+)?$/, '')<br>     <br>    var array3 = /businessCategory=\w+\s\w+,/<br>    var novaArray3 = retornaMatch(String(array),array3)<br>    novaArray3 = String(novaArray3).split('=')<br>    novaArray3[1] = novaArray3[1].replace(/,(\s+)?$/, '')<br>     <br>    var array4 = /serialNumber=[0-9]{14},/<br>    var novaArray4 = retornaMatch(String(array),array4)<br>    novaArray4 = String(novaArray4).split('=')<br>    novaArray4[1] = novaArray4[1].replace(/,(\s+)?$/, '')<br>     <br>    function parseX509(array, encode){<br>            var tam = array.length-1<br>            var novaArray = []<br>     <br>            novaArray[0] = array[tam]<br>            novaArray[1] = '2.5.4.97=' +encode +'2A' + hexa(novaArray1[1])<br>            novaArray[2] = '1.3.6.1.4.1.311.60.2.1.3=' +encode +'02' + hexa(novaArray2[1])<br>            novaArray[3] = '2.5.4.15=' +encode +'14' + hexa(novaArray3[1])<br>            novaArray[4] = '2.5.4.5=' +encode +'0E' + hexa(novaArray4[1])<br>            novaArray[5] = array[tam-5]<br>            novaArray[6] = array[tam-6]<br>            novaArray[7] = array[tam-7]<br>            novaArray[8] = array[tam-8]<br>            novaArray[9] = array[tam-9]<br>     <br>            var res = 'subject='<br>            for(i=0; i < novaArray.length ; i++){<br>                    res += novaArray[i]<br>                    res += ','<br>            }<br>            res = res.replace(/,(\s+)?$/, '')<br>     <br>            return res<br>    }<br>     <br>    console.log('Suject DN em Printable String: ', parseX509(array, '#13'))<br>    console.log('Suject DN em UTF-8: ', parseX509(array, '#0C')) |
| --- |

| ----BEGIN CERTIFICATE-----<br>    MIIHSzCCBjOgAwIBAgIUKga83ZMp8P0fd24M2oQUvq1ViPcwDQYJKoZIhvcNAQEL<br>    BQAwcTELMAkGA1UEBhMCQlIxHDAaBgNVBAoTE09wZW4gQmFua2luZyBCcmFzaWwx<br>    FTATBgNVBAsTDE9wZW4gQmFua2luZzEtMCsGA1UEAxMkT3BlbiBCYW5raW5nIFNB<br>    TkRCT1ggSXNzdWluZyBDQSAtIEcxMB4XDTIyMDgyOTE3NDYwMFoXDTIzMDkyODE3<br>    NDYwMFowggFDMQswCQYDVQQGEwJCUjELMAkGA1UECBMCU1AxDzANBgNVBAcTBkxP<br>    TkRPTjEcMBoGA1UEChMTT3BlbiBCYW5raW5nIEJyYXNpbDFDMEEGA1UEAxM6aHR0<br>    cHM6Ly93ZWIuY29uZm9ybWFuY2UuZGlyZWN0b3J5Lm9wZW5iYW5raW5nYnJhc2ls<br>    Lm9yZy5icjEXMBUGA1UEBRMONDMxNDI2NjYwMDAxOTcxGjAYBgNVBA8TEUdvdmVy<br>    bm1lbnQgRW50aXR5MRMwEQYLKwYBBAGCNzwCAQMTAlVLMTMwMQYDVQRhEypPRkJC<br>    Ui03NGU5MjlkOS0zM2I2LTRkODUtOGJhNy1jMTQ2Yzg2N2E4MTcxNDAyBgoJkiaJ<br>    k/IsZAEBEyQxMDEyMDM0MC0zMzE4LTRiYWYtOTllMi0wYjU2NzI5YzRhYjIwggEi<br>    MA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC7BjqM17OFx1eN5bdkZIz2cWq5<br>    /eWuQONogpz2e38AyTsA8xxtTmYABTAHnS6QWBrGqK7XDxKks6srHzbNkr7UVR5+<br>    fg5EfF/SqqWeatFstw3rr5qsN3XnHJUCFsBD6R6IetmrnGlWSIAoJFfqKtYx594U<br>    w0dnE5egBfas087RqSM2V5H9uRcjSfB40MqANERDAZEeftGkNYyzj9Csa5g+WZLH<br>    GqdtW28y7d2tOK4px0e99dAuNRjofCLpRoVH8Ez8ayy7+iJoo4CNRwoGGCayRatK<br>    hrsp6CQ1/0X2sn3Rc02QiiCRhEY3AUYSgiUm64YcAbsO913YtC92lSMUe9gDAgMB<br>    AAGjggMFMIIDATAMBgNVHRMBAf8EAjAAMB0GA1UdDgQWBBQ7XBioIXwyC2PYczsD<br>    uwtKXNck1jAfBgNVHSMEGDAWgBSGf1itF/WCtk60BbP7sM4RQ99MvjBMBggrBgEF<br>    BQcBAQRAMD4wPAYIKwYBBQUHMAGGMGh0dHA6Ly9vY3NwLnNhbmRib3gucGtpLm9w<br>    ZW5iYW5raW5nYnJhc2lsLm9yZy5icjBLBgNVHR8ERDBCMECgPqA8hjpodHRwOi8v<br>    Y3JsLnNhbmRib3gucGtpLm9wZW5iYW5raW5nYnJhc2lsLm9yZy5ici9pc3N1ZXIu<br>    Y3JsMEUGA1UdEQQ+MDyCOmh0dHBzOi8vd2ViLmNvbmZvcm1hbmNlLmRpcmVjdG9y<br>    eS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnIwDgYDVR0PAQH/BAQDAgWgMBMGA1Ud<br>    JQQMMAoGCCsGAQUFBwMCMIIBqAYDVR0gBIIBnzCCAZswggGXBgorBgEEAYO6L2QB<br>    MIIBhzCCATYGCCsGAQUFBwICMIIBKAyCASRUaGlzIENlcnRpZmljYXRlIGlzIHNv<br>    bGVseSBmb3IgdXNlIHdpdGggUmFpZGlhbSBTZXJ2aWNlcyBMaW1pdGVkIGFuZCBv<br>    dGhlciBwYXJ0aWNpcGF0aW5nIG9yZ2FuaXNhdGlvbnMgdXNpbmcgUmFpZGlhbSBT<br>    ZXJ2aWNlcyBMaW1pdGVkcyBUcnVzdCBGcmFtZXdvcmsgU2VydmljZXMuIEl0cyBy<br>    ZWNlaXB0LCBwb3NzZXNzaW9uIG9yIHVzZSBjb25zdGl0dXRlcyBhY2NlcHRhbmNl<br>    IG9mIHRoZSBSYWlkaWFtIFNlcnZpY2VzIEx0ZCBDZXJ0aWNpY2F0ZSBQb2xpY3kg<br>    YW5kIHJlbGF0ZWQgZG9jdW1lbnRzIHRoZXJlaW4uMEsGCCsGAQUFBwIBFj9odHRw<br>    Oi8vcmVwb3NpdG9yeS5zYW5kYm94LnBraS5vcGVuYmFua2luZ2JyYXNpbC5vcmcu<br>    YnIvcG9saWNpZXMwDQYJKoZIhvcNAQELBQADggEBACjaIPM71+6aarcCzUUscTuu<br>    N1ZHazWsGBAsVyPPLgC/cxX1IqAA8W9pLaxRBO4F/CVsqJf2ArS0HMB6aZxVxSty<br>    Ka//oAI/qd6Z+8vx10iT2u359yTXBA7AoIQGAeoC0A2UyKG32V2OtCOKdSQVtu2F<br>    MOaDZhdjxrJACAt8/nTXOZubqFk8laFVo9dmdXxdFd0vejCpvcVQItkjmTsjihMp<br>    xpVPAP52I/ZW3tct2cMJfaw+NulaYgVKhcAu/HGtT0KKbPWq8E7IgtuQrqaLe9n6<br>    Jz3aHfCWJ7IYgBbIRyMhd5oi5Dp8txLxrpTgJ2V9+8wyvzijWbUBHMJnXuiXojM=<br>    -----END CERTIFICATE----- |
| --- |

### 9.1. Enviar uma solicitação com uma declaração de software

Este exemplo inclui vários campos opcionais, alguns dos quais podem não ser aplicáveis a algumas implantações. Para um guia completo dos atributos e sua obrigatoriedade, consultar o Swagger DCR [OFB-DCR/DCM-Swagger](https://raw.githubusercontent.com/OpenBanking-Brasil/specs-seguranca/main/dcr_review/dcr-dcm-swagger.yaml). A quebra de linha dentro dos valores são apenas para fins de exibição.

| POST /reg HTTP/1.1<br>    Host: auth.raidiam.com<br>    Content-Type: application/json<br>    {<br>      "application_type": "web",<br>      "grant_types": [<br>        "client_credentials",<br>        "authorization_code",<br>        "refresh_token",<br>        "implicit"<br>      ],<br>      "id_token_signed_response_alg": "PS256",<br>      "require_auth_time": false,<br>      "response_types": [<br>        "code id_token",<br>        "id_token"<br>      ],<br>      "software_statement": "eyJraWQiOiJzaWduZXIiLCJ0eXAiOiJKV1QiLCJhbGciOiJQUzI1NiJ9.eyJzb2Z0d2FyZV9tb2RlIjoiTGl2ZSIsInNvZnR3YXJlX3JlZGlyZWN0X3VyaXMiOlsiaHR0cHM6XC9cL3d3dy5yYWlkaWFtLmNvbVwvYWNjb3VudGluZ1wvY2IiXSwic29mdHdhcmVfc3RhdGVtZW50X3JvbGVzIjpbeyJyb2xlIjoiREFET1MiLCJhdXRob3Jpc2F0aW9uX2RvbWFpbiI6Ik9wZW4gQmFua2luZyIsInN0YXR1cyI6IkFjdGl2ZSJ9LHsicm9sZSI6IlBBR1RPIiwiYXV0aG9yaXNhdGlvbl9kb21haW4iOiJPcGVuIEJhbmtpbmciLCJzdGF0dXMiOiJBY3RpdmUifV0sInNvZnR3YXJlX2NsaWVudF9uYW1lIjoiUmFpZGlhbSBBY2NvdW50aW5nIiwib3JnX3N0YXR1cyI6IkFjdGl2ZSIsInNvZnR3YXJlX2NsaWVudF9pZCI6IkNraTFFYnZqd3loUEIxMk5HTGx6MiIsImlzcyI6Ik9wZW4gQmFua2luZyBPcGVuIEJhbmtpbmcgQnJhc2lsIHByb2QgU1NBIGlzc3VlciIsInNvZnR3YXJlX3Rvc191cmkiOiJodHRwczpcL1wvd3d3LnJhaWRpYW0uY29tXC9hY2NvdW50aW5nXC90b3MuaHRtbCIsInNvZnR3YXJlX2NsaWVudF9kZXNjcmlwdGlvbiI6IlJhaWRpYW0gQWNjb3VudGluZyBsZXZlcmFnZSBjdXR0aW5nIGVkZ2Ugb3BlbiBiYW5raW5nIGFjY2VzcyB0byBicmluZyB5b3UgcmVhbCB0aW1lIHVwIHRvIGRhdGUgdmlld3Mgb2YgeW91ciBmaW5hbmNlcyIsInNvZnR3YXJlX2p3a3NfZW5kcG9pbnQiOiJodHRwczpcL1wva2V5c3RvcmUuZGlyZWN0b3J5Lm9wZW5iYW5raW5nYnJhc2lsLm9yZy5iclwvYjk2MWM0ZWItNTA5ZC00ZWRmLWFmZWItMzU2NDJiMzgxODVkXC8yNTU1NmQ1YS1iOWRkLTRlMjctYWExYS1jY2U3MzJmZTc0ZGVcL2FwcGxpY2F0aW9uLmp3a3MiLCJzb2Z0d2FyZV9wb2xpY3lfdXJpIjoiaHR0cHM6XC9cL3d3dy5yYWlkaWFtLmNvbVwvYWNjb3VudGluZ1wvcG9saWN5Lmh0bWwiLCJzb2Z0d2FyZV9pZCI6IjI1NTU2ZDVhLWI5ZGQtNGUyNy1hYTFhLWNjZTczMmZlNzRkZSIsInNvZnR3YXJlX2NsaWVudF91cmkiOiJodHRwczpcL1wvd3d3LnJhaWRpYW0uY29tXC9hY2NvdW50aW5nLmh0bWwiLCJzb2Z0d2FyZV9qd2tzX2luYWN0aXZlX2VuZHBvaW50IjoiaHR0cHM6XC9cL2tleXN0b3JlLmRpcmVjdG9yeS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnJcL2I5NjFjNGViLTUwOWQtNGVkZi1hZmViLTM1NjQyYjM4MTg1ZFwvMjU1NTZkNWEtYjlkZC00ZTI3LWFhMWEtY2NlNzMyZmU3NGRlXC9pbmFjdGl2ZVwvYXBwbGljYXRpb24uandrcyIsInNvZnR3YXJlX2p3a3NfdHJhbnNwb3J0X2luYWN0aXZlX2VuZHBvaW50IjoiaHR0cHM6XC9cL2tleXN0b3JlLmRpcmVjdG9yeS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnJcL2I5NjFjNGViLTUwOWQtNGVkZi1hZmViLTM1NjQyYjM4MTg1ZFwvMjU1NTZkNWEtYjlkZC00ZTI3LWFhMWEtY2NlNzMyZmU3NGRlXC9pbmFjdGl2ZVwvdHJhbnNwb3J0Lmp3a3MiLCJzb2Z0d2FyZV9qd2tzX3RyYW5zcG9ydF9lbmRwb2ludCI6Imh0dHBzOlwvXC9rZXlzdG9yZS5kaXJlY3Rvcnkub3BlbmJhbmtpbmdicmFzaWwub3JnLmJyXC9iOTYxYzRlYi01MDlkLTRlZGYtYWZlYi0zNTY0MmIzODE4NWRcLzI1NTU2ZDVhLWI5ZGQtNGUyNy1hYTFhLWNjZTczMmZlNzRkZVwvdHJhbnNwb3J0Lmp3a3MiLCJzb2Z0d2FyZV9sb2dvX3VyaSI6Imh0dHBzOlwvXC93d3cucmFpZGlhbS5jb21cL2FjY291bnRpbmdcL2xvZ28ucG5nIiwib3JnX2lkIjoiYjk2MWM0ZWItNTA5ZC00ZWRmLWFmZWItMzU2NDJiMzgxODVkIiwic29mdHdhcmVfZW52aXJvbm1lbnQiOiJwcm9kdWN0aW9uIiwic29mdHdhcmVfdmVyc2lvbiI6MS4xMCwic29mdHdhcmVfcm9sZXMiOlsiREFET1MiLCJQQUdUTyJdLCJvcmdfbmFtZSI6Ik9wZW4gQmFua2luZyBCcmFzaWwiLCJpYXQiOjE2MTgzMzYyNjIsIm9yZ2FuaXNhdGlvbl9jb21wZXRlbnRfYXV0aG9yaXR5X2NsYWltcyI6W3siYXV0aG9yaXNhdGlvbl9kb21haW4iOiJPcGVuIEJhbmtpbmciLCJhdXRob3Jpc2F0aW9ucyI6W10sInJlZ2lzdHJhdGlvbl9pZCI6IjEzMzUzMjM2LU9CQi1DT05UQSIsImF1dGhvcml0eV9pZCI6IjY4N2ExYzk0LWIzNjAtNGUwNC05NTg5LTBmYTVjYjE2NDUxYiIsImF1dGhvcmlzYXRpb25fcm9sZSI6IkNPTlRBIiwiYXV0aG9yaXR5X2NvZGUiOiJCQ0IiLCJzdGF0dXMiOiJBY3RpdmUifSx7ImF1dGhvcmlzYXRpb25fZG9tYWluIjoiT3BlbiBCYW5raW5nIiwiYXV0aG9yaXNhdGlvbnMiOltdLCJyZWdpc3RyYXRpb25faWQiOiIxMzM1MzIzNi1PQkItREFET1MiLCJhdXRob3JpdHlfaWQiOiI2ODdhMWM5NC1iMzYwLTRlMDQtOTU4OS0wZmE1Y2IxNjQ1MWIiLCJhdXRob3Jpc2F0aW9uX3JvbGUiOiJEQURPUyIsImF1dGhvcml0eV9jb2RlIjoiQkNCIiwic3RhdHVzIjoiQWN0aXZlIn0seyJhdXRob3Jpc2F0aW9uX2RvbWFpbiI6Ik9wZW4gQmFua2luZyIsImF1dGhvcmlzYXRpb25zIjpbXSwicmVnaXN0cmF0aW9uX2lkIjoiMTMzNTMyMzYtT0JCLVBBR1RPIiwiYXV0aG9yaXR5X2lkIjoiNjg3YTFjOTQtYjM2MC00ZTA0LTk1ODktMGZhNWNiMTY0NTFiIiwiYXV0aG9yaXNhdGlvbl9yb2xlIjoiUEFHVE8iLCJhdXRob3JpdHlfY29kZSI6IkJDQiIsInN0YXR1cyI6IkFjdGl2ZSJ9XX0.W6hUAYhjT6I61rxEIVMKYKre93LTbRdzKnk9dJvUdzVgAz5B9KxZNutf27oO3k0hrjYVWBdWq23o_e4Y_AaKdpS9-rtU84JiHtmqV0wcFYIM8nqcUVWqQ-Ux6Nq9L2G-s2YNd3PcJ1e3yGg9h8553Gr7iJusKEgApzXUpkM2rBELQuumktUE_JBiuIkXmWxoRnO1cW-Osbk3MT3bxG43SPcxii07Q5S8qXI6PjCPA3fYlnaUAygwZM3O0oa7jqmSr7d9UsHuDMJfYhIKdq2wyQQKORCN-D2UopmMX-lHMvAVkkrAO08T0-7odjr4PJk-PrwuoCxeAfa7440ZDOrlmQ",<br>      "subject_type": "public",<br>      "token_endpoint_auth_method": "private_key_jwt",<br>      "request_object_signing_alg": "PS256",<br>      "require_signed_request_object": true,<br>      "require_pushed_authorization_requests": false,<br>      "tls_client_certificate_bound_access_tokens": true,<br>      "client_id": "aCnBHjZBvD6ku3KVBaslL",<br>      "client_name": "Raidiam Accounting",<br>      "client_uri": "https://www.raidiam.com/accounting.html",<br>      "request_object_encryption_alg": "RSA-OAEP",<br>      "request_object_encryption_enc": "A256GCM",<br>      "jwks_uri": "https://keystore.directory.openbankingbrasil.org.br/b961c4eb-509d-4edf-afeb-35642b38185d/25556d5a-b9dd-4e27-aa1a-cce732fe74de/application.jwks",<br>      "redirect_uris": [<br>        "https://www.raidiam.com/accounting/cb"<br>      ],<br>      "webhook_uris": [<br>        "https://www.myitp.com/mykong3"<br>      ]<br>    } |
| --- |

### 9.2. Open Finance Brasil SSA Key Store e detalhes do emissor

As links a seguir apontam para as chaves públicas do Diretório de Participantes, e devem ser usadas para verificar a validadade da assinatura dos *software\_statements* apresentados durante o processo de registro de cliente.

**Producão**

[https://keystore.directory.openbankingbrasil.org.br/openbanking.jwks](https://keystore.directory.openbankingbrasil.org.br/openbanking.jwks)

Emissor do Open Finance Open Finance Brasil SSA de produção

**Sandbox**

[https://keystore.sandbox.directory.openbankingbrasil.org.br/openbanking.jwks](https://keystore.sandbox.directory.openbankingbrasil.org.br/openbanking.jwks)

Emissor do Open Finance Open Finance Brasil SSA de sandbox

### 9.3. Sobre os mecanismos de autenticação e autorização dos serviços de DCR e DCM

Por serem serviços auxiliares ao fluxo principal do Open Finance Brasil, os serviços de registro e manutenção dinâmica de clientes não utilizam os mesmos mecanismos de controle de acesso. Por exemplo: não é possível exigir um *access\_token* OAuth 2.0 de uma aplicação cliente que ainda não está registrada na instituição transmissora. Para estender as [RFC7591](https://tools.ietf.org/html/rfc7591) e [RFC7592](https://tools.ietf.org/html/rfc7592), que recomendam mecanismos mínimos para autenticação dos seus serviços, as instituições que suportam os fluxos de registro e manutenção dinâmica de clientes devem implementar em seus Servidores de Autorização os controles a seguir:

#### 9.3.1. Registro de cliente - POST /register

1. validar que o certificado apresentado pela aplicação cliente é subordinado às cadeias do ICP-Brasil definidas no Padrão de Certificados do Open Finance Brasil;
2. enquanto houver a necessidade do período de convivência (mencionado no tópico 7.1) deve ser implementado a validação para ambos os casos: certificados que possuem o valor *org\_id* no campo *organizationUnitName* (*OU*) e certificados que possuem o valor *org\_id* no campo *organizationIdentifier*.
3. assegurar que a assinatura do *software\_statement* apresentado pela aplicação cliente durante o registro tenha sido feita pelo Diretório de Participantes através das chaves públicas descritas na seção anterior;
4. assegurar que o *software\_statement* apresentado pela aplicação cliente durante o registro corresponda à mesma instituição do certificado de cliente apresentado, validando-o através dos atributos que trazem `organization_id` no certificado X.509.
5. não devem ser permitidos múltiplos cadastros DCR para o mesmo Software Statement , de forma que em caso de tentativa de novo registro para um Software Statement já cadastrado, deve se utilizar o procedimento de Error Response definido no item 3.2.2 da RFC7591.
6. emitir, na resposta do registro, um `registration_access_token` para ser usado como token de autenticação nas operações de manutenção da aplicação cliente registrada, seguindo as especificações descritas na [RFC7592](https://tools.ietf.org/html/rfc7592).

#### 9.3.2. Manutenção de cliente - GET /register - PUT /register - DELETE /register

1. removido
2. validar a presença e a correspondência do header Bearer `Authorization` contendo o valor do atributo `registration_access_token` retornado durante o registro do cliente correspondente.
3. quando o método chamado for PUT /register, realizar as validações dos subitens 1, 3, 4 e 6 do item [Registro de cliente - POST /register](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/82215063/PT+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3).
4. quando o método chamado for GET /register, realizar as validações dos subitens 1 e 6 do item [Registro de cliente - POST /register](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/82215063/PT+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3).
5. quando o método chamado for DELETE /register, realizar a validação do subitem 1 do item [Registro de cliente - POST /register](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/82215063/PT+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3).

*Observação:* A [RFC7592](https://tools.ietf.org/html/rfc7592) prevê a possibilidade de rotação do `registration_access_token` emitido pelo Servidor de Autorização a cada uso, tornando-o um token de uso único. As instituições devem considerar esse aspecto no registro de suas aplicações cliente para receber e atualizar o `registration_access_token` pelo novo valor recebido nas chamadas de manutenção de cliente.

### 9.4. Validação de certificados de assinatura

- O diretório realiza a validação do certificado de assinatura através da função **cert rescan**, a cada hora.
- As instituições devem assegurar que o processo de validação é realizado.
- Cada instituição deve ter alternativa de contingência em caso de indisponibilidade do serviço de validação realizado pelo diretório.
- Ao identificar que o certificado de assinatura **não é válido **pois, está com status **revogado** de acordo com o OCSP/CRL da CA emissora, ou está **inativo** no cadastro do diretório, o conjunto de chaves públicas é movido para o repositório de chaves inativas (Inactive Keystore).
- É recomendado que o processo de validação inclua:

    - Validação da assinatura da mensagem do Transmissor de Dados, a ser feita pelo Receptor de Dados

        - Validar se a mensagem está assinada conforme o *Message Signature Guidelines*, incluindo se o *iss* é igual ao *organisation\_id *do servidor que emitiu a mensagem.
        - Buscar a declaração iss do JWT e gerar URI do JWKS publicado no diretório, para consulta.
        - Certificar se o *kid* do cabeçalho JWT da mensagem está presente no diretório JWKS.
        - Validar se a chave privada para o *kid* correspondente é capaz de validar a assinatura da mensagem.
    - Validação da assinatura da mensagem do Receptor de Dados, a ser feita pelo Transmissor de Dados

        - Validar se a mensagem está assinada conforme o *Message Signature Guidelines*.
        - Obter o *org\_jwks\_uri* que foi apresentado no SSA pelo cliente no momento do DCR.
        - Certificar se o *kid* do cabeçalho JWT da mensagem está presente no diretório JWKS.
        - Validar se a chave privada para o *kid* correspondente é capaz de validar a assinatura da mensagem.

## 10. Reconhecimento

Agradecemos a todos que estabeleceram as bases para o compartilhamento seguro de dados por meio da formação do Grupo de Trabalho OpenID Foundation FAPI, o GT de Segurança do Open Finance Brasil e aos pioneiros que ficarão em seus ombros.

As seguintes pessoas contribuíram para este documento:

- Alexandre Daniel Dalabrida (Cooperativa Central Ailos)
- Alexandre Siqueira (Mercado Pago)
- André Borges (Banco Fibra)
- Bernardo Vale (Banco Inter)
- Danilo Sasaki (Banco Itaú)
- João Rodolfo Vieira da Silva (Banco Itaú)
- Michelle Bandarra (Chicago)
- Nic Marcondes (Quanto)
- Rafael Gonzalez Hashimoto (Banco C6)
- Ralph Bragg (Raidiam)

## Appendix A. Avisos

Copyright (c) 2023 Estrutura Inicial do Open Finance Brasil

A Estrutura Inicial do Open Finance Brasil (EIOFB) concede a qualquer Colaborador, desenvolvedor, implementador ou outra parte interessada uma licença de direitos autorais mundial não exclusiva, livre de royalties para reproduzir, preparar trabalhos derivados, distribuir, executar e exibir, estes Implementadores Rascunho ou Especificação Final exclusivamente para fins de (i) desenvolver especificações e (ii) implementar Rascunhos de Implementadores e Especificações Finais com base em tais documentos, desde que a atribuição seja feita ao EIOFB como a fonte do material, mas que tal atribuição o faça não indica endosso do EIOFB.

A tecnologia descrita nesta especificação foi disponibilizada a partir de contribuições de várias fontes, incluindo membros da OpenID Foundation, do Grupo de Trabalho de Segurança do Open Finance Brasil e outros. Embora a Estrutura Inicial do Open Finance Brasil tenha tomado medidas para ajudar a garantir que a tecnologia esteja disponível para distribuição, ela não toma posição quanto à validade ou escopo de qualquer propriedade intelectual ou outros direitos que possam ser reivindicados como pertencentes à implementação ou uso do tecnologia descrita nesta especificação ou até que ponto qualquer licença sob tais direitos pode ou não estar disponível; nem representa que fez qualquer esforço independente para identificar tais direitos. A Estrutura Inicial do Open Finance Brasil e os contribuidores desta especificação não oferecem (e por meio deste expressamente se isentam de quaisquer) garantias (expressas, implícitas ou de outra forma), incluindo garantias implícitas de comercialização, não violação, adequação a uma finalidade específica ou título, relacionados a esta especificação, e todo o risco quanto à implementação desta especificação é assumido pelo implementador. A política de Direitos de Propriedade Intelectual do Open Finance Brasil exige que os contribuidores ofereçam uma promessa de patente de não fazer valer certas reivindicações de patentes contra outros contribuidores e implementadores. A Estrutura Inicial do Open Finance Brasil convida qualquer parte interessada a trazer à sua atenção quaisquer direitos autorais, patentes, pedidos de patentes ou outros direitos de propriedade que possam abranger a tecnologia que possa ser necessária para praticar esta especificação.

### A.1. Apêndice A. Exemplo de afirmação de declaração de software

| eyJraWQiOiJzaWduZXIiLCJ0eXAiOiJKV1QiLCJhbGciOiJQUzI1NiJ9.eyJzb2Z0d2FyZV9tb2RlIjoiTGl2ZSIsInNvZnR3YXJlX3JlZGlyZWN0X3VyaXMiOlsiaHR0cHM6XC9cL3d3dy5yYWlkaWFtLmNvbVwvYWNjb3VudGluZ1wvY2IiXSwic29mdHdhcmVfc3RhdGVtZW50X3JvbGVzIjpbeyJyb2xlIjoiREFET1MiLCJhdXRob3Jpc2F0aW9uX2RvbWFpbiI6Ik9wZW4gQmFua2luZyIsInN0YXR1cyI6IkFjdGl2ZSJ9LHsicm9sZSI6IlBBR1RPIiwiYXV0aG9yaXNhdGlvbl9kb21haW4iOiJPcGVuIEJhbmtpbmciLCJzdGF0dXMiOiJBY3RpdmUifV0sInNvZnR3YXJlX2NsaWVudF9uYW1lIjoiUmFpZGlhbSBBY2NvdW50aW5nIiwib3JnX3N0YXR1cyI6IkFjdGl2ZSIsInNvZnR3YXJlX2NsaWVudF9pZCI6IkNraTFFYnZqd3loUEIxMk5HTGx6MiIsImlzcyI6Ik9wZW4gQmFua2luZyBPcGVuIEJhbmtpbmcgQnJhc2lsIHByb2QgU1NBIGlzc3VlciIsInNvZnR3YXJlX3Rvc191cmkiOiJodHRwczpcL1wvd3d3LnJhaWRpYW0uY29tXC9hY2NvdW50aW5nXC90b3MuaHRtbCIsInNvZnR3YXJlX2NsaWVudF9kZXNjcmlwdGlvbiI6IlJhaWRpYW0gQWNjb3VudGluZyBsZXZlcmFnZSBjdXR0aW5nIGVkZ2Ugb3BlbiBiYW5raW5nIGFjY2VzcyB0byBicmluZyB5b3UgcmVhbCB0aW1lIHVwIHRvIGRhdGUgdmlld3Mgb2YgeW91ciBmaW5hbmNlcyIsInNvZnR3YXJlX2p3a3NfZW5kcG9pbnQiOiJodHRwczpcL1wva2V5c3RvcmUuZGlyZWN0b3J5Lm9wZW5iYW5raW5nYnJhc2lsLm9yZy5iclwvYjk2MWM0ZWItNTA5ZC00ZWRmLWFmZWItMzU2NDJiMzgxODVkXC8yNTU1NmQ1YS1iOWRkLTRlMjctYWExYS1jY2U3MzJmZTc0ZGVcL2FwcGxpY2F0aW9uLmp3a3MiLCJzb2Z0d2FyZV9wb2xpY3lfdXJpIjoiaHR0cHM6XC9cL3d3dy5yYWlkaWFtLmNvbVwvYWNjb3VudGluZ1wvcG9saWN5Lmh0bWwiLCJzb2Z0d2FyZV9pZCI6IjI1NTU2ZDVhLWI5ZGQtNGUyNy1hYTFhLWNjZTczMmZlNzRkZSIsInNvZnR3YXJlX2NsaWVudF91cmkiOiJodHRwczpcL1wvd3d3LnJhaWRpYW0uY29tXC9hY2NvdW50aW5nLmh0bWwiLCJzb2Z0d2FyZV9qd2tzX2luYWN0aXZlX2VuZHBvaW50IjoiaHR0cHM6XC9cL2tleXN0b3JlLmRpcmVjdG9yeS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnJcL2I5NjFjNGViLTUwOWQtNGVkZi1hZmViLTM1NjQyYjM4MTg1ZFwvMjU1NTZkNWEtYjlkZC00ZTI3LWFhMWEtY2NlNzMyZmU3NGRlXC9pbmFjdGl2ZVwvYXBwbGljYXRpb24uandrcyIsInNvZnR3YXJlX2p3a3NfdHJhbnNwb3J0X2luYWN0aXZlX2VuZHBvaW50IjoiaHR0cHM6XC9cL2tleXN0b3JlLmRpcmVjdG9yeS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnJcL2I5NjFjNGViLTUwOWQtNGVkZi1hZmViLTM1NjQyYjM4MTg1ZFwvMjU1NTZkNWEtYjlkZC00ZTI3LWFhMWEtY2NlNzMyZmU3NGRlXC9pbmFjdGl2ZVwvdHJhbnNwb3J0Lmp3a3MiLCJzb2Z0d2FyZV9qd2tzX3RyYW5zcG9ydF9lbmRwb2ludCI6Imh0dHBzOlwvXC9rZXlzdG9yZS5kaXJlY3Rvcnkub3BlbmJhbmtpbmdicmFzaWwub3JnLmJyXC9iOTYxYzRlYi01MDlkLTRlZGYtYWZlYi0zNTY0MmIzODE4NWRcLzI1NTU2ZDVhLWI5ZGQtNGUyNy1hYTFhLWNjZTczMmZlNzRkZVwvdHJhbnNwb3J0Lmp3a3MiLCJzb2Z0d2FyZV9sb2dvX3VyaSI6Imh0dHBzOlwvXC93d3cucmFpZGlhbS5jb21cL2FjY291bnRpbmdcL2xvZ28ucG5nIiwib3JnX2lkIjoiYjk2MWM0ZWItNTA5ZC00ZWRmLWFmZWItMzU2NDJiMzgxODVkIiwic29mdHdhcmVfZW52aXJvbm1lbnQiOiJwcm9kdWN0aW9uIiwic29mdHdhcmVfdmVyc2lvbiI6MS4xMCwic29mdHdhcmVfcm9sZXMiOlsiREFET1MiLCJQQUdUTyJdLCJvcmdfbmFtZSI6Ik9wZW4gQmFua2luZyBCcmFzaWwiLCJpYXQiOjE2MTgzMzYyNjIsIm9yZ2FuaXNhdGlvbl9jb21wZXRlbnRfYXV0aG9yaXR5X2NsYWltcyI6W3siYXV0aG9yaXNhdGlvbl9kb21haW4iOiJPcGVuIEJhbmtpbmciLCJhdXRob3Jpc2F0aW9ucyI6W10sInJlZ2lzdHJhdGlvbl9pZCI6IjEzMzUzMjM2LU9CQi1DT05UQSIsImF1dGhvcml0eV9pZCI6IjY4N2ExYzk0LWIzNjAtNGUwNC05NTg5LTBmYTVjYjE2NDUxYiIsImF1dGhvcmlzYXRpb25fcm9sZSI6IkNPTlRBIiwiYXV0aG9yaXR5X2NvZGUiOiJCQ0IiLCJzdGF0dXMiOiJBY3RpdmUifSx7ImF1dGhvcmlzYXRpb25fZG9tYWluIjoiT3BlbiBCYW5raW5nIiwiYXV0aG9yaXNhdGlvbnMiOltdLCJyZWdpc3RyYXRpb25faWQiOiIxMzM1MzIzNi1PQkItREFET1MiLCJhdXRob3JpdHlfaWQiOiI2ODdhMWM5NC1iMzYwLTRlMDQtOTU4OS0wZmE1Y2IxNjQ1MWIiLCJhdXRob3Jpc2F0aW9uX3JvbGUiOiJEQURPUyIsImF1dGhvcml0eV9jb2RlIjoiQkNCIiwic3RhdHVzIjoiQWN0aXZlIn0seyJhdXRob3Jpc2F0aW9uX2RvbWFpbiI6Ik9wZW4gQmFua2luZyIsImF1dGhvcmlzYXRpb25zIjpbXSwicmVnaXN0cmF0aW9uX2lkIjoiMTMzNTMyMzYtT0JCLVBBR1RPIiwiYXV0aG9yaXR5X2lkIjoiNjg3YTFjOTQtYjM2MC00ZTA0LTk1ODktMGZhNWNiMTY0NTFiIiwiYXV0aG9yaXNhdGlvbl9yb2xlIjoiUEFHVE8iLCJhdXRob3JpdHlfY29kZSI6IkJDQiIsInN0YXR1cyI6IkFjdGl2ZSJ9XX0.W6hUAYhjT6I61rxEIVMKYKre93LTbRdzKnk9dJvUdzVgAz5B9KxZNutf27oO3k0hrjYVWBdWq23o_e4Y_AaKdpS9-rtU84JiHtmqV0wcFYIM8nqcUVWqQ-Ux6Nq9L2G-s2YNd3PcJ1e3yGg9h8553Gr7iJusKEgApzXUpkM2rBELQuumktUE_JBiuIkXmWxoRnO1cW-Osbk3MT3bxG43SPcxii07Q5S8qXI6PjCPA3fYlnaUAygwZM3O0oa7jqmSr7d9UsHuDMJfYhIKdq2wyQQKORCN-D2UopmMX-lHMvAVkkrAO08T0-7odjr4PJk-PrwuoCxeAfa7440ZDOrlmQ |
| --- |

## Author's Address

**OFBIS GT Security**

Open Finance Brasil Initial Structure

Email: [gt-seguranca@openfinancebrasil.org.br](mailto:gt-seguranca@openfinancebrasil.org.br)

URI: [https://openfinancebrasil.org.br](https://openfinancebrasil.org.br/)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/240649543)
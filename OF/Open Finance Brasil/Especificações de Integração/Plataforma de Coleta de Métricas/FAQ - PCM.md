[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/45711395)

#### O que significa a sigla P.C.M.?

PCM significa Plataforma de Coleta de Métricas. [Saiba mais](../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20Integra%c3%a7%c3%a3o/Plataforma%20de%20Coleta%20de%20M%c3%a9tricas/Especifica%c3%a7%c3%a3o%20T%c3%a9cnica/index).

#### Onde podemos acessar a documentação da PCM?

A documentação está publicada na Área do Desenvolvedor dentro do portal Open Finance Brasil. Link direto: [Plataforma de Coleta de Métricas](../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20Integra%c3%a7%c3%a3o/Plataforma%20de%20Coleta%20de%20M%c3%a9tricas/index) 

#### Qual é o SLA para envio de reportes à PCM?

Está em definição pelo GT Arquitetura. Podemos adiantar que é esperado que os dados tenham sido enviados durante o dia e conciliados entre os participantes até a manhã seguinte. Esta definição será publicada em um Open Finance Informa muito em breve.

#### Preciso enviar dados da versão 1 da Fase 2?

Não. Esta versão está sendo depreciada.

#### Precisarei enviar dados referentes a futuras APIs em estado deprecated?

Sim. A única exceção é a versão 1.x.x da Fase 2.

#### Como faço para referenciar as marcas acionadas?

Atualmente os dados enviados à PCM não são diferenciados por marcas, estão à nível da organização (organization-org-id).

#### Havia um problema em minha integração e eu enviei um dado errado. Consigo corrigir?

Está previsto um método PUT para que o participante corrija algum dado de sua responsabilidade, entretanto o processo administrado de resolução de divergências será definido futuramente, após aprendizados baseados nos eventos observados no MVP.

#### Qual é o escopo de endpoints que a PCM vai receber?

São todas as APIs hoje disponíveis no Open Finance Brasil. Elas são separadas em duas categorias:

**Private APIs:** que são as que possuem Dados de Cliente (fase 2), Serviços (fase 3) e Segurança (FAPI/OAUTH).

**OpenData APIs**: que são as APIs não autenticadas, que respondem por Dados Abertos (fase 1).

Você encontra na especificação técnica da PCM uma lista detalhada com todos os endpoints e que quais papéis necessitam realizar envio quais tipos de telemetria. Saiba mais

#### Temos a necessidade de teste funcional ou certificação específica dos participantes para a PCM?

Não há pré-certificação. Está previsto para que a FVP (Ferramenta de Validação em Produção) envie telemetria à PCM sobre todas as requisições feitas, e, desta forma, será possível ter métricas relativas à conformidade da integração feita pelo participante em ambiente produtivo.

#### Podemos enviar dados de sandbox para a PCM?

Até 1/2/2023 será permitido o envio de dados não produtivos. Nós recomendamos que sejam enviados dados produtivos, a fim de se colaborar para testarmos a capacidade de pareamento real da plataforma.

#### Quais são os padrões de certificado de segurança que precisam ser adotados para se integrar à PCM?

A PCM utiliza o padrão de tokens OAuth2, na modalidade client\_credentials. Deve-se utilizar, para tal, um certificado de transporte (mTLS) padrão Open Finance Brasil (BRCAC) atrelado a sua organização. Para detalhes, consulte a documentação técnica da PCM.

#### Minha instituição não possui BRCAC. Como faço para me integrar à PCM?

Você poderá utilizar o certificado emitido pelo Diretório de sandbox. Para sua plena operação e 1/2/23, uma alternativa está em definição pelo GT Arquitetura.

#### Qual é o prazo para se integrar à PCM?

Prazo estabelecido, conforme Open Finance Informa #282, para 1/Fev/2023.

#### Qual é o processo para correção de eventos com divergência de reportes com status PAIRED\_INCONSISTENT ou UNPAIRED?

A PCM possui um métodos do tipo PUT, que deverão ser utilizados para a realização de reenvio de pontos de telemetria problemáticos e, desta forma, se aplique a correções. Neste momento, porém, não há definição de regras definidas sobre quais os casos em que o uso do PUT será permitido, pois o GT Arquitetura optou por elaborar tais regras baseado em estudo de casos reais, com dados reais, que ocorrerem em produção pós lançamento da plataforma.

#### Como é contabilizada a paginação?

Atualmente não é feita contabilização de paginações pela PCM. Será feito um estudo para adição do pagination-key como campo no additionalInfo.

#### Estou com uma dúvida que não está explicada nem na documentação neste FAQ. Como faço para fazer perguntas para especialistas em PCM?

Utilize o Service Desk. Uma nova categoria para centralizar as questões será disponibilizada nos próximos dias.

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/45711395)
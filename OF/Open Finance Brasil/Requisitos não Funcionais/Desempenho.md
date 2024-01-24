[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17891396)

Deverá ser medido o tempo de resposta de cada requisição, ou seja, o tempo transcorrido entre o recebimento de uma requisição que não ultrapassa os limites de tráfego e o momento em que a requisição é completamente respondida.

Adicionalmente, esta medição deverá ser feita de maneira que os tempos medidos sejam os mais próximos possíveis dos tempos de resposta experimentados por quem fez a requisição. Neste contexto, os *endpoints *das APIs deverão manter o percentil 95 do tempo de resposta em no máximo:

I. 1.500ms, em endpoints classificados como de alta frequência.

II. 2.000ms, em endpoints classificados como de média-alta frequência.

III. 2.000ms, em endpoints classificados como de média frequência.

IV. 4.000ms, em endpoints classificados como de baixa frequência.

Por exemplo, em um dia que um *endpoint *de alta frequência receba 10.000 requisições, o tempo de resposta de pelo menos 9.500 requisições deve ser inferior a 1.500ms.

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17891396)
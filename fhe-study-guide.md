---
description: >-
  Um pequeno guia para quem está interessado em aprender mais sobre a
  criptografia completamente homomórfica, mas não sabe por onde começar.
---

# FHE Study guide

Recentemente, a fhe.org publicou uma nova página, contendo o timeline da trajetória da criptografia completamente homomórfica. Com isto, decidi escrever aqui acerca desta timeline e, sugerir materiais de estudo para que você possa ter um norte de onde começar a estudar esta incrível inovação.

> Todo o conteúdo da timeline foi extraído e adptado diretamente do website da fhe.org: [https://fhe.org/history/](https://fhe.org/history/)

## Privacy Homomorphisms

A criptografia completamente homomórfica surgiu na área da criptografia há cerca de 14 anos, inicialmente sob o conceito de "homomorfismos privados\*" (_privacy homomorphisms_ em inglês). A ideia consistia em uma função que atuava homomorficamente, ou seja, preservava operações específicas como adição e multiplicação. Isso permitia a execução de operações em dados criptografados, resultando em efeitos correspondentes nos dados originais não criptografados.

> * Este artigo se refere ao escrito por Rivest, Adleman, Dertouzos: On data banks and privacy homomorphisms (Disponível em: [https://luca-giuzzi.unibs.it/corsi/Support/papers-cryptography/RAD78.pdf](https://luca-giuzzi.unibs.it/corsi/Support/papers-cryptography/RAD78.pdf)).

## Esquema RSA

O sistema criptográfico RSA, criado em 1977 por Rivest, Shamir e Adleman, foi um algoritmo fundamental que estabeleceu conceitos importantes para a criptografia homomórfica. Foi o primeiro exemplo de um esquema de criptografia parcialmente homomórfica, permitindo que a multiplicação de dois _ciphertexts_ resultasse em uma forma criptografada do produto de seus respectivos _plaintexts_.

> O artigo original pode ser encontrado em: [https://dl.acm.org/doi/10.1145/359340.359342](https://dl.acm.org/doi/10.1145/359340.359342)

## Criptografia Parcialmente Homomórfica

Ao longo das três décadas seguintes, houve avanços significativos, com pesquisadores concentrados em criar esquemas criptográficos que suportassem operações homomórficas, principalmente adição e multiplicação, cada uma limitada por restrições específicas. No entanto, nenhum desses esquemas conseguia suportar ambas as operações simultaneamente.

O maior objetivo da comunidade criptográfica era desenvolver um esquema capaz de suportar, homomorficamente, tanto a adição quanto a multiplicação. Contudo, essa aspiração parecia inatingível, levando muitos especialistas a duvidarem da viabilidade de uma verdadeira criptografia homomórfica.

## Craig Gentry

Em 2009, um avanço significativo ocorreu quando Craig Gentry publicou o primeiro exemplo de um esquema criptográfico seguro que suportava tanto a adição quanto a multiplicação de forma homomórfica. Esse desenvolvimento foi inesperado e revolucionário, reacendendo o interesse no campo e abrindo novas possibilidades para pesquisas em criptografia completamente homomórfica (FHE). A contribuição de Gentry marcou um ponto de virada crucial na evolução da FHE, transformando-a de um conceito puramente teórico em uma tecnologia aplicável no mundo real.

> O artigo de Gentry pode ser acessado em: [https://crypto.stanford.edu/craig/craig-thesis.pdf](https://crypto.stanford.edu/craig/craig-thesis.pdf)

## DGHV

Logo após, Marten van Dijk, Craig Gentry, Shai Halevi e Vinod Vaikuntanathan desenvolveram o esquema DGHV ("Criptografia completamente homomórfica sobre números inteiros"), que utilizava apenas adição e multiplicação sobre números inteiros, em contraste com as estruturas algébricas mais complexas empregadas no esquema de Gentry baseado em lattices ideais. Conceitualmente, o DGHV é muito simples e baseia-se no problema do GCD aproximado, uma suposição de dificuldade distinta do LWE. Este esquema serve como uma demonstração de que a criptografia homomórfica completamente homomórfica (FHE) pode ser construída de maneira mais acessível e compreensível.

## BGV

O esquema BGV foi introduzido em 2011 por Zvika Brakerski, Craig gentry e Vinod Vaikuntanathan, baseado na dificuldade do problema de aprendizado com erros sobre anéis (RLWE). O que o diferenciava era seu gerenciamento de erro, ou ruído, que, assim como no esquema BFV, aumenta à medida que as operações criptográficas são realizadas. No entanto, o BGV foi projetado especificamente para controlar esse crescimento, especialmente após operações de multiplicação homomórfica, garantindo tanto a segurança quanto a praticidade do esquema.

> O artigo pode ser encontrado em: [https://eprint.iacr.org/2011/277](https://eprint.iacr.org/2011/277)

## BFV

O esquema BFV foi apresentado em 2012 por meio de dois trabalhos distintos: um por Brakerski e outro por Fan e Vercauteren. Brakerski introduziu um esquema baseado em LWE, enquanto Fan e Vercauteren utilizaram esse esquema como base para construir uma versão aprimorada baseada em ring-LWE. Um aspecto interessante do esquema BFV é sua característica de tamanho invariante. Diferentemente do BGV, no BFV os bits da mensagem são codificados nos _higher-order bits_ do _plaintext_.

> O artigo referente ao esquema pode ser encontrado em: [https://eprint.iacr.org/2012/144](https://eprint.iacr.org/2012/144)

## FHEW

Um esquema de FHE booleano que opera a partir da avaliação de portas booleanas em bits encriptados. Em particular, a partir de operações em que são admitidas a computação de portas NAND homomorficamente em dois bits de criptografia de _ciphertexts._ Essa foi a primeira aparição de bootstrapping em menos de 1 segundo.

> O artigo referente ao esquema pode ser encontrado em: [https://github.com/lducas/FHEW](https://github.com/lducas/FHEW)

## CKKS

O esquema CKKS foi primeiramente introduzido em 2016 por Cheon, Kim, Kim, e Song. Esse esquema foi o primeiro esquema de FHE que performava sobre números aritméticos aproximados sobre números complexos e reais. Foi utilizada uma nova técnica de encoding para mapear um vetor de valores complexos em um anél polinomial. Um novo método de reescalonamento foi introduzido, permitindo _ciphertexts_ mais compactos sobre uma avaliação homomórifca.

> O artigo referente ao esquema pode ser encontrado em: [https://link.springer.com/chapter/10.1007/978-3-319-70694-8\_15](https://link.springer.com/chapter/10.1007/978-3-319-70694-8\_15)

## TFHE

Pouco tempo depois um esquema parecido com o FHEW foi desenvolvido por Ilaria Chillotti, Nicolas Gama, Mariya Georgieva, e Malika Izabachènem, que consideram uma seleção de de melhorias para que seja possível aumentar a eficiência, comparado com o uso de um "produto interno" no FHEW. Aqui, o processo de _boostrapping_ é considerado como um "produto externo" do qual aumenta a eficiência. Outras técnicas descrevem como reduzir o tamanho da chave de _bootstrapping_ de \~1 GB para dezenas de MB. Foi a primeira instância registrada de bootstrapping em menos de 100 ms.

> O artigo referente ao esquema pode ser encontrado em: [https://tfhe.github.io/tfhe/](https://tfhe.github.io/tfhe/)
>
> Fun fact: O esquema de TFHE já está sendo utilizado de maneira comercial pela empresa ZAMA ([https://www.zama.ai/](https://www.zama.ai/)) da qual oferece soluções de criptografia completamente homomórfica para empresas.

Seguindo esta linha do tempo podemos ter uma direção mais direcionada de como estudar a FHE propriamente dita. Como dito na página anterior, você também precisa entender conceitos como algebra abstrata. Um bom recurso para estudar sobre este assunto pode ser encontrado no canal [Socratica](https://www.youtube.com/@Socratica) no Youtube. Playlist sobre algebra abstrata: [https://youtube.com/playlist?list=PLi01XoE8jYoi3SgnnGorR\_XOW3IcK-TP6\&si=6Eh\_-\_4QGTwBDGFW](https://youtube.com/playlist?list=PLi01XoE8jYoi3SgnnGorR\_XOW3IcK-TP6\&si=6Eh\_-\_4QGTwBDGFW)

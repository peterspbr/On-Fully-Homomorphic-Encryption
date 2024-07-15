# Introdução à Criptografia totalmente homomórfica (FHE)

Nos dias de hoje, a privacidade digital emergiu como uma preocupação significativa. A enorme quantidade de dados gerados diariamente acarreta uma responsabilidade proporcionalmente maior de assegurar a segurança dessas informações. Nesse contexto, a criptografia se destaca como a forma mais eficaz de proteger os dados.

A privacidade digital envolve a proteção das informações pessoais e sensíveis contra acessos não autorizados, garantindo que apenas indivíduos autorizados possam acessar e manipular esses dados. Com o crescente uso de tecnologias digitais em todas as esferas da vida cotidiana, a quantidade de dados gerados e armazenados em servidores e dispositivos pessoais aumentou exponencialmente. Este cenário torna a proteção desses dados um desafio crítico.

A criptografia oferece uma solução robusta para esse desafio. Trata-se de um processo que transforma dados legíveis em um formato codificado, que só pode ser decifrado por aqueles que possuem a chave de criptografia adequada. Este mecanismo assegura que, mesmo que os dados sejam interceptados, eles permanecerão inacessíveis e inúteis para qualquer pessoa sem a chave correta.

Portanto, a implementação de criptografia é essencial para qualquer estratégia de segurança digital. Ao proteger as informações através de métodos criptográficos, é possível garantir que os dados sensíveis permaneçam confidenciais e seguros, mesmo em um ambiente digital cada vez mais ameaçador.

Os sistemas criptográficos atuais apresentam limitações significativas na preservação da confidencialidade dos dados, pois é necessário descriptografá-los para realizar qualquer operação. Esse processo expõe os dados a possíveis vulnerabilidades durante o período em que permanecem em texto claro (_plaintext_). No entanto, a criptografia totalmente homomórfica (Fully Homomorphic Encryption, FHE), proposta por Craig Gentry em 2009, oferece uma solução inovadora para esse problema.

A FHE permite que operações sejam realizadas diretamente em dados criptografados sem a necessidade de primeiro convertê-los para _plaintext_. Essa abordagem revolucionária mantém a confidencialidade dos dados durante todo o processo de computação. Quando um servidor recebe dados criptografados, ele pode realizar cálculos sobre esses dados sem jamais descriptografá-los. Após a computação, os dados permanecem criptografados e são retornados ao proprietário original.

Somente o proprietário dos dados, que possui a chave secreta, pode descriptografar os resultados e revelar o _plaintext_. Essa capacidade de computação segura tem implicações significativas para a privacidade e segurança digital, especialmente em ambientes onde a confidencialidade dos dados é crítica.

É importante notar que Craig Gentry não foi o primeiro a trazer o conceito de homomorfismo à criptografia. Essa noção, originalmente chamada de homomorfismo de privacidade, foi introduzida por Rivest, Adleman e Dertouzous logo após a invenção do RSA por Rivest, Shamir e Adleman. A FHE é um desenvolvimento contínuo desse conceito, proporcionando um nível de segurança sem precedentes nas operações computacionais.

Para mais detalhes, o artigo original de Craig Gentry pode ser acessado [aqui](https://crypto.stanford.edu/craig/craig-thesis.pdf).

### **Aplicações Reais da Criptografia Totalmente Homomórfica (FHE)**

A criptografia totalmente homomórfica (FHE) oferece uma solução promissora para diversos desafios de segurança e privacidade em várias áreas. Algumas das aplicações reais do FHE incluem:

1. **Leis e Compliance**: Países como o Brasil e nações da Europa precisam seguir rigorosas leis de privacidade de dados, como a Lei Geral de Proteção de Dados (LGPD) no Brasil e o Regulamento Geral sobre a Proteção de Dados (GDPR) na Europa. A FHE pode ajudar a garantir a conformidade com essas regulamentações, uma vez que somente o proprietário dos dados terá acesso a eles. Isso assegura que os dados pessoais e sensíveis permaneçam protegidos durante todo o processo de processamento e armazenamento.
2. **Sistemas de Voto**: A FHE pode ser utilizada para evitar modificações não autorizadas de votos, garantindo assim a integridade e a democracia nos processos eleitorais. Ao permitir que os votos sejam processados de forma criptografada, a FHE impede que os resultados de uma eleição sejam adulterados, proporcionando um nível adicional de segurança e confiança no sistema eleitoral.
3. **Processamento por IA**: A FHE permite que os dados processados por sistemas de inteligência artificial (IA) sejam mantidos seguros. Isso significa que os dados sensíveis podem ser utilizados para treinar e operar modelos de IA sem que sejam expostos ao servidor de IA. Essa capacidade é particularmente importante em setores como saúde, finanças e defesa, onde a proteção de dados sensíveis é crucial.

Essas aplicações destacam o potencial da FHE em transformar a forma como dados sensíveis são manipulados e protegidos, oferecendo soluções robustas para desafios contemporâneos de segurança e privacidade.

Antes de nos aprofundarmos em mais detalhes sobre a criptografia totalmente homomórfica (FHE), é essencial compreender alguns conceitos fundamentais:

1. **Circuitos na Criptografia**:
   * Em criptografia, os circuitos referem-se a operações booleanas, como adição e multiplicação. Essas operações são a base para realizar cálculos sobre dados criptografados. Os circuitos booleanos são compostos de portas lógicas que processam bits, permitindo a execução de operações matemáticas necessárias para computações criptográficas.
2. **Par de Chaves**:
   * O conceito de par de chaves é fundamental na criptografia de chave pública (Public-key encryption), ou também conhecido como criptografia assíncrona. Um par de chaves consiste em duas chaves: uma chave pública e uma chave privada. A chave pública é usada para criptografar dados, enquanto a chave privada é utilizada para descriptografar esses dados. Essa abordagem garante que apenas o proprietário da chave privada possa acessar os dados criptografados.
3. **Computação em Dados Criptografados**:
   * Quando um servidor precisa realizar computações em dados criptografados, ele utiliza um processo chamado Avaliação (Evaluation). A Avaliação permite que o servidor execute operações sobre dados criptografados sem a necessidade de descriptografá-los primeiro. Isso é possível graças às propriedades matemáticas da FHE, que preservam a estrutura dos dados durante as operações, mantendo-os protegidos.

Esses pontos formam a base para entender como a FHE funciona e como ela pode ser aplicada em diversas áreas para proteger a privacidade e a segurança dos dados.

Nas próximas páginas, iremos nos aprofundar mais nos conceitos matemáticos, bibliotecas e programação (em C++), e mais para frente construir uma aplicação utilizando a biblioteca [OpenFHE](https://github.com/openfheorg/openfhe-development) utilizando o esquema BFV, BGV e logo após utilizando CKKS.

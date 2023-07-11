# Atividade Cap. 06 - Operação de Cifra de Bloco
_______________________________

1. **O que é encriptação tripla?**

É um padrão de criptografia baseado em outro algoritmo de criptografia simétrica, o DES, desenvolvido pela IBM em 1974 e adotado como padrão em 1977. O **3DES** usa 3 chaves de 64 bits,embora apenas 56 bits de cada chave são efetivamente usados, os outros 8 bits são usados para verificar paridade. Sendo assim, o tamanho máximo efetivo da chave é de 168 bits. Os dados são encriptados com a primeira chave, decriptados com a segunda chave e finalmente encriptados novamente com uma terceira chave. Isto faz o 3DES ser mais lento que o DES original, porém em contrapartida oferece maior segurança.

Em vez de 3 chaves podem ser utilizadas apenas 2, sendo a terceira igual a primeira, tendo assim uma chave de 112 bits efetivos.
A variante mais simples do 3DES opera da seguinte forma: **E(k3; D(k2; E(k1; M)))** onde _M_ é o bloco de mensagem a ser criptografado e _k1_, _k2_ e _k3_ são chaves DES.

2. **O que é ataque meet-in-the-middle?**


O ataque meet-in-the-middle(encontro no meio) é um tipo de ataque criptográfico que visa quebrar uma criptografia de chave dupla ou tripla, explorando a complexidade computacional para reduzir a busca de chaves possíveis.
É um ataque particularmente eficiente contra criptografias que usam duas etapas de encriptação em sequência, como o 2DES ou o 3DES. O princípio básico desse ataque é encontrar um ponto intermediário na sequência de encriptação e descriptação, onde a busca de chaves se torna viável.

3. **Quantas chaves são usadas na encriptação tripla?**

São utilizadas três chaves separadas para criptografar os dados. Cada chave é aplicada em uma etapa distinta do processo de encriptação.

O 3DES é uma evolução do algoritmo DES (Data Encryption Standard), que usa uma única chave de 56 bits. No entanto, para aumentar a segurança, o 3DES aplica o algoritmo DES três vezes consecutivamente para cada bloco de dados. Portanto, são necessárias três chaves distintas, cada uma com 56 bits de tamanho, totalizando 168 bits no total.

4. **Por que a parte do meio do 3DES é decriptação, em vez de encriptação?**

O DES é um algoritmo de criptografia de bloco que opera em blocos de 64 bits. No entanto, devido ao aumento da capacidade de processamento dos computadores e avanços na criptoanálise, o DES foi considerado inseguro para aplicações sensíveis. Como uma solução intermediária, surgiu o 3DES, que utiliza o DES três vezes para fornecer um nível mais alto de segurança.

No 3DES, a sequência de encriptação-decriptação-encriptação é usada para garantir compatibilidade com sistemas que usam o DES original. Isso permite que o 3DES seja usado como uma substituição direta para o DES em sistemas legados sem a necessidade de modificar a lógica de encriptação existente.


5. Por que alguns modos de operação de cifra de bloco só utilizam a encriptação, enquanto outros
empregam encriptação e decriptação?


6. Você deseja construir um dispositivo de hardware para realizar encriptação de bloco no modo
cipher block chaining (CBC) usando um algoritmo mais forte do que DES. 3DES é um bom
candidato. A Figura 1 mostra duas possibilidades, ambas acompanhando a definição do CBC.
Qual das duas você escolheria:
(a) Por segurança?
(b) Por desempenho?

7. Crie um software que possa encriptar e decriptar no modo cipher block chaining usando uma
das seguintes cifras: módulo affine 256, módulo Hill 256, S-DES, DES.
Teste os dados para S-DES usando um vetor de inicialização binário de 1010 1010. Um texto
claro binário de 0000 0001 0010 0011 encriptado com uma chave binária de 01111 11101
deverá dar um texto claro binário de 1111 0100 0000 1011. A decriptação deverá funcionar
de modo correspondente.
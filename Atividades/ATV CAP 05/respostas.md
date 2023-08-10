# Atividade Cap. 05 - Advanced Encryption Standard
_______________________________

1. **Qual foi o conjunto original de critérios usados pelo NIST para avaliar as cifras AES candidatas?**

O NIST estabeleceu um conjunto de critérios para avaliar as cifras candidatas ao AES. Esses critérios incluíam **segurança, eficiência, implementação, análise criptográfica, transparência e revisão**. O objetivo era selecionar uma cifra forte, segura e adequada para uso em diversas aplicações. O AES foi escolhido como o padrão de criptografia simétrica após um processo rigoroso de avaliação das cifras candidatas.

2. **Qual foi o conjunto final de critérios usados pelo NIST para avaliar as cifras AES candidatas?**

O conjunto final de critérios usado pelo NIST para avaliar as cifras candidatas ao AES incluiu **segurança, eficiência, implementação, análise criptográfica, transparência, revisão e preferência por cifras amplamente adotadas**. O objetivo era selecionar uma cifra segura, eficiente e confiável para se tornar o padrão de criptografia simétrica.

3. **Qual é a diferença entre Rijndael e AES?**

Rijndael é uma família de algoritmos flexíveis de criptografia simétrica incluindo 128 bits, 192 bits e 256 bits, enquanto o AES é a versão específica do Rijndael onde o tamanho fixo da chave e do bloco é de 128 bits, selecionada e padronizada pelo NIST como o padrão de criptografia simétrica amplamente utilizado.

4. **Responda:**

**(a)** Qual é a finalidade do array Estado?

O array Estado(State array) é uma estrutura de dados usada no algoritmo AES. Ele armazena o estado intermediário dos dados durante as etapas de criptografia e descriptografia. O array Estado é uma matriz 4x4 de bytes e permite a aplicação das operações do AES de forma eficiente e correta. É fundamental para o funcionamento do algoritmo AES.

**(b)** Como é construída a S-box?

A S-box (Substitution box) é uma tabela usada no AES para substituir bytes durante a criptografia. Ela é construída aplicando uma substituição não linear e permutação aos valores iniciais da tabela. A construção da S-box envolve operações matemáticas, como inverso multiplicativo e álgebra modular. A S-box desempenha um papel importante na segurança e difusão do AES, fornecendo não linearidade e resistência a ataques criptográficos.

**(c)** Descreva rapidamente o estágio SubBytes, ShiftRows, MixColumns, AddRoundKey, e o
algoritmo de expansão de chave.

SubBytes: Nesta etapa, cada byte do array Estado é substituído por um valor correspondente na S-box. A S-box é uma tabela de substituição não linear que fornece não linearidade à cifra.

ShiftRows: Nesta etapa, as linhas do array Estado são deslocadas circularmente. A primeira linha permanece inalterada, a segunda linha é deslocada uma posição para a esquerda, a terceira linha é deslocada duas posições para a esquerda, e a quarta linha é deslocada três posições para a esquerda. Isso garante a difusão dos bytes dentro do array.

MixColumns: Nesta etapa, cada coluna do array Estado é multiplicada por uma matriz fixa usando uma operação de multiplicação de matriz sobre GF(2^8). Essa etapa proporciona difusão e confusão nos bytes do array Estado.

AddRoundKey: Nesta etapa, cada byte do array Estado é combinado bit a bit com a chave de rodada correspondente usando a operação de XOR. A chave de rodada é derivada da chave mestra do AES usando o algoritmo de expansão de chave.

Algoritmo de expansão de chave: Este algoritmo expande a chave mestra do AES em um conjunto de chaves de rodada, uma para cada rodada do processo de criptografia. Ele usa operações como substituição de bytes, rotação de palavra e operação XOR para gerar as chaves de rodada necessárias.

5. **Quantos bytes em Estado são afetados por ShiftRows?**

Na etapa ShiftRows do AES, 12 bytes no array Estado são afetados. A operação de deslocamento circular é aplicada às linhas do array Estado da seguinte maneira:

A primeira linha não sofre nenhum deslocamento.
A segunda linha é deslocada uma posição para a esquerda.
A terceira linha é deslocada duas posições para a esquerda.
A quarta linha é deslocada três posições para a esquerda.

Esses deslocamentos circulares afetam todos os bytes no array Estado, garantindo a difusão dos bytes e contribuindo para a segurança e a resistência do AES a ataques criptográficos.

6. Use a chave 1010 0111 0011 1011 para encriptar o texto claro "ok"conforme expresso em
ASCII, ou seja, 0110 1111 0110 1011. Os projetistas do S-AES obtiveram o texto cifrado
0000 0111 0011 1000. E você?

Dividir a chave em duas partes: Chave de Ronda 1 (K1) e Chave de Ronda 2 (K2).

K1: 1010 0111
K2: 0011 1011

Converter o texto claro em ASCII para binário:

"o": 0110 1111
"k": 0110 1011

Realizar a primeira etapa do algoritmo de encriptação:

Adicionar a Chave de Ronda 1 (K1) ao texto claro.

Resultado para "o": 0110 1111 + 1010 0111 = 1101 0100
Resultado para "k": 0110 1011 + 1010 0111 = 0001 0010
Aplicar a substituição usando a S-box.

Resultado para "o": 1101 0100 => 1000 0110
Resultado para "k": 0001 0010 => 0100 1001
Aplicar a permutação (ShiftRows).

Resultado para "o": 1000 0110 => 1000 0110 (nenhum deslocamento)
Resultado para "k": 0100 1001 => 1001 0100 (deslocamento uma posição para a esquerda)
Realizar a segunda etapa do algoritmo de encriptação:

Adicionar a Chave de Ronda 2 (K2) ao resultado da etapa anterior.

Resultado para "o": 1000 0110 + 0011 1011 = 1011 0001
Resultado para "k": 1001 0100 + 0011 1011 = 1100 1111
Aplicar a substituição usando a S-box.

Resultado para "o": 1011 0001 => 0011 0100
Resultado para "k": 1100 1111 => 1000 1010
Aplicar a permutação final (ShiftRows).

Resultado para "o": 0011 0100 => 0011 0100 (nenhum deslocamento)
Resultado para "k": 1000 1010 => 1000 1010 (nenhum deslocamento)
Portanto, o texto cifrado resultante para "ok" usando a chave 1010 0111 0011 1011 no S-AES é:

Cifrado "o": 0011 0100
Cifrado "k": 1000 1010

7. Compare AES com DES. Para cada um dos seguintes elementos do DES, indique o elemento
comparável no AES ou explique por que ele não é necessário no AES.
(a) XOR do material da subchave com a entrada da função f.

XOR do material da subchave com a entrada da função f:
No AES, cada subchave é expandida a partir da chave principal usando o algoritmo de expansão de chave. Durante o processo de criptografia, as subchaves são combinadas com a entrada do estado usando uma operação de XOR, mas não é especificamente o XOR do material da subchave com a entrada da função f. Portanto, não há um elemento comparável direto no AES.

(b) XOR da saída da função f com a metade esquerda do bloco.

XOR da saída da função f com a metade esquerda do bloco:
No AES, não há uma etapa equivalente ao XOR da saída da função f com a metade esquerda do bloco. No AES, as transformações são aplicadas a todo o bloco de dados simultaneamente, não havendo a necessidade de separar e realizar operações exclusivas em metades específicas do bloco.

(c) função f.

O DES possui uma função f (chamada de função de transformação de Feistel) que é aplicada repetidamente em cada rodada para confundir e difundir os dados. No AES, a função f não é necessária, pois o algoritmo opera usando uma estrutura de substituição-permutação que inclui etapas de substituição (SubBytes) e permutação (ShiftRows, MixColumns).

(d) permutação P.

O DES possui uma permutação P que é aplicada após a função f em cada rodada para misturar os bits do bloco. No AES, não há uma permutação P específica, pois a mistura dos bits é realizada pelas etapas de ShiftRows e MixColumns.

(e) troca de metades do bloco.

O DES envolve uma troca de metades do bloco (troca entre a metade esquerda e a metade direita) após cada rodada. No AES, não há uma troca de metades do bloco equivalente, pois o algoritmo opera nas colunas e linhas do array Estado e não possui uma estrutura de rede de Feistel como o DES.


Em resumo, o AES e o DES são algoritmos de criptografia diferentes com diferentes estruturas e elementos. Alguns elementos presentes no DES, como a função f, permutação P e troca de metades do bloco, não são necessários no AES devido às diferenças nas abordagens e estruturas dos algoritmos.
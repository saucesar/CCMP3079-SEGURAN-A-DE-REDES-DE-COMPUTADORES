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


5. **Por que alguns modos de operação de cifra de bloco só utilizam a encriptação, enquanto outros empregam encriptação e decriptação?**

Os modos de operação de cifra de bloco são técnicas usadas para determinar como uma cifra de bloco (como o AES) deve ser aplicada para cifrar ou decifrar dados maiores do que o tamanho do bloco da cifra. Alguns modos de operação utilizam apenas a encriptação, enquanto outros empregam tanto a encriptação quanto a decriptação. Essa diferença ocorre devido aos diferentes objetivos e propósitos dos modos de operação e à forma como eles gerenciam a segurança e a eficiência.

A escolha entre usar apenas a encriptação ou envolver tanto a encriptação quanto a decriptação depende dos objetivos do modo de operação e de como ele deve ser projetado para alcançar os níveis desejados de segurança, integridade e eficiência.


6. **Você deseja construir um dispositivo de hardware para realizar encriptação de bloco no modo cipher block chaining (CBC) usando um algoritmo mais forte do que DES. 3DES é um bom candidato. A Figura 1 mostra duas possibilidades, ambas acompanhando a definição do CBC.
Qual das duas você escolheria:**

**(a) Por segurança?**
Opção b. Por possuir mais loops, o que aprimora a encriptação.

**(b) Por desempenho?**
Opção a. Possui apenas um loop de encriptação, tornando a execução bem mais rápida se comparado com a opção b.


7. Crie um software que possa encriptar e decriptar no modo cipher block chaining usando uma
das seguintes cifras: módulo affine 256, módulo Hill 256, S-DES, DES.
Teste os dados para S-DES usando um vetor de inicialização binário de 1010 1010. Um texto
claro binário de 0000 0001 0010 0011 encriptado com uma chave binária de 01111 11101
deverá dar um texto claro binário de 1111 0100 0000 1011. A decriptação deverá funcionar
de modo correspondente.

```python
# Substituição e permutação S-DES
P10 = [3, 5, 2, 7, 4, 10, 1, 9, 8, 6]
P8 = [6, 3, 7, 4, 8, 5, 10, 9]
P4 = [2, 4, 3, 1]
IP = [2, 6, 3, 1, 4, 8, 5, 7]
IP_INV = [4, 1, 3, 5, 7, 2, 8, 6]
EP = [4, 1, 2, 3, 2, 3, 4, 1]
S0 = [[1, 0, 3, 2],
      [3, 2, 1, 0],
      [0, 2, 1, 3],
      [3, 1, 3, 2]]
S1 = [[0, 1, 2, 3],
      [2, 0, 1, 3],
      [3, 0, 1, 0],
      [2, 1, 0, 3]]

# Funções auxiliares S-DES
def permute(input, mapping):
    return [input[i - 1] for i in mapping]

def xor(a, b):
    return [int(x) ^ int(y) for x, y in zip(a, b)]

def split_half(input):
    mid = len(input) // 2
    return input[:mid], input[mid:]

def sbox_lookup(input, sbox):
    row = int(input[0] + input[3], 2)
    col = int(input[1] + input[2], 2)
    return format(sbox[row][col], '02b')

# Funções S-DES
def key_generation(key):
    key = permute(key, P10)
    left, right = split_half(key)
    
    left = left[1:] + [left[0]]
    right = right[1:] + [right[0]]
    
    subkey1 = permute(left + right, P8)
    
    left = left[2:] + left[:2]
    right = right[2:] + right[:2]
    
    subkey2 = permute(left + right, P8)
    
    return subkey1, subkey2

def fk(input, subkey):
    left, right = split_half(input)
    
    expanded = permute(right, EP)
    xor_result = xor(expanded, subkey)
    
    sbox_input = [xor_result[:4], xor_result[4:]]
    
    sbox_output = [sbox_lookup(sbox_input[0], S0), sbox_lookup(sbox_input[1], S1)]
    sbox_output = [int(bit) for char in sbox_output for bit in char]
    
    p4_result = permute(sbox_output, P4)
    
    new_right = xor(left, p4_result)
    new_left = right
    
    return new_left + new_right

def encrypt_block(block, subkey1, subkey2):
    block = permute(block, IP)
    block = fk(block, subkey1)
    block = block[4:] + block[:4]
    block = fk(block, subkey2)
    block = permute(block, IP_INV)
    return block

def decrypt_block(block, subkey1, subkey2):
    block = permute(block, IP)
    block = fk(block, subkey2)
    block = block[4:] + block[:4]
    block = fk(block, subkey1)
    block = permute(block, IP_INV)
    return block

def cbc_encrypt(data, key, iv):
    subkey1, subkey2 = key_generation(key)
    ciphertext = []
    previous_block = iv
    
    for block in data:
        block = xor(block, previous_block)
        encrypted_block = encrypt_block(block, subkey1, subkey2)
        ciphertext.append(encrypted_block)
        previous_block = encrypted_block
    
    return ciphertext

def cbc_decrypt(ciphertext, key, iv):
    subkey1, subkey2 = key_generation(key)
    plaintext = []
    previous_block = iv
    
    for encrypted_block in ciphertext:
        decrypted_block = decrypt_block(encrypted_block, subkey1, subkey2)
        decrypted_block = xor(decrypted_block, previous_block)
        plaintext.append(dec


# Substituição e permutação S-DES (como mencionado anteriormente)
# Funções auxiliares S-DES (como mencionado anteriormente)
# Funções S-DES (como mencionado anteriormente)

# Função para converter uma string binária em uma lista de inteiros
def binary_string_to_list(binary_string):
    return [int(bit) for bit in binary_string]

# Função para converter uma lista de inteiros em uma string binária
def list_to_binary_string(bit_list):
    return ''.join(str(bit) for bit in bit_list)

# Vetor de inicialização (IV) e chave
iv = "10101010"
key = "0111111101"

# Dados de entrada e saída esperados
plaintext_binary = "0000000100100011"
ciphertext_expected = "1111010000001011"
decrypted_text_expected = plaintext_binary

# Converter o IV e a chave em listas de inteiros
iv_list = binary_string_to_list(iv)
key_list = binary_string_to_list(key)

# Converter o texto claro binário em uma lista de blocos
plaintext_blocks = [binary_string_to_list(plaintext_binary[i:i+8]) for i in range(0, len(plaintext_binary), 8)]

# Criar as chaves de subchave
subkey1, subkey2 = key_generation(key_list)

# Criar o vetor para manter o estado do bloco anterior (inicializado com o IV)
previous_block = iv_list

# Encriptar os blocos
ciphertext_blocks = []
for plaintext_block in plaintext_blocks:
    plaintext_block_xor_prev = xor(plaintext_block, previous_block)
    encrypted_block = encrypt_block(plaintext_block_xor_prev, subkey1, subkey2)
    ciphertext_blocks.append(encrypted_block)
    previous_block = encrypted_block

# Converter a saída cifrada para uma string binária
ciphertext_binary = ''.join(list_to_binary_string(block) for block in ciphertext_blocks)

# Imprimir a saída cifrada
print("Ciphertext (Expected):", ciphertext_expected)
print("Ciphertext (Generated):", ciphertext_binary)

# Decriptar os blocos
decrypted_blocks = []
previous_block = iv_list
for ciphertext_block in ciphertext_blocks:
    decrypted_block = decrypt_block(ciphertext_block, subkey1, subkey2)
    decrypted_block_xor_prev = xor(decrypted_block, previous_block)
    decrypted_blocks.append(decrypted_block_xor_prev)
    previous_block = ciphertext_block

# Converter a saída decriptada para uma string binária
decrypted_binary = ''.join(list_to_binary_string(block) for block in decrypted_blocks)

# Imprimir a saída decriptada
print("Decrypted Text (Expected):", decrypted_text_expected)
print("Decrypted Text (Generated):", decrypted_binary)

```
---
title: "Melhores bibliotecas de criptografia em C++20"
description: "O objetivo deste artigo é fornecer uma lista abrangente de bibliotecas em C++ que podem ser usadas com os novos recursos do C++20. O que veremos será de grande utilidade quando você precisar de uma implementação específica de uma funcionalidade particular."
lead: ""
date: 2022-10-17T01:10:21-03:00
lastmod: 2022-10-17T01:10:21-03:00
draft: false
images: []
menu:
  docs:
    parent: ""
    identifier: "cryptography-libraries-c20-49ccc17a165dd74feb31b4b50cca7214"
weight: 3002
toc: true
---
## Visão geral das bibliotecas de criptografia

Na tabela abaixo listamos as bibliotecas mais importantes; cuja seleção foi baseada em duas métricas:

Tempo de execução e flexibilidade.

Acesso ao source code baseado em licenças de código aberto.

Ter acesso ao código-fonte é muito útil porque você pode comparar seu trabalho e algoritmos aos outros algoritmos e implementações, com isso, você pode melhorar seu trabalho.

| **Título da biblioteca** |       **Desenvolvedor/Indústria**       | **Linguagem de Programação** | **Código Aberto** | **Referências** |
|:------------------------:|:---------------------------------------:|:----------------------------:|:-----------------:|:---------------:|
|        **OpenSSL**       |             OpenSSL Project             |               C              |        sim        |  [1.](https://www.openssl.org/)[2.](https://github.com/openssl/openssl)[3.](https://slproweb.com/products/Win32OpenSSL.html)               |
|       **Crypto++**       |            Crypto C++ Project           |              C++             |        sim        |  [4.](https://cryptopp.com/)[5.](https://cryptopp.com/docs/ref/)              |
|         **Botan**        |                Jack Lloyd               |              C++             |        sim        |  [6.](https://botan.randombit.net/)               |
|       **Libcrypt**       |             GnuPC Commmunity            |               C              |        sim        |  [7.](https://www.gnupg.org/related_software/libgcrypt/)[8.](https://www.gnupg.org/documentation/manuals.html)               |
|        **GnuTLS**        | Simon Josefsson/Nikos Mavrogiannopoulos |               C              |        sim        |  [9.](https://gnutls.org/)[10.](https://gnutls.org/documentation.html)               |
|       **Cryptlib**       |              Peter Gutmann              |               C              |        sim        |  [11.](https://cryptlib.com/)              |

Para cada uma das bibliotecas, apresentaremos as melhores implementações das primitivas criptográficas (como geração e troca de chaves, criptografia de curva elíptica, criptografia de chave pública, funções de hash, algoritmos MAC, cifras de bloco, etc.).

### Hash Functions

A Tabela abaixo mostra as bibliotecas de criptografia e seus recursos em diferentes funções de hash.

| **Título da biblioteca** |                                 **MD5**                                 | **SHA-1** | **SHA-2** | **SHA-3** | **Whirlpool** | **GOST** | **BLAKE2** |
|:------------------------:|:-----------------------------------------------------------------------:|:---------:|:---------:|:---------:|:-------------:|:--------:|:----------:|
|        **OpenSSL**       |                                   sim                                   |    sim    |    sim    |    sim    |      sim      |    sim   |     sim    |
|       **Crypto++**       |                                   sim                                   |    sim    |    sim    |    sim    |      sim      |    sim   |     sim    |
|         **Botan**        |                                   sim                                   |    sim    |    sim    |    sim    |      sim      |    sim   |     sim    |
|       **Libcrypt**       |                                   sim                                   |    sim    |    sim    |    sim    |      sim      |    sim   |     sim    |
|       **Cryptlib**       |                                   sim                                   |    sim    |    sim    |    sim    |      sim      |     -    |      -     |

Agora, escolheremos aleatoriamente uma função hash de uma biblioteca (por exemplo, uma implementação MD5 do OpenSSL) e forneceremos alguns comentários sobre a implementação. É muito importante mencionar que a implementação fornecida para a função hash MD5 já está implementada no OpenSSL e isso será feito com respeito à implementação original de [1](https://www.openssl.org/source/). A primeira coisa a fazer é baixar o arquivo ***openssl -1.1.1g.tar.gz*** e extrair o conteúdo para ter acesso ao código fonte. Depois de extraído, navegue até a pasta crypto seguindo o caminho openssl-1.1.1g\crypto. Desta forma, você terá acesso aos arquivos de código fonte de todos os algoritmos criptográficos implementados dentro da biblioteca. Veja a figura abaixo.

![img](./openssl.png)

### Overview da função hash MD5

Escolhemos este exemplo porque é um algoritmo simples, por isso é fácil de seguir e entender. A implementação do MD5 contém três arquivos (dois arquivos C e um arquivo de cabeçalho) e uma pasta ASM com três arquivos escritos na linguagem PERL. Os arquivos PERL são otimizações para quatro plataformas, 586, x86, x64 e sparc.

Exemplo:

![img](./md5.png)

Você também pode usar o [Gerador de hash MD5](https://www.md5hashgenerator.com/).
_____

### Criptografia de chave pública

A maioria das bibliotecas inclui implementações de diferentes padrões de PKCS (Public Key Cryptography Standards) e são bem testadas.

| **Título da biblioteca** | **PKCS#1** | **PKCS#5** | **PKCS#8** | **PKCS#12** | **IEEE P1363** | **ASN.1** |
|:------------------------:|:----------:|:----------:|:----------:|:-----------:|:--------------:|:---------:|
|        **OpenSSL**       |     sim    |     sim    |     sim    |     sim     |        -       |    sim    |
|       **Crypto++**       |     sim    |     sim    |     sim    |      -      |       sim      |    sim    |
|         **Botan**        |     sim    |     sim    |     sim    |      -      |       sim      |    sim    |
|       **Libcrypt**       |     sim    |     sim    |     sim    |     sim     |       sim      |    sim    |
|       **Cryptlib**       |     sim    |     sim    |     sim    |     sim     |        -       |     -     |

Para usar criptografia de chave pública usando o OpenSSL, siga o exemplo abaixo para ver o workflow. Suponha que existam dois usuários, Alice e Bob, que se comunicam entre si. O fluxo de trabalho de comunicação é o seguinte.

1. Alice gera uma chave privada, ***alicePrivateKey.pem*** com 2048 bits.
   
```html
openssl genrsa -out alicePrivateKey.pem 2048
```
![img](aliceprivatekey.png)

2. Alice extrai a chave pública ***alicePublicKey.pem*** e a envia para Bob.
   
```html
openssl rsa -pubout -in alicePrivateKey.pem -out alicePublicKey.pem
```
![img](alicepublickey.png)

3. Bob criptografa a mensagem e envia ***BobMessageToAllice.txt*** para Alice.

```html
openssl rsautl -encrypt -in cleartext -out encryptedWithAlicePubKey -inkey alicePublicKey.pem -pubin 
```
4. Alice descriptografa a mensagem de Bob.
   
```html
openssl rsautl -decrypt -in encryptedWithAlicePubKey -inkey alicePrivKey.pem
```
______

### Criptografia de curva elíptica (ECC)

Um dos protocolos de key exchange mais utilizados com base em curvas elípticas é o ECDH (Elliptic Curve Diffie-Hellman). O objetivo deste protocolo é definir uma chave secreta compartilhada utilizada no processo de criptografia sem a necessidade de enviá-la diretamente para cada um dos úsuarios dentro do processo de comunicação.

| **Título da biblioteca** | **NIST** | **SECG** | **ECDSA** | **ECDH** | **GOST R 34.10** |
|:------------------------:|:--------:|:--------:|:---------:|:--------:|:-----------------:|
|        **OpenSSL**       |    sim   |    sim   |    sim    |    sim   |        sim        |
|       **Crypto++**       |    sim   |    sim   |    sim    |    sim   |         -         |
|         **Botan**        |    sim   |    sim   |    sim    |    sim   |        sim        |
|       **Libcrypt**       |    sim   |    sim   |    sim    |    sim   |        sim        |
|       **Cryptlib**       |    sim   |    sim   |    sim    |    sim   |         -         |

Para evitar o aparato matemático por trás do protocolo, resumiremos o fluxo de trabalho do protocolo da seguinte forma para que você tenha uma visão clara dos parâmetros de domínio que são trocados entre os úsuarios de comunicação (Alice e Bob):

- Alice gera uma chave privada e uma chave pública com os parâmetros do domínio.
- Bob gera uma chave privada e uma chave pública com o domínio parâmetros definidos acima.
- Ambos os usuários trocam suas chaves públicas.
- Alice calcula usando a chave pública de Bob e a função compartilhada é caracterizada por um segredo compartilhado, conhecido como chave derivada de B.
- Bob faz a mesma coisa com a chave pública de Alice. A função compartilhada é caracterizada por um segredo compartilhado, conhecido como chave derivada de A.
- Alice agora usa a chave derivada de Bob para criptografar a mensagem.
- Bob usa a chave derivada de Alice para criptografar a mensagem.
- Ambos os usuários podem descriptografar a mensagem usando sua própria chave privada.

Para ficar mais claro, vamos tentar implementar o algoritmo ECDH em python. Vamos usar o código criador pelo [Svetlin Nakov](https://cryptobook.nakov.com/asymmetric-key-ciphers/ecdh-key-exchange-examples).

Usaremos a biblioteca **tinyec** para ECC em Python

```python
pip install tinyec
```
Agora, vamos gerar **dois pares** de chaves público-privadas, trocar as **chaves públicas** e calcular o segredo compartilhado:

```python
from tinyec import registry
import secrets

def compress(pubKey):
    return hex(pubKey.x) + hex(pubKey.y % 2)[2:]

curve = registry.get_curve('brainpoolP256r1')

alicePrivKey = secrets.randbelow(curve.field.n)
alicePubKey = alicePrivKey * curve.g
print("Alice public key:", compress(alicePubKey))

bobPrivKey = secrets.randbelow(curve.field.n)
bobPubKey = bobPrivKey * curve.g
print("Bob public key:", compress(bobPubKey))

print("Now exchange the public keys (e.g. through Internet)")

aliceSharedKey = alicePrivKey * bobPubKey
print("Alice shared key:", compress(aliceSharedKey))

bobSharedKey = bobPrivKey * alicePubKey
print("Bob shared key:", compress(bobSharedKey))

print("Equal shared keys:", aliceSharedKey == bobSharedKey)

```
A curva elíptica usada para os cálculos de ECDH é de 256 bits denominada curva brainpoolP256r1. As chaves privadas são de 256 bits (64 dígitos hexadecimais) e são geradas aleatoriamente. As chaves públicas serão de 257 bits (65 dígitos hexadecimais), devido à compressão das chaves.

O output do código acima dever ser assim:

```python
Alice public key: 0x66c808e6b5be6d6620934bc6ffa2b8b47f9786c002bfb06d53a0c27535641a5d1
Bob public key: 0x7d15195432d1ac7f38aeb054d07d9b2e1faa913b78ad04d5efdd4a1ee8d9a3191
Now exchange the public keys (e.g. through Internet)
Alice shared key: 0x90f5a1cf2ed1dbb0322178df6bb0dd72c541884618b2989a3e5e663198667a621
Bob shared key: 0x90f5a1cf2ed1dbb0322178df6bb0dd72c541884618b2989a3e5e663198667a621
Equal shared keys: True
```
Devido à randomização, se você executar o código acima, as chaves serão diferentes, mas o segredo compartilhado calculado para Alice e Bob no final será sempre o mesmo. O segredo compartilhado gerado é um inteiro de 257 bits (ponto EC compactado para curva de 256 bits, codificado como 65 dígitos hexadecimais).

### Criando chaves ECDH

É muito importante que primeiro verifiquemos qual suporte OpenSSL você tem em seu computador relacionados a chave ECDH. Para fazer isso, digite o seguindo comando no seu terminal:

```html
openssl ecparam -list_curves
```
O comando fornecerá uma lista completa de curvas que você pode usar, e a maioria delas são implementados adequadamente com respeito aos seus padrões. Sua implementação no OpenSSL e as atualizações recentes usando os novos recursos do C++20 os tornam fáceis de seguir.

![img](./curves-list.png)
*Veja a lista completa executando o comando no seu terminal*

Temos uma maneira rápida de gerar o par de chaves usando o **prime256v1** com o seguinte comando:

```html
openssl ecparam -name prime256v1 -genkey -noout -out myKey.pem
```
![img](./ec-key.png)

Isso deve fornecer um arquivo PEM contendo sua chave privada EC, que deve paracer com o seguinte:

```html
-----BEGIN EC PRIVATE KEY-----
MHcCAQEEIBmkTf1F3t19l3hKpFRUNl0SdqXmlmFo6htO5EFlTu2UoAoGCCqGSM49
AwEHoUQDQgAEuRUFJ+JrdzkzXppuMELz7Oc7wUqLvy+rJr8sb5f9HLGo8H5hJO9C
bywgBGKuhxhZJAvx8vUeYaIjkc5drj4iag==
-----END EC PRIVATE KEY-----
```
Agora que você tem sua chave privada, pode usá-la para gerar outro PEM, contendo apenas sua chave pública.

```html
openssl ec -in myKey.pem -pubout -out public-key.pem
```
![img](ec-public.png)

Você terá agora outro arquivo PEM, contendo sua chave-pública:

```html
-----BEGIN PUBLIC KEY-----
MFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAEuRUFJ+JrdzkzXppuMELz7Oc7wUqL
vy+rJr8sb5f9HLGo8H5hJO9CbywgBGKuhxhZJAvx8vUeYaIjkc5drj4iag==
-----END PUBLIC KEY-----
```
Se você quiser ver os detalhes do parâmetro EC, execute o seguinte comando:

```html
openssl ec -in mykey.pem -text -noout
```
![img](ec-details.png)
_____


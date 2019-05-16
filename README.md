
# Teste Python | Omelete


## Problema


Dada uma matriz de tamanho MxN na qual cada elemento represente um pixel, crie  um programa que leia uma sequência de comandos e os interprete manipulando a matriz de acordo com a descrição de cada comando.


O programa deve rodar em uma aplicação web e os comandos serão recebidos por meio de uma API REST.  Uma sequência de comandos deve ser enviada em uma única requisição e a API deverá responder com a matriz em seu estado final, após a aplicação de cada comando, respeitando a ordem de execução da sequência.


A API REST deve aceitar o input dos comandos em dois formatos:
**1 -** enviando os comandos diretamente na requisição, como plain text, retornando a saída também como plain text; 
**2 -** enviando os comandos como um objeto JSON, retornando a saída também como um objeto JSON.

Os dois casos devem ser implementados e servidos por meio de endpoints diferentes, sendo que o segundo endpoint deve ser terminado em ".json".

A aplicação deve ser implementada em Python e recomendamos o uso de frameworks Django ou Flask.

Recomendamos também o uso de Docker.

A implementação de testes automatizados é recomendada. 



## Comandos

I M N

Cria uma nova matriz MxN. Todos os pixels são brancos (O).

C

Limpa a matriz. O tamanho permanece o mesmo. Todos os pixels ficam brancos (O).

L X Y C

Colore um pixel de coordenadas (X,Y) na cor C.

V X Y1 Y2 C

Desenha um segmento vertical na coluna X nas linhas de Y1 a Y2 (intervalo inclusivo) na cor C.

H X1 X2 Y C

Desenha um segmento horizontal na linha Y nas colunas de X1 a X2 (intervalo inclusivo) na cor C.

K X1 Y1 X2 Y2 C

Desenha um retangulo de cor C. (X1,Y1) é o canto superior esquerdo e (X2,Y2) o canto inferior direito.

F X Y C

Preenche a região com a cor C. A região R é definida da seguinte forma:
O pixel (X,Y) pertence à região. Outro pixel pertence à região, se e somente se, ele tiver a mesma cor que o pixel (X,Y) e tiver pelo menos um lado em comum com um pixel pertencente à região, seja na vertical ou na horizontal.

## Considerações

Comandos diferentes de I, C, L, V, H, K, F, S e X devem ser ignorados.

## Testes



### Entrada 01:

I 5 6

L 2 3 A

G 2 3 J

V 2 3 4 W

H 3 4 2 Z

F 3 3 J

### Saida 01:

JJJJJ

JJZZJ

JWJJJ

JWJJJ

JJJJJ

JJJJJ

### Entrada 02:

I 10 9

L 5 3 A

G 2 3 J

V 2 3 4 W

H 1 10 5 Z

F 3 3 J

K 2 7 8 8 E

F 9 9 R

### Saida 02:

JJJJJJJJJJ

JJJJJJJJJJ

JWJJAJJJJJ

JWJJJJJJJJ

ZZZZZZZZZZ

RRRRRRRRRR

REEEEEEERR

REEEEEEERR

RRRRRRRRRR

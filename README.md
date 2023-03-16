# C/C++ Core!

## Qual é o propósito do C/C++ Core?
Esse repositório tem a motivação de *repassar* uma parte do conhecimento fundamental adquirido em **C** ao longo dos últimos meses.
Tenho notado que muitos programadores iniciantes encontram dificuldades em interpretar e implementar fundamentos da linguagem - Como comunidade, acho beem legal a ideia de repassar alguns conhecimentos! Então sejam bem vindos ao meu documento informal sobre como iniciar sua jornada em C!
*Disclaimer: Eu não sou e em momento nenhum me apresento como a maior autoridade em C do universo. Só quero ajudar  ;)*

**Index -**
1. Programar, qual o lance com isso?
2. O que é C? (em construção)
3. Como usar C? (em construção)
4. Operadores (em construção)
5. Sintaxe da Linguagem!
6. ???
7. ???
8. ???
9. ???
10. ???

## Programar, qual o lance com isso?
Pra mim, programar não é muito diferente de qualquer e toda arte que você encontra por aí. É criar coisas completamente novas a partir de bits, transformar sua imaginação em coisas palpáveis e visíveis! Programar te dá a capacidade de criar seus próprios instrumentos musicais, elaborar ferramentas complexas, criar jogos e organismos complexos- é insano.
É como tocar algum instrumento, como uma guitarra. Tudo que você precisa fazer é entender como os movimentos feitos por você podem reagir com o instrumento para criar música. Com programação, podemos trocar a guitarra por um computador, onde você passa cadeias de comandos com a intenção que ele retorne algo novo, elaborado e sugerido por você! As possibilidades são virtualmente infinitas ;)

## O que é C?
[C](https://en.wikipedia.org/wiki/C_(programming_language)) é uma [linguagem de programação](https://pt.wikipedia.org/wiki/Linguagem_de_programa%C3%A7%C3%A3o#:~:text=A%20linguagem%20de%20programa%C3%A7%C3%A3o%20%C3%A9,instru%C3%A7%C3%B5es%20de%20processamento%20ao%20computador.). Linguagens de programação são essencialmente interpretadores, coisas que fazem as coisas que você diz serem legiveis para a máquina... É como se você estivesse usando o Google Tradutor para se comunicar com um estrangeiro!
Computadores são máquinas complexas que trabalham informações usando binário - Humanos tem muita dificuldade interpretando binário, e por isso geralmente não fazemos isso: nós deixamos para que as linguagens de programação façam o intermédio entre homem-máquina.

C especificamente é uma linguagem imperativa. Das aulas de português, imperativo faz referencia a ordens, pedidos e afins. Isso significa que ao usar C, precisamos escrever blocos de **ordens**, que serão levados ao processador do computador e retornarão algo. Simples, não?

## Sintaxe da linguagem!
The books are on the table = Os livros estão na mesa.
Linguagens de programação também tem conjuntos de coisas que significam... Bem, outras coisas! Vamos começar pelo básico:

### Declarações de tipo:

##### int
Int vem de Integer, que representa algo no inteiro matemático. Ints são referenciados como o interante do conjunto matemático ao qual fazem referência. 
Se eu quiser, por exemplo, criar um contador de 0 a 10, posso faze-lo em C da seguinte maneira:

int numero = 0;
while (numero != 10)
  numero++;

Ints tem 4 bytes, ou  seja, 32 bits (que são binários!) - Isso convem que um int em C tradicionalmente suporte valores entre **-2147483648** e **2147483647**.

É divertido notar que o próximo tipo de tipo a ser comentado, char, tem apenas 1 byte de tamanho! Ou seja, na prática, um int é 4x mais pesado que uma letra.

#### char
Char vem de Character, ou, na lingua brazuca, caractere;
Caracteres são  contidos na tabela [ASCII](https://www.rapidtables.com/code/text/ascii-table.html), e são vistos pelo sistema como todo algarismo comunicativo não matemático que compreende a comunicação humano-máquina. Acentos, Ç e caracteres não americanos não fazem parte da tabela ASCII "básica".

Um char tem tamanho de 1 byte, por que seu valor só precisa compreender os 127 caracteres da tabela ASCII. Isso significa que char é literalmente um número, mas um número que faz analogia a um cararactere! No exemplo a seguir vou definir o valor de uma variavel tipo char para "A":

char  letra = 65;

Isso é a mesma coisa que dizer

char  letra = 'A'.

Note que usamos aspas simples para definir o conteudo de 'Letra'. Em C, aspas simples fazem referência a um char. Aspas duplas fazem referência a **strings**, que vamos ver daqui a pouco...!

#### string/array(tipo char)!
Uma string é, em essência, uma cadeia de caracteres. Quando você escreve uma palavra, no seu caderno, com lápis ou caneta, qual é o processo? Para escrever a palavra SAMBA, nós precisamos escrever primeiro o S, depois o A, depois o M, e por assim vai...
Declarações de strings funcionam do mesmo jeito que as de char, em C:

char string[10]

Com isso, estamos informando o computador que queremos montar uma cadeia de 10 caracteres consecutivos! C tem problemas sérios com administração de memória, e strings precisam ser muito cuidadosamente gerenciadas para evitar leaks. Funções como Malloc(), Calloc() e Free() são essênciais para o gerenciamento de memória de programas complexos em C, e, sinceramente, são uma das maiores dores de cabeça que você pode ter na hora de refatorar um código.

Esse é o jeito mais "fácil" de criar strings - Outro jeito está relacionado com o uso de ponteiros!
Usar ponteiros é mais divertido, na minha concepção burra de diversão: Eles te permitem criar strings de tamanhos dinâmicos.

Um ponteiro não é nada mais que um endereço de memória, um marca-página no seu computador - Ele marca, nesse caso, o início da string. Isso é tudo que você precisa saber sobre ponteiros para criar strings.
Uma declaração de string usando ponteiros é a seguinte:

char  *string;

Isso indica, para o computador, que em vez de reservar 1 byte para 1 char, ele vai se preparar para receber uma sequência de caracteres a partir do seu ponteiro. Para dar valor a uma string assim, usamos

char  *string;
string = "conteúdo da string"

Fácil, não?

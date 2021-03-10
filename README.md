## Manual de como usar as cores

​		A muito tempo sinto a necessidade de usar cores no terminal para que os meus códigos possam ser iguais aos exercícios que venho fazendo na apostila Slago-C. Colocar **aprovado** em azul, **em recuperação** em amarelo e assim por diante. Existem alguns exercícios que pedia isso, mas infelizmente a biblioteca **<conio.h>** se encontra quase que impossível de se usar em um sistema operacional Linux (Pelo menos eu tive muita dificuldade). Mesmo sabendo que essa biblioteca mencionada, se encontra totalmente obsoleta, ainda seria interessante usar apenas para fins didáticos por sua simplicidade. Ouvi dizer que a biblioteca **ncurses** poderia substituir, mas pelo fato da complexidade, resolve procurar outras alternativas.
​		Por pura sorte cai em uma página que mostra como fazer isso de forma improvisada, sem a necessidade de bibliotecas como a **conio** e nem a **ncurses**. 

​		A solução é bem básica. Consistem em apenas definir uma constante e atribuir seu valor referente a cor desejada. Exemplo:

```c
#include <stdio.h>
#define RED 	"\x1B[31m" 
#define BOLD 	"\x1B[1m"
#define RESET	"\x1B[0m"

int main(){
    //Fonte vermelha com negrito
    printf(RED BOLD "Hello World!\n" RESET);
	return 0;
}
```

​		Também é possível adicionar plano de fundo (background) nos textos 

``` c
#include <stdio.h>
#define BG_GREEN 	"\x1B[42m"
#define YELLOW		"\x1B[33m"
#define BOLD 	"\x1B[1m"
#define RESET	"\x1B[0m"

int main(){
    //Fonte amarela com negrito e o fundo verde
    printf(YELLOW BOLD BG_GREEN "Hello World!\n" RESET);
	return 0;
}
```

​		Tudo dependerá da sua criatividade apartir de agora. Caso não tenha muita afinidade com o inglês, assim como eu. Fiz questão de colocar mais informações abaixo:

```CQL
BOLD		= Negrito.
STANDOUT 	= Itálico.
FAINT 		= Enfraquece a cor.
UNDERLINE	= Sublinha o texto.
BLINK		= Faz o texto ficar piscando. (literalmente)
REVERSE		= Inverte. A cor do texto passa a ser do fundo. 
HIDDEN		= Esconde. 
NO_HIDDEN	= Desesconde o texto.
NO_STANDOUT = Remove o itálico
Assim por diante...
```

​		Para mais informações, abaixo eu citei as fontes e você poderá obter mais informações lá.



Fontes:
https://wiki.bash-hackers.org/scripting/terminalcodes
http://ascii-table.com/ansi-escape-sequences.php
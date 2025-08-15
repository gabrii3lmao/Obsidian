## 1. Tática número um: Comentar o seu código
Se o código apresentar erro, comente partes dele e teste novamente.  
Se o erro continuar, a parte comentada provavelmente não é a causa.
#### Exemplo: 
Considere o seguinte código: 
``` cpp
int main(){
getNames(); // pergunta ao usuário um monte de nomes
doMaintenance(); // faz umas coisas aleatórias
sortNames(); //organiza em ordem alfabética
printNames(); // escreve a lista organizada de nomes
return 0;
}
```
Vamos dizer que o código está escrevendo os nomes em ordem contrária do que deveria. O erro deve estar em funções que lidam com os nomes; assim, podemos comentar `doMaintenance()` por provavelmente não ser a causa.
``` cpp
int main(){
getNames(); // pergunta ao usuário um monte de nomes
// doMaintenance(); // faz umas coisas aleatórias
sortNames(); //organiza em ordem alfabética
printNames(); // escreve a lista organizada de nomes
return 0;
}
```
Agora, temos três possibilidades:
* Se o problema foi resolvido, então `doMaintenance()` estava causando o problema, logo o erro estava nele.
* Se não tiver mudado nada (o que é bem provável) nós pelo menos teremos menos código para analisar, reduzindo o trabalho.
* Se ao comentar `doMaintenance()` o problema mudar para outro relacionado, ela provavelmente é necessária a outro código. Nesse caso, reative-a e teste outra abordagem.

## 2. Tática número 2: Validando seu fluxo de código
Outro problema comum em programas mais complexos é que o programa chama uma função muitas ou poucas vezes (inclusive nenhuma vez). Nesses casos, pode ser útil colocar instruções no topo das suas funções para exibir o nome da função.

#### Exemplo:

``` cpp
int getValue(){
	return 4;
}

int main(){
std::cout << getValue << '\n';

	return 0;
}
```
Embora esperamos que o programa acima imprima _4_, ele deve printar o lugar onde o endereço da função está.
Vamos adicionar algumas instruções de depuração nesse código: 
``` cpp
#include <iostream>

int getValue(){
std::cerr << "getValue() chamado\n";
return 4;
}

int main(){
std::cerr << "main() chamado\n";
	std::cout << getValue << '\n';

return 0;
}
```
Quando vemos o output, percebemos que a função ``getValue()`` não havia sido chamada na main. Analisando o erro, vemos que a função estava sem parênteses .

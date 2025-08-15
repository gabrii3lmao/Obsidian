## Modularizar funções é um passo importante para uma estrutura organizada. 

 Caso tenha uma parte que se repita muitas vezes, você pode separar elas em funções. Logo, você não precisará mais digitar tudo do começo. Apenas precisará chamar uma função.

## Exemplo:
#### Podemos usar esse código:
```cpp
void startQuestion(){
std::cout << "==================";
std::cout << "COMEÇO DO CÓDIGO";
std::cout << "==================";
}

int main(){
//questão 1.
startQuestion();

//questão 2.
startQuestion();
.
.
.
return 0;
}
```
#### Em vez de: 
```cpp
int main(){
//questão 1
std::cout << "==================";
std::cout << "COMEÇO DO CÓDIGO";
std::cout << "==================";
//questão 2.
std::cout << "==================";
std::cout << "COMEÇO DO CÓDIGO";
std::cout << "==================";

return 0;
}
```
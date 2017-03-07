# Treinamento python/django
## Introdução ao python
### Instalação
No linux o python já vem instalado, verifique na sua máquina qual a versão está rodando abrindo o terminal e executando o seguinte comando:
```
$ python -V
Python 2.7.10
```
Se a versão do python for 2 ponto alguma coisa, vamos instalar a versão mais nova que é a 3.6.0. Vamos fazer a instalação usando um biblioteca chamada `pyenv`.
Precisamos instalar algumas coisas antes execute o seguinte comando:
```
$ sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev xz-utils git
```
Agora vamos instalar de fato o `pyenv` executando este outro comando:
```
$ curl -L https://raw.githubusercontent.com/yyuu/pyenv-installer/master/bin/pyenv-installer | bash
```
Quando terminar de instalar pegue as seguintes linhas e insira no final do arquivo `~/.bashrc` e feche o terminal e abra novamente:
```
export PATH="~/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```
Ao abrir novamente o terminal teste se o pyenv está funcionando executando o comando `pyenv`.
Para instalar o versão 3.6.0 do python execute o seguinte comando:
```
$ pyenv install 3.6.0
```
E agora execute este outro comando:
```
$ pyenv global 3.6.0
```
Agora testa se funcionou executando:
```
$ python -V
Python 3.6.0
```
### Operadores aritméticos
Abaixo segue uma lista com os operadores aritméticos utilizados em Python:
 - "+" → soma
 - "–" → subtração
 - "*" → multiplicação
 - "/" → divisão
 - "//" → divisão de inteiros
 - "**" → potenciação
 - "%" → módulo (resto da divisão)
 
### Tipos primitivos
#### Simples
inteiro (`int`)
ponto flutuante (`float`)
booleano (`bool`)
complexo (`complex`)
string (`string`)
#### Compostos
listas (`list`)
dicionários (`dict`)
tuplas (`tuple`)
conjuntos (`set`)

### Executando python
Abra o terminal e abra o interpretador python executendo o comando `python`.
E depois, tente digitar alguma operação matemática, como 2 + 3 e aperte Enter.
```
>>> 2 + 3
5
```
### Strings
Digite olá entre aspas, desse jeito:
```
>>> "Ola"
'Ola'
```
A string sempre precisa iniciar e terminar com o mesmo caractere. Este pode ser aspas duplas(") ou simples(') - elas dizem ao Python que o que está dentro delas é uma string.

Strings podem ser concatenadas. Tente isto:
```
>>> "Oi " + "Ola"
'Oi Ola'
```
Você também pode multiplicar strings por um número:
```
>>> "Ola" * 3
'OlaOlaOla'
```
Se você precisa colocar uma apóstrofe dentro de sua string, existem duas maneiras de fazer.

Usando aspas duplas:
```
>>> "Correndo' ladeira abaixo" 
"Correndo' ladeira abaixo"
```
ou escapando apóstrofo com uma barra invertida (`\`):
```
>>> 'Correndo\' ladeira abaixo'
"Correndo' ladeira abaixo"
```
Legal, hein? Para ver uma string em letras maiúsculas, basta digitar:
```
>>> "Ola".upper()
'OLA'
```
Você acabou de usar a **função** `upper` na sua string! Uma função (como `upper()`) é um conjunto de instruções que o Python realiza em um determinado objeto (`"Ola"`), sempre que você chamar por ele.

Se você quer saber o número de letras de uma string, existe uma função para isso também!
```
>>> len("Ola")
3
```
Se perguntando porque algumas vezes você chama funções com um `.` no fim de uma string (como `"Ola".upper()`) e algumas vezes você primeiro chama a função colocando a string nos parênteses? Bem, em alguns casos, funções pertencem ao objeto, como `upper()`, que só pode ser utilizada em strings. Nesse caso, nós chamamos a função de **método**. Outras vezes, funções não pertencem a nada específico e podem ser usadas em diferentes tipos de objetos, assim como `len()`. É por isso que nós estamos fornecendo `"Ola"` como um parâmetro para a função `len`.

### Erro
Vamos tentar algo novo. Podemos obter o tamanho de um número da mesma forma que podemos encontrar o tamanho de uma string? Digite `len(304023)` e pressione Enter:
```
>>> len(304023)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: object of type 'int' has no len()
```
Temos nosso primeiro erro! Ele diz que objetos do tipo "int" (inteiros, apenas números) não têm nenhum comprimento. Então o que podemos fazer agora? Talvez possamos escrever nosso número como uma string? Strings têm um comprimento, certo?
```
>>> len(str(304023))
6
```
Funcionou! Usamos a função `str` dentro da função `len`. `str()` converte tudo para strings.
- A função str converte as coisas em **strings**
- A função int converte as coisas em **números inteiros**
>>> Importante: podemos converter números em texto, mas nós não podemos, necessariamente, converter texto em números - `int('hello')` por exemplo não funciona.
### Variáveis
Utilizamos variaveis para fazer nossos códigos mais legíveis e para não ter que se lembrar sempre o que algumas coisas significam, por isso é importante definir variáveis com nome significativos.

Digamos que queremos criar uma nova variável chamada `nome`:
 ```
 >>> nome = "Ola"
 ```
 Vê? É fácil! É só fazer: `nome` igual a Ola.

Como você percebeu, seu programa não retornou nada como fez anteriormente. Então como sabemos que a variável realmente existe? Simplesmente digite `nome` e tecle Enter:
```
>>> nome
'Ola'
```
Você sempre pode mudar o seu valor:
```
>>> nome = "Sonja"
>>> nome
'Sonja'
```
Você pode usá-la também em funções:
```
>>> len(nome)
5
```
Incrível não? Claro, variáveis podem ser qualquer coisa, então podem ser números também! Tente isso:
```
>>> a = 4
>>> b = 6
>>> a * b
24
```
Mas, e se digitarmos o nome errado? Você consegue adivinhar o que aconteceria? Vamos tentar!
```
>>> city = "Tokyo"
>>> ctiy
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'ctiy' is not defined
```
Um erro! Como você pode ver, Python tem diferentes tipos de erros e este é chamado **NameError**. Python dará este erro se você tentar usar uma variável que não foi definida ainda. Se você encontrar esse erro depois, veja se no seu código se você não digitou o nome de uma variável errado.

### Função print
Tente isso:
```
>>> nome = 'Maria'
>>> nome
'Maria'
>>> print(nome)
Maria
```
Quando você apenas digita `nome`, o interpretador Python responde com a representação como string da variável `'nome'`, que são as letras M-a-r-i-a, entre aspas simples. Quando você diz `print(nome)`, Python vai "imprimir" o conteúdo da variável na tela, sem as aspas, o que é mais puro.

Como veremos mais tarde, `print()` também é útil quando queremos imprimir algo dentro de funções, ou quando queremos imprimir algo em várias linhas.

### Listas
Além de strings e inteiros, o Python tem todos os tipos diferentes de objetos. Vamos apresentar um chamado **lista**. Listas são exatamente o que você acha que elas são: elas são objetos que são listas de outros objetos :)

Vá em frente e crie uma lista:
```
>>> []
[]
```
Sim, esta é uma lista vazia. Não é muito, não é? Vamos criar uma lista dos números da loteria. Como não queremos ficar repetindo o código todo o tempo vamos criar uma variável para ela:
```
>>> loteria = [3, 42, 12, 19, 30, 59]
```
Tudo certo, nós temos uma lista! O que podemos fazer com isso? Vamos ver quantos números de loteria existem nesta lista. Você tem ideia de qual função deve usar para isso? Você já sabe disso!
```
>>> len(loteria)
6
```
Sim! `len()` pode te dar o número de objetos que fazem parte de uma lista. Uma mão na roda, não? Vamos organizar isso agora:
```
>>> loteria.sort()
```
Isso não retorna nada, apenas troca a ordem em que os números aparecem na lista. Vamos imprimir isso outra vez e ver o que acontece:
```
>>> print(loteria)
[3, 12, 19, 30, 42, 59]
```
Como você pode ver, os números na nossa lista estão ordenados do menor para o maior.
Talvez a gente queira inverter essa ordem? Vamos fazer isso!
```
>>> loteria.reverse()
>>> print(loteria)
[59, 42, 30, 19, 12, 3]
```
Moleza né? Se você quiser adicionar alguma coisa à sua lista, você pode fazer isto digitando o seguinte comando:
```
>>> loteria.append(199)
>>> print(loteria)
[59, 42, 30, 19, 12, 3, 199]
```
Se você quiser mostrar apenas o primeiro número você pode usar **índices**. Um índice é um número que diz onde um item da lista está. Os computadores gostam de iniciar a contagem por 0, então o primeiro objeto tem índice 0, o próximo tem índice 1 e por aí vai. Tente isso:
```
>>> print(loteria[0])
59
>>> print(loteria[1])
42
```
Como você pode ver, você pode acessar diferentes objetos na sua lista usando o nome da lista e o índice do objeto dentro dos colchetes.

### Dicionários
Um dicionário é semelhante a uma lista, mas você pode acessar valores através de uma chave ao invés de um índice. Uma chave pode ser qualquer string ou número. A sintaxe para definir um dicionário vazio é:
```
>>> {}
{}
```
Isso mostra que você acabou de criar um dicionário vazio. Hurra!

Agora, tente escrever o seguinte comando (tente substituir com as suas próprias informações também):
```
>>> participante = {'nome': 'Ola', 'pais': 'Polonia', 'numeros_favoritos': [7, 42, 92]}
```
Com esse comando, você acabou de criar uma variável chamada `participante` com três pares de chave-valor:
 - A chave `nome` aponta para o valor `'Ola'` (um objeto `string`),
 - `pais` aponta para `'Polonia'` (outra `string`),
 - e `numeros_favoritos` apontam para `[7, 42, 92]` (uma `lista` com três números nela).
Você pode checar o conteúdo de chaves individuais com a sintaxe:
```
>>> print(participante['nome'])
Ola
```
Veja, que dicionário é similar a uma lista. Mas você não precisa lembrar o índice - apenas o nome.

O que acontece se pedirmos ao Python o valor de uma chave que não existe?
```
>>> participante['idade']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'idade'
```
Olha, outro erro! Esse é um **KeyError**. Python é bastante prestativo e te diz que a chave `'idade'` não existe nesse dicionário.

Quando usar um dicionário ou uma lista?
 - Você precisa de uma sequência ordenada de itens? Use uma lista.
 - Você precisa associar valores com chaves, assim você pode procurá-los eficientemente (pela chave) mais tarde? Use um dicionário.
Dicionários, como listas, são *mutáveis*, ou seja, que podem ser mudados depois que são criados. Você pode adicionar novos pares de chave/valor para o dicionário após sua criação, como:
```
>>> participante['linguagem_favorita'] = 'Python'
```
Como as listas, usar o método `len()` em dicionários retorna o número de pares chave-valor do dicionário. Vá em frente e digite o comando:
```
>>> len(participante)
4
```
Você pode usar o comando `pop()` para deletar um item no dicionario. Digamos, se você quer excluir a entrada correspondente a chave `'numeros_favoritos'`, basta digitar o seguinte comando:
```
>>> participante.pop('numeros_favoritos')
>>> participante
{'pais': 'Polonia', 'linguagem_favorita': 'Python', 'nome': 'Ola'}
```
Como você pode ver no retorno, o par chave-valor correspondente à chave `'numeros_favoritos'` foi excluído.

Além disso você pode mudar o valor associado com uma chave já criada no dicionário. Digite:
```
>>> participante['pais'] = 'Alemanha'
>>> participante
{'pais': 'Alemanha', 'linguagem_favorita': 'Python', 'nome': 'Ola'}
```
Como você pode ver, o valor da chave `'pais'` foi alterado de `'Polonia'` para `'Alemanha'`.

### Tuplas
Há tipo em Python chamado tupla (tuple) que é similar a uma lista exceto por ele ser imutável. Sintaticamente, uma tupla é uma lista de valores separados por vírgulas:
```
>>> tupla = 'a', 'b', 'c', 'd', 'e'
```
Embora não seja necessário, é convencional colocar tuplas entre parênteses:
```
>>> tupla = ('a', 'b', 'c', 'd', 'e')
```
Para criar uma tupla com um único elemento, temos que incluir uma vírgula final:
```
>>> t1 = ('a',)
>>> type(t1)
<type 'tuple'>
```
Sem a vírgula, Python entende ('a') como uma string entre parênteses:
```
>>> t2 = ('a')
>>> type(t2)
<type 'string'>
```
Questões de sintaxe de lado, as operações em tuplas são as mesmas operações das listas. O operador índice seleciona um elemento da tupla.
```
>>> tupla = ('a', 'b', 'c', 'd', 'e')
>>> tupla[0]
'a'
```
E o operador slice (fatia) seleciona uma “faixa” (range) de elementos.
```
>>> tupla[1:3]
('b', 'c')
```
Mas se tentarmos modificar um dos elementos de uma tupla, teremos um erro:
```
>>> tupla[0] = 'A'
TypeError: object doesn't support item assignment
```
Naturalmente, mesmo que não possamos modificar os elementos de uma tupla, podemos substituí-la por uma tupla diferente:

```
>>> tupla = ('A',) + tupla[1:]
>>> tupla
('A', 'b', 'c', 'd', 'e')
```

### Operadores lógicos
```
>>> 5 > 2
True
>>> 3 < 1
False
>>> 5 > 2 * 2
True
>>> 1 == 1
True
>>> 5 != 2
True
```
Demos ao Python alguns números para comparar. Como você pode ver, Python pode comparar não só números mas também resultados de métodos. Legal, hein?

Você está se perguntando por que colocamos dois sinais de igual `==` lado a lado para comparar se os números são iguais? Nós usamos um único `=` para atribuir valores a variáveis. Você sempre, sempre precisa colocar dois `==` se quiser verificar se as coisas são iguais. Também é possível afirmar que as coisas são desiguais entre si. Para isso, usamos o símbolo `!=`, conforme mostrado no exemplo acima.

Dê ao Python mais duas tarefas:
```
>>> 6 >= 12 / 2
True
>>> 3 <= 2
False
```

x `>` y significa: x é maior que y
x `<` y significa: x é menor que y
x `<=` y significa: x é menor ou igual a y
x `>=` y significa: x é maior ou igual a y
Fantástico! Quer mais? Tente isto:
```
>>> 6 > 2 and 2 < 3
True
>>> 3 > 2 and 2 < 1
False
>>> 3 > 2 or 2 < 1
True
```
Você pode dar ao Python quantos números você quiser comparar, e ele vai te dar uma resposta!
 - **and** - se você usar o operador and, ambas as comparações terão que ser verdadeiras para que todo o comando seja verdadeiro
 - **or** - se você usar o operador or, apenas uma das comparações precisa ser verdadeira para que o comando todo seja verdadeiro

Já ouviu a expressão "comparar maçãs com laranjas"? Vamos tentar o equivalente em Python:
```
>>> 1 > 'django'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unorderable types: int() > str()
```
Aqui vemos que assim como na expressão, Python não é capaz de comparar um número (`int`) e uma string (`str`). Em vez disso, ele mostrou um **TypeError** e nos disse que os dois tipos não podem ser comparados juntos.

### Booleano
Acidentalmente, você aprendeu sobre um novo tipo de objeto em Python. É chamado de **booleano** -- e provavelmente o tipo mais fácil que existe.

Existem apenas dois objetos booleanos: - True (verdadeiro) - False (falso)

Mas para o Python entender isso, você precisa sempre escrever True (primeira letra maiúscula, com o resto das letras em minúsculo). **true**, **TRUE**, **tRUE** **não vai funcionar** -- só **True** é correto. (O mesmo se aplica ao **False**, claro.)

Booleanos podem ser variáveis também! Veja:
```
>>> a = True
>>> a
True
```
Você também pode fazer desse jeito:
```
>>> a = 2 > 5
>>> a
False
```

### if...elif...else
Crie um arquivo com `python_intro.py` e insira isto:
```python
if 3 > 2:
```
Salve e execute com o seguinte comando:
```
$ python python_intro.py
```
```
File "python_intro.py", line 2
         ^
SyntaxError: unexpected EOF while parsing
```
Python espera que nós forneçamos mais instruções que serão supostamente executadas caso a condição `3 > 2` venha a ser verdadeira (ou `True` nesse caso). Vamos tentar fazer o Python imprimir "It works!". Altere o seu código no seu arquivo **python_intro.py** para isto:
```python
if 3 > 2:
    print('It works!')
```
Você percebeu que identamos a próxima linha com 4 espaços? Precisamos fazer isso para que o Python saiba qual código será executado se o resultado for `True`. Você pode fazer com 1 espaço, mas quase todos os programadores Python fazem com 4 para deixar as coisas arrumadas. Um único tab também vai contar como 4 espaços.

Salvá-lo e execute novamente:
```
$ python python_intro.py
It works!
```
#### E se não?
Nos exemplos anteriores, o código foi executado somente quando as condições eram verdade. Mas o Python também tem instruções `elif` e `else`:
```python
if 5 > 2:
    print('5 é realmente maior que 2')
else:
    print('5 não é maior que 2')
```
Quando for executado irá imprimir:
```
$ python python_intro.py
5 é realmente maior que 2
```
Se 2 for um número maior do que 5, então o segundo comando será executado. Fácil, né? Vamos ver como funciona o `elif`:
```python
name = 'Sonja'
if name == 'Ola':
    print('Hey Ola!')
elif name == 'Sonja':
    print('Hey Sonja!')
else:
    print('Hey anonymous!')
```
e executado:
```
$ python python_intro.py
Hey Sonja!
```

### Suas próprias funções!
Uma função é uma sequência de instruções que o Python deve executar. Cada função em Python começa com a palavra-chave `def`, seguido de um nome para a função e opcionalmente uma lista de parâmetros. Vamos começar com uma função simples. Substitua o código no **python_intro.py** com o seguinte:
```python
def hi():
    print('Hi there!')
    print('How are you?')

hi()
```
Ok, nossa primeira função está pronta!

Você pode se perguntar por que escrevemos o nome da função na parte inferior do arquivo. Isto é porque Python lê o arquivo e executa de cima para baixo. Então, para usar a nossa função, temos de escrevê-lo na parte inferior.

Vamos executa-lo agora e ver o que acontece:
```
$ python python_intro.py
Hi there!
How are you?
```
Isso foi fácil! Vamos construir nossa primeira função com parâmetros. Usaremos o exemplo anterior - uma função que diz 'hi' para quem o executa - com um name:
```python
def hi(name):
```
Como você pode ver, agora demos um parâmetro chamado `name` para nossa função:
```python
def hi(name):
    if name == 'Ola':
        print('Hi Ola!')
    elif name == 'Sonja':
        print('Hi Sonja!')
    else:
        print('Hi anonymous!')

hi()
```
Como você pode ver, nós precisamos colocar dois tabs antes da função `print`, porque `if` precisa saber o que deve acontecer quando a condição for atendida. Vamos ver como isso funciona agora:
```
$ python python_intro.py
Traceback (most recent call last):
File "python_intro.py", line 10, in <module>
  hi()
TypeError: hi() missing 1 required positional argument: 'name'
```
Oops, um erro. Felizmente, Python nos fornece uma mensagem de erro bastante útil. Ela diz que a função `hi()` (aquela que declaramos) tem um argumento obrigatório (chamado `name`) e que nós esquecemos de passá-lo ao chamar a função. Vamos corrigi-lo na parte inferior do arquivo:
```python
hi("Ola")
```
e execute novamente:
```
$ python python_intro.py
Hi Ola!
```
E se mudarmos o nome?
```python
hi("Sonja")
```
e executá-lo:
```
$ python python_intro.py
Hi Sonja!
```
Agora, o que acha que vai acontecer se você escrever outro nome lá? (Sem ser Ola ou Sonja) Experimentá-lo e ver se você está certo. Ele deve imprimir isto:
```
Hi anonymous!
```
Isto é incrível, não? Dessa maneira você não precisa se repetir (DRY - don't repeat yourself, ou em português, não se repita) cada vez que for mudar o nome da pessoa que a função pretende cumprimentar. E é exatamente por isso que precisamos de funções - você nunca quer repetir seu código!

Vamos fazer algo mais inteligente..--existem mais que dois nomes, e escrever uma condição para cada um seria difícil, certo?
```python
def hi(name):
    print('Hi ' + name + '!')

hi("Rachel")
```
Vamos chamar o código agora:
```
$ python python_intro.py
Hi Rachel!
```
### Laços
Como mencionamos, os programadores são preguiçosos, não gostam de repetir as mesmas coisas. Programação fala sobre como automatizar as coisas, então não queremos cumprimentar cada pessoa pelo seu nome manualmente, certo? É aí onde os laços vem a calhar.

Ainda se lembra das listas? Vamos fazer uma lista de garotas:
```python
girls = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'You']
```
Queremos cumprimentar todas elas pelos seus nomes. Temos a função hi para fazer isso, então vamos usá-la em um loop:
#### for
```python
for name in girls:
```
O `for` se comporta da mesma forma que o `if`, o código abaixo esses dois precisam ser recuados quatro espaços.

Aqui está o código completo que será salvo no arquivo:
```python
def hi(name):
    print('Hi ' + name + '!')

girls = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'You']
for name in girls:
    hi(name)
    print('Next girl')
```
e quando executá-lo:
```
$ python python_intro.py
Hi Rachel!
Next girl
Hi Monica!
Next girl
Hi Phoebe!
Next girl
Hi Ola!
Next girl
Hi You!
Next girl
```
Como você pode ver, tudo o que você vai colocar dentro de uma instrução `for` com espaço será repetido para cada elemento da lista `girls`.

Você também pode usar o `for` em números usando a função `range`:
```python
for i in range(1, 6):
    print(i)
```
Que iria imprimir:
```
1
2
3
4
5
```
`range` é uma função que cria uma lista de números que se seguem um após o outro (esses números são dados por você como parâmetros).

Note que o segundo desses dois números não está incluído na lista que o Python mostrou (em `range(1, 6)`, conta de 1 a 5, mas o 6 não é incluído).

#### while
O `while` é um comando que manda um bloco de código ser executado enquanto uma condição não for satisfeita. Assim, permite que sejam criados loops de execução.

O `while` é um comando muito útil, mas pode ser perigoso, pois se não tratarmos corretamente o critério de parada, o laço pode não ter fim, e o programa não faz o que deveria.

Vamos ver então um exemplo:
```python
x = 100
while x > 0:
    print "x > 0"
    x = x - 1
```
Neste código, será mostrada a mensagem `x > 0` até que `x` seja igual a zero. Quando o valor de `x` passar para `0`, a verificação `x > 0` retornará falso, o programa sai do laço.

## Introdução ao Django
### O que é Django
Django é um framework para perfeccionistas com prazos. É gratuito e de código aberto para a criação de aplicações web, escrito em Python. É um framework web, ou seja, é um conjunto de componentes que ajuda a desenvolver sites de forma mais rápida e mais fácil.

Veja, quando você está construindo um site, você sempre precisa um conjunto similar de componentes: uma maneira de lidar com a autenticação do usuário (inscrever-se, realizar login, realizar logout), painel de gerenciamento para o seu site, formulários, upload de arquivos, etc.

### Fluxo de requisição no Django
<p align="center">
  <img src="http://uilian.com/presentations/django/django-intro/images/djangoflow.png">
</p>

Quando chega uma requisição para o servidor web ela é passada para o Django que tenta descobrir do que ela se trata. Primeiro ele pega um endereço web e tenta descobrir o que fazer. Essa parte é feita pelo urlresolver do Django. (Note que o endereço de um site se chama URL - Uniform Resource Locator, em português Localizador de Recursos Uniforme, dessa forma o nome urlresolver, ou resolvedor de urls, faz sentido). Isso não é muito inteligente - leva à uma lista de padrões e tenta corresponder a URL. O Django verifica padrões de cima para baixo e se algo é correspondido, passa a solicitação para a função associada (que é chamada view).

Imagine um carteiro com uma carta. Ela está andando pela rua e verifica cada número de casa com a que está na carta. Se ele corresponder, ela coloca a carta lá. É assim que funciona o urlresolver!

Todas as coisas interessantes são feitas dentro da view: podemos dar uma olhada no banco de dados para procurar algumas informações. Talvez o usuário queira mudar algo nos dados? Como uma carta dizendo: "Por favor mude a descrição do meu emprego." - a view checa se você tem permissão para fazer isso e então atualiza a descrição do emprego pra você, enviando em seguida uma mensagem: "Feito!". Então a view gera uma resposta e o Django pode enviá-la para o navegador do cliente.








# NAP - Notações Aleatórias de Progresso

Protótipo de linguagem de marcação pausada para registros diários não consecutivos de progresso sem obrigatoriedade de posicionamento cronológico.

A ferramenta de conversão da notação para texto comum está disponível em: [nap-parser](https://thethales.github.io/nap-parser/)


**Versão:** *0.3_beta*



**Pontos principais:**

- Atribuição associativa de valores e chaves
- A informação é codificada em pares, nomeadamente, 1º e 2º membro. Separadados por um caracters reservado chamado de *Operador*
- Escrita condensada

*Isto é um rascunho*

Backlog
- Definição clara de termos para representação da chave e valor; e parser
- Definição clara de termos para representação do termo parser



## Terminologia

|Termo          |Simbolo    |Descrição                                              |
|---------------|-----------|-------------------------------------------------------|
|chave          |           |Qualquer valor com peso classificador. e.g. Dia, Peso, Vaso|
|valor          |           |Qualquer dado representativo. e.g. *Hoje está nublado* |
|delimitador    |```:```    |Separador entre chave e valor                          |
|atribuição     |```:=```   |Ver [Atribuição](####Operador-de-Atribuição)           |
|sufixo         |```.```    |Identifica um sufixo para o valor ou chave  e.g. CC.1  |
|prefixo        |```.```    |Identifica um sufixo para o valor ou chave. e.g. 1<span>.CC  |
|palavras de atalho|            |Refere-se a chaves abreviadas por meio do uso do operador de [Atribuição](####Operador-de-Atribuição)|


### Caracteres Reservados

Os seguintes caracteres são reservados para operação das notações, e portanto não podem ser utilizados: ``` :    :=    . ```
## Estrutura

### Marcadores

São códigos customizáveis, representativos para facilitação e aceleração de escrita. A informação (ou valor) é relacionada de maneira associativa com palavras reservadas, denonimadas chaves, que correspondem sempre ao primeiro mebro à esquerda. 
Entretanto a relação entre chave e valor não é restrita ou obrigatória. Uma chave poderá operar como valor ou vice e versa dependendo do caso.

### Operadores

Operadores são elementos ou simbolos reservados que indicam uma regra de notação. Como os delimitadores, que separam as chaves dos valores por exemplo.
#### Operador Delimitador

Ver [Terminologia](##Terminologia), delimitador
#### Operador de Atribuição

As chaves são nomeadas automaticamente mediante sua escrita, entretanto a partir de um operador reservado pode-se atribuir uma abreviação que funcionará como um atalho de escrita; i.e., um código. 
```A partir daqui referido como *palavra atalho*.```

No momento da transcrição as palavras atalho serão trocadas pelos seus valores equivalentes.
Essas atribuições poderão ser realizadas à qualquer momento no registro diário passando à ser aplicada globalmente após enunciação.

O operador atribuidor é representado pelos caracteres ```:=```, conforme:

```
CC:=Cacto
plantio:=Plantio da planta
```

```
CC:=Cacto
pl:=Plantio da planta
```
**Uso**


*Raw*
```
CC01:pl:realizado em terra vegetal obitida do pomar
```

*Parsed*
```
20210611 -> 13H
Cacto-> 01
Plantio da Planta -> realizado em terra vegetal obtida do pomar
```



#### Operador de Sufixo

Identifica um sufixo para o valor ou chave.
É utilizado junto das *palavras de atalho* para aceleração da escrita. Através desse recurso é possível identificar uma série de mesmos elementos com varições deterministiscas através de um sufixo final. 

*Raw*
```
CC.01:CC.02:CC.03:Regados hoje às 15h07
CC:=Cacto
```

*Parsed*
```
Cacto.01 Cacto.02
Cacto.03 -> Regados hoje às 15h07
```


#### Operador de Conjuntos (Listas)

A composição de listas é suportada através do uso da vírgula: ```,```
podendo ser aplicada em qualquer membro.

**Uso**


*Raw*
```

CC.01,CC.02,CC.03,AL.01:pl:realizado em terra vegetal obitida do pomar
```

*Parsed*
```

```








~~### Elemento Sequenciador~~

~~O uso de dois separadores consecutivos, i.e.  ```::```, indica um elemento sequenciador preferencial, como uma data ou um sistema de numeração. e.g.~~

~~20210611:13H::CC.01:plantio:realizado em terra vegetal obitida do pomar
001::CC.01:plantio:realizado em terra vegetal obitida do pomar~~





~~### Agrupamento~~



~~*Discussão sobre o Agrupamento*~~

~~Enquanto o agrupamento fica a quesito de operação do parser, da-se as opções:~~
~~-Pode ser realizado por sinalização no texto~~
~~-Pode ser realizado por similaridade/contagem de caracteres em busca de padrões ~similares a escolha do usuário~~







# Protótipo de Linguagem de Marcação para Registros Diários de Progresso

*Isto é um rascunho*

## Marcadores

São códigos customizáveis, representativos para facilitação e aceleração de escrita. A informação (ou valor) é relacionada de maneira associatia com palavras reservadas, denonimadas chaves, entretanto a relação entre chave e valor não é restrita ou obrigatória. Uma chave poderá operar como valor ou vice e versa dependendo do caso.

## Estrutura

**Pontos principais:**
- Atribuição associativa de valores e chaves
- Tolerante a Caixa Alta/Caixa Baixa
- Leitura da String é realiza em pares


**Atribuição**
```
CC:=Cacto
plantio:=Plantio da planta
```
**Uso**


*Raw*
```
20210611:13H:CC:01:plantio:realizado em terra vegetal obitida do pomar
```

*Parsed*
```
20210611 -> 13H
Cacto-> 01
Plantio da Planta -> realizado em terra vegetal obtida do pomar
```






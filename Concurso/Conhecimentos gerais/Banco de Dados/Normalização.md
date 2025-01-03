### **Primeira Forma Normal (1FN)**

**Definição:**  
Um banco de dados está na 1FN quando todas as suas tabelas têm as seguintes características:

1. **Eliminação de atributos multivalorados**: Cada coluna deve conter apenas um único valor (atômico) por célula.
2. **Presença de uma chave primária**: Deve existir um identificador único para cada linha.

**Objetivo:**  
Eliminar valores repetidos ou listas dentro de uma célula, garantindo que os dados estejam organizados em tabelas bem definidas.

### **Segunda Forma Normal (2FN)**

**Definição:**  
Um banco de dados está na 2FN quando:

1. Ele já está na **1FN**.
2. Todos os atributos não-chave dependem **unicamente** da chave primária.

**Objetivo:**  
Remover dependências parciais, ou seja, quando um atributo depende apenas de parte da chave primária em tabelas com chaves compostas.

### **Terceira Forma Normal (3FN)**

**Definição:**  
Um banco de dados está na 3FN quando:

1. Ele já está na **2FN**.
2. Todos os atributos não-chave são **independentes entre si** e dependem somente da chave primária.

**Objetivo:**  
Remover dependências transitivas, ou seja, quando um atributo depende de outro atributo não-chave.
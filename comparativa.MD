# Máquina de Turing Reconocedora/Aceptadora vs. Máquina de Turing Calculadora

## Definiciones

**MT reconocedora / aceptadora:** dado un lenguaje L, la máquina recibe una cadena w en la cinta y su única salida posible es *aceptar* o *no aceptar* (rechazar o no detenerse), según si w pertenece o no a L. Se usa para **clasificar lenguajes** (decidir a qué nivel de la jerarquía de Chomsky pertenecen).

**MT calculadora (o transductora):** dada una función f, la máquina recibe una entrada w en la cinta y, si se detiene, deja escrito el resultado f(w) en la cinta. No le interesa "aceptar o rechazar", sino **transformar la entrada en una salida**. Se usa para definir qué funciones son computables (Tesis de Church-Turing).

## Cuadro comparativo

| Aspecto | MT reconocedora / aceptadora | MT calculadora (función) |
|---|---|---|
| Objetivo | Decidir si w ∈ L | Calcular f(w) y dejar el resultado en la cinta |
| Salida | Acepta / No acepta (llega o no a un estado final) | El contenido final de la cinta es el resultado |
| Detención | Puede aceptar, rechazar, o no detenerse nunca (lenguajes recursivamente enumerables) | Debe detenerse siempre que f esté definida para esa entrada, dejando el resultado |
| Relación con la jerarquía de Chomsky | Reconoce exactamente los lenguajes recursivamente enumerables (Tipo 0); permite clasificar lenguajes según qué autómata más débil también los reconoce (regular, independiente del contexto, etc.) | No clasifica lenguajes; define qué funciones son "computables" |
| Uso del estado final | Alcanza con un solo estado final para marcar aceptación (o varios, es indistinto) | El estado final marca "terminé de calcular"; lo relevante es el contenido de la cinta, no el estado |
| Ejemplo de este trabajo | MT para el lenguaje regular {w ∈ {a,b}\* : cantidad par de a's} y MT para el lenguaje independiente del contexto {w#w^R : w ∈ {0,1}\*} — ambas solo dicen sí/no | MT "Duplicar Unos" — transforma la entrada en otra cadena sobre la cinta |

## Conclusión

La diferencia clave es el **propósito**: una MT reconocedora se usa como herramienta teórica para estudiar y clasificar lenguajes (qué tan "difícil" es reconocer una cadena de ese lenguaje), mientras que una MT calculadora se usa como modelo de **computación general**, es decir, para definir formalmente qué significa que un problema sea "calculable" por un algoritmo.
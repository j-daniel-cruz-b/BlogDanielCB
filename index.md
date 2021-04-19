# Lenguajes y Automatas I
**by Daniel Cruz**

## Unidad 1. Introducción a la Teoría de Lenguajes Formales.
1. Alfabeto.
2. Cadenas.
3. Lenguajes, tipos y herramientas.
4. Estructura de un traductor.

+ **Aplicaiones:**
1. [appCodificaciónGUI](https://github.com/moonligth-cb/appCodificacionGUI.git) 

```markdown
Sintaxis importante de esta aplicación:

# Elaborada en Qt
## C++ [visual]

Clases.
Definición de la clase [Encryption]
#ifndef ENCRYPTION_H
#define ENCRYPTION_H

#include <cstring>
#include <string>
#include <stdio.h>

class Encryption
{
public:
    Encryption();

    //Arreglo para el nuevo texto
    char *newCode;

    //Metodos
    void encode(char msj[], int n);
    void decode(char msj[], int n);
    int charToAscii(char c);
    char asciiToChar(int c);
};

#endif // ENCRYPTION_H
```
**Uno de los metodos a resonar es** `int charToAscii(char c);` debido a que gracias a la faciliad de convertir un caracte a codigo _ASCII_.

5. Fases de un compilador

## Unidad 2. Expresiones Regulares. 
1. Definición formal de una ER.
2. Diseño de ER.
3. Aplicaciones en problemas reales. 

## Contacto

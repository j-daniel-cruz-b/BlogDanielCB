# Lenguajes y Automatas I
> **by Daniel Cruz**

## Unidad 1. Introducción a la Teoría de Lenguajes Formales.
1. Alfabeto.
2. Cadenas.
3. Lenguajes, tipos y herramientas.
4. Estructura de un traductor.
5. Fases de un compilador

### Tema 1. Alfabeto.
+ **Aplicaiones:**
1. [appCopiarArchivoConsola](https://github.com/moonligth-cb/appCopiarArchivoConsola.git)

```c++
Sintaxis importante de esta aplicación:

# Elaborada en Qt
# C++ [consola]

Main.
Aquí se elaboró con un path estatico.

#include <iostream>
#include <cstring>
#include <string>
#include <stdio.h>

using namespace std;

int main()
{
    //Punteros de la estructura FILE, para el archivo de entrada (origen) y salida (destino)
    FILE *fe, *fs;
    unsigned char buffer[2048]; // Buffer de 2 Kbytes
    int bytesLeidos;

    // Constante  para la dirección que se genera por default de los archivos que van a utilizar.
    char *dir = "D:/DOCUMENTOS/ITL/6TO SEMESTRE/LyA1/";
    // Constante para la extensión (txt) para usar solamente archivos de texto.
    char *ext = ".txt";

    // Declarar e inicializar los variables que tendrán el PATH, NOMBRE y EXTENSIÓN de los archivos que ingresará el usuario
    char origen[255] = "";
    char destino[255] = "";

    // Declarar los variables que tendrán solamente los nombres de los archivos que ingresará el usuario
    char nombreOrigen[25];
    char nombreDestino[25];

    // Ingresar nombre del archivo de origen
    cout << "Ingrese el nombre del archivo de origen (Este archivo debe de existir): ";
    cin >> nombreOrigen;

    // Concatenar la dirección y extensión del archivo de origen
    // Nota -> El archivo de origen debe existir
    strcat(origen, dir);
    strcat(origen, nombreOrigen);
    strcat(origen, ext);

    cout << origen << "\n";

    // Se bedrá abrir el archivo de origen en lectura y binario el método fopen(), mandando como parámetros el nombre
    // y el modo "rb" ( lectura y binario)
    // el método fopen() regresa una estructura FILE que será apuntada por fe

    fe = fopen(origen, "rb");

    if(!fe) {
        // comprobar que el archivo existe, si no existe se muestra un mensaje de error y se regresa un 1
        printf("El fichero %s no existe o no puede ser abierto.\n", origen);
        return 1;
    }

    // Ingresar nombre del archivo de destino
    cout << "Ingrese el nombre del archivo de destino(Este archivo se va a crear): ";
    cin >> nombreDestino;

    // Concatenar la dirección y extensión del archivo de destino
    // Nota -> El archivo de destino, se va a crear
    strcat(destino, dir);
    strcat(destino, nombreDestino);
    strcat(destino, ext);

    // Crear o sobreescribir el fichero de salida en binario también con el método fopen(), mandando
    //nombre y modo (w = write y b = binario)

    fs = fopen(destino, "wb");

    if(!fs) {
        // comprobar que el archivo existe, si no existe se muestra un mensaje de error y se regresa un 1
        printf("El fichero %s no puede ser creado.\n", destino);
        fclose(fe);
        return 1;
    }
    // Bucle de copia:
    // Una vez creados loa archivos, se hace la copia
    // fread = regresa el número de registros/bytes leídos
    // se define bytesLeidos con el número de registros leídos del archivo de entrada u origen hasta 2048
    // se escriben en el archivo de salida o destino todos los bytes leídos
    while((bytesLeidos = fread(buffer, 1, 2048, fe)))
        fwrite(buffer, 1, bytesLeidos, fs);
    // Cerrar ficheros:
    fclose(fe);
    fclose(fs);

    // se termina la copia y se regresa un 0
    cout << "\nTodo Correcto, el archivo fue copiado!\n";
    return 0;
}
```

+ **Recursos Didacticos:**

### Tema 2. Cadenas.
+ **Aplicaiones:**
+ **Recursos Didacticos:**

### Tema 3. Lenguajes, tipos y herramientas.
+ **Aplicaiones:**
+ **Recursos Didacticos:**

### Tema 4. Estructura de un traductor.

+ **Aplicaiones:**
1. [appCodificaciónGUI](https://github.com/moonligth-cb/appCodificacionGUI.git) 

```c++
Sintaxis importante de esta aplicación:

# Elaborada en Qt
# C++ [visual]

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

### Tema 5. Fases de un compilador
+ **Aplicaiones:**
+ **Recursos Didacticos:**

## Unidad 2. Expresiones Regulares. 
1. Definición formal de una ER.
2. Diseño de ER.
3. Aplicaciones en problemas reales. 

### Tema 1. Definición formal de una ER.
+ **Aplicaiones:**
+ **Recursos Didacticos:**

### Tema 2. Diseño de ER.
+ **Aplicaiones:**
1. [appExpRegLeer](https://github.com/moonligth-cb/appExpReg1.git)

```java
Sintaxis importante de esta aplicación:

# Elaborada en NetBeans
# Java [visual]

## Alistar una pantalla:
public void arbol() {
    this.label1.setText("Arbol");
    this.label2.setText("Maíz");
    this.label3.setText("Brocolí");
    this.labelImg.setIcon(new ImageIcon("src/images/bigs/arbol.png"));
    this.panelArbol.setVisible(true);
    this.btnSiguiente.setEnabled(false);
    this.labelError.setVisible(false);
    this.labelCorrecto.setVisible(false);
}

## Revisar una palabra:
private void arbolRevisar() {
    String cadena = this.textArbol.getText();
    String regExpString = "[a-zA-Z]{5}";
    Pattern pStr = Pattern.compile(regExpString);
    Matcher mStr = pStr.matcher(cadena);
    if (mStr.matches()) {
        cadena = cadena.toLowerCase().strip();
        if(!cadena.equals("arbol")){
            this.labelError.setVisible(true);
            this.labelError.setText("No es correcto :c");
        } else {
            this.btnSiguiente.setEnabled(true);
            this.labelCorrecto.setVisible(true);
            this.labelCorrecto.setText("Muy Bien!!");
            this.textArbol.setEnabled(false);
        }
    } else {
        this.labelError.setVisible(true);
        this.labelError.setText("Faltan letras :c");
    }
}

## Constructor del main menu:
public MainMenu(String nombreUsuario) {
    initComponents();
    getContentPane().setBackground(new Color(88, 238, 252));
    NOMBRE_USUARIO = nombreUsuario;
    if (NOMBRE_USUARIO.length() >= 10) {
        this.jLabel2.setFont(new Font("Comics Sans MS", 1, 30));
    }
    this.jLabel2.setText("Hola, " + NOMBRE_USUARIO + " Bienvenida(o) a [CUDI].");
    Image icon = new ImageIcon(getClass().getResource("../images/logo.png")).getImage();
    setIconImage(icon);
}
```

+ **Recursos Didacticos:**

### Tema 3. Aplicaciones en problemas reales. 
+ **Aplicaiones:**
1. [appValidacionesSencillas](https://github.com/moonligth-cb/appExpReg2.git)

```java
Sintaxis importante de esta aplicación:

# Elaborada en NetBeans
# Java [visual]

## Botón que evalua para ver si el NC es correcto:
private void btnValidarActionPerformed(java.awt.event.ActionEvent evt) {                                           
    String nc = this.textNC.getText();
    String regExpString = "^([1-2])([0-9])13([0-9]){4}";
    Pattern pStr = Pattern.compile(regExpString);
    Matcher mStr = pStr.matcher(nc);
    if (mStr.matches()) {
            this.labelError.setVisible(false);
            this.labelCorrecto.setVisible(true);
    } else {
        this.labelError.setVisible(true);
        this.labelCorrecto.setVisible(false);
    }
        
}   

```

+ **Recursos Didacticos:**


## Contacto.

![image](https://estaticos-cdn.elperiodico.com/clip/aeb3d323-7bd6-42e9-90c5-18878cac5a9a_alta-libre-aspect-ratio_default_0.jpg)
> **Autor:** Jaime Daniel Cruz Bustamante.

> **Correo Electronico:** <jaime.dcb@hotmail.com>

> **Numero Telefonico:** 6371149255


> **Tecnologíco Nacional de Mexico Campus La Laguna**


| Syntax | Description |
| ----------- | ----------- |
| Header | Title |
| Paragraph | Text |


Strikethrough	~~The world is flat.~~


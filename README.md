# Programación en C#

## Variables:

```csharp
int -> Número entero de 32 bits. Todo número que no tenga coma. Permite negativos.
Mínimo: -2.147.483.648         Máximo: +2.147.483.647         Peso: 4 bytes

float -> Número con decimales. Permite negativos.
        Mínimo: -3.4 × 10^38                 Máximo: +3.4 × 10^38                Peso: 4 bytes

char -> Guarda caracteres como letras, números o signos. Se asigna usando comillas simples (ej: char a = ‘$’).
        Peso: 2 bytes


bool -> Almacena verdadero o falso, true o false.
        Peso: 1 byte


string -> Cadena de caracteres. Se asigna usando comillas dobles (ej: string a = "hola").
        Peso: Variado. Siendo simplistas podríamos pensar que son 2 bytes por letra (char)


double -> Número con decimales. Tiene el doble de la precisión en decimales que el float. Permite negativos.
        Mínimo: -1.7976931348623157E+308        Máximo: 1.7976931348623157E+308 Peso: 8 bytes


long -> Número entero de 64 bits. Permite negativos.
        Mínimo: -9.223.372.036.854.775.808         Máximo: 9.223.372.036.854.775.807   Peso: 8 bytes


short -> Número entero de 16 bits. Permite negativos.
        Mínimo: -32.768                         Máximo: 32.767        Peso: 2 bytes


byte -> Número entero de 8 bits. No permite negativos.
        Mínimo: 0                                Máximo: 255                Peso: 1 byte


sbyte -> Igual que el byte, pero admite negativos. La ‘S’ es de Signed (con signo).
        Mínimo: -128                                 Máximo: 127                 Peso: 1 byte


uint -> Igual que el int, pero no admite negativos. La ‘U’ es de Unsigned (sin signo).
        Mínimo: 0                                Máximo: 4.394.967.395        Peso: 4 bytes


ushort -> Igual que el short, pero no admite negativos.
        Mínimo: 0                                 Máximo: 65535        Peso: 2 bytes


ulong -> Igual que el long, pero no admite negativos.
        Mínimo: 0                        Máximo: 18446744073709551615        Peso: 8 bytes
```

### Ejemplos:

```csharp
public static void Main()
{
	int a = 15;
	float b = 5.4f;
	char c = ‘#’;
	bool d = true;
	string e = "Marcos";
}
```

## Constantes:

También existen las constantes. Se declaran con la palabra reservada const y se asignan en la misma línea en la que se declaran. Su valor no puede cambiar.

```csharp
public static void Main()
{
	const float gravedad = 9.81f;

	gravedad = 3.2f //Esto dará un error. Las constantes no pueden cambiar su valor.
}
```

## Operadores

### Operadores Matemáticos:

- Suma ---> +
- Resta ---> -
- Multiplicación ---> *
- División ---> /
- Resto ---> %


### Ejemplos:

```csharp
public static void Main()
{
	int a = 7;
	int b = 4;
	int c = a + b;
	int d = a -b;
	int e = a * b;
	int f = a / b;
	int g = a % b;
}
```

## Operadores de Asignación:

Estos operadores sirven para asignar un valor a una variable. Siempre la variable va del lado izquierdo y el valor del derecho.

- Asignación Simple ---> =
- Suma y asignación ---> +=
- Resta y asignación ---> -=
- Multiplicación y asignación ---> *=
- División y asignación ---> /=
- Resto y asignación ---> %=
- Incremento en 1 ---> ++
- Decremento en 1 ---> --

### Ejemplos:

```csharp
public static void Main()
{
	int a = 15; //Asignación simple. a tendrá el valor asignado, en este caso 15.
	int b = a = 10; //Se puede asignar un mismo valor a más una variable a la vez.
	a += 10; //Se suma 10 al valor que actualmente tiene a y se le asigna el resultado
	a -= 10; //Se resta 10 al valor que actualmente tiene a y se le asigna el resultado
	a *= 10; //Se multiplica por 10 el valor que actualmente tiene a y se le asigna el resultado
	a /= 10; //Se divide por 10 el valor que actualmente tiene a y se le asigna el resultado
	a %= 10; //Se divide por 10 el valor que actualmente tiene a y se le asigna el resto
	a++; //Esto es lo mismo que poner a += 1.
	a--; //Esto es lo mismo que poner a -= 1.
}
```

## Operadores de Comparación:

Estos operadores dan como resultado de su operación un bool (true o false). Se evalúa de izquierda a derecha.

- Igual a ---> ==
- Desigual a ---> !=
- Menor que ---> <
- Mayor que ---> >
- Menor o igual que ---> <=
- Mayor o igual que ---> >=

### Ejemplos:

```csharp
public static void Main()
{
	int a = 1
	int b = 10;
	bool respuesta;
	respuesta = (a == b); //Si a es igual a b, el resultado es true, sino false.
	respuesta = (a != b); //Si a no es igual a b, el resultado es true, sino false.
	respuesta = (a < b); //Si a es menor a b, el resultado es true, sino false.
	respuesta = (a > b); //Si a es mayor a b, el resultado es true, sino false.
	respuesta = (a <= b); //Si a es menor o igual a b, el resultado es true, sino false.
	respuesta = (a >= b); //Si a es mayor o igual a b, el resultado es true, sino false.
}
```

## Operadores Lógicos:

Son también operadores de comparación que sólo funcionan con bools. Sirven para comparar comparaciones (valga la redundancia). También retornan como resultado un bool.

- Operador AND (‘y’ en inglés) ---> &&
- Operador OR (‘o’ en inglés) ---> ||
- Operador NOT (‘no’ en inglés) ---> !

### Ejemplos:

```csharp
public static void Main()
{
	int a = 15;
	int b = 10;
	bool respuesta;
	respuesta = (a < b) && (a == 9); //AND //Se deben cumplir las dos condiciones a la vez. a debe ser menor que b y ser igual a 9. Si ambas se cumplen, retorna true, sino false.
	Si una condición no se cumple, las condiciones que le siguen no se evaluarán.
	respuesta = (a < b) || (a == 9); //OR //Se debe cumplir al menos una de las condiciones. Si cualquiera de las condiciones se cumple retorna true, si ninguna se cumple retorna false.
	Si una condición se cumple, las condiciones que le siguen no se evaluarán.
	respuesta = !(a < b); //El operador NOT (! signo de exclamación) retornará al revés del resultado de la condición dada. Es decir, al agregarle el signo de exclamación antes de la condición hará que convierta el resultado en lo contrario. Si (a < b) es igual a true, !(a < b) sera igual a false y viceversa.
}
```

## Tabla de la verdad:

### OPERADOR AND (&&):

| Condición 1   | Condición 2   | Resultado		|
|:-------------:|:-------------:|:----------:	|
|TRUE			|TRUE			|TRUE			|
|FALSE			|TRUE 			|FALSE			|
|TRUE			|FALSE			|FALSE			|
|FALSE			|FALSE			|FALSE			|
	

### OPERADOR OR (||):

| Condición 1   | Condición 2   | Resultado		|
|:-------------:|:-------------:|:----------:	|
|TRUE			|TRUE			|TRUE			|
|FALSE			|TRUE 			|TRUE			|
|TRUE			|FALSE			|TRUE			|
|FALSE			|FALSE			|FALSE			|

## Condicionales

### Bloque IF(condición):

El bloque if evalúa bools dentro de sus paréntesis. Si lo que tiene dentro es igual a true, entra al bloque, sino no entra.
Un if puede ser seguido por un bloque else if o else.
El bloque else if se evalúa si el anterior bloque (que puede ser if u otro else if) obtuvó un false. Es necesario que la condición evaluada por este bloque sea igual a true para que entre al mismo, si es false no entrará.
El bloque else en cambio no evalúa nada, sino que entra sólo si el anterior bloque obtuvo como resultado false.

### Ejemplos:

```csharp
public static void Main()
{
	int a = 15;
	int b = 10;

	if(a == b)
	{
	    Console.WriteLine("a es igual a b");
	}
	else if(a < b)
	{
	    Console.WriteLine("a es menor que b");
	}
	else //Si ninguna de las anteriores es igual a true
	{
	    Console.WriteLine("a es mayor que b");
	}
}

public static void Main()
{
	int a = 15;
	int b = 10;

	if(a == b && a == 15) 
	{
	    Console.WriteLine("a y b son iguales a 15");
	}
	else if(a < b || a == 15)
	{
	    Console.WriteLine("a es menor que b o es igual a 15");
	}
	else if(!(a < b)) //Con operador NOT, si (a < b) es true, entonces es false y viceversa
	{
	    Console.WriteLine("a no es menor que b");
	}
}
```

### Bloque SWITCH(expresión)

El bloque switch evalúa si la expresión dada (la variable) es igual a alguno de los casos expuestos en el bloque. Para determinar un caso se utiliza la palabra reservada case. Si ninguno de los casos cumple se puede utilizar un caso por defecto, con la palabra reservada default. Al final de cada caso se debe cerrar con un sentencia de quiebre, con la palabra reservada break.

### Ejemplos:

```csharp
public static void Main()
{
	int a = 15;
	
	switch(a) //La expresión debe ser variable
	{
	    case 1: //Los casos deben ser constantes
	        Console.WriteLine("a es igual a 1");
	        break;
	    case 2:
	        Console.WriteLine("a es igual a 2");
	        break;
	    default:
	        Console.WriteLine("a es igual a " + a);
	        break;
	}
}
```

## Bucles:

### Bloque WHILE(condición):

El bloque while, al igual que el if, evalúa bools dentro de sus paréntesis. Si lo que tiene dentro es igual a true, entra al bloque, sino no entra. El bloque se ejecutará una y otra vez hasta que la condición dentro de sus paréntesis sean igual a false.

### Ejemplos:

```csharp
public static void Main()
{
	int a = 15;
	int b = 10;

	while(a > b) //Mientras que a sea mayor que b, ejecutará el bloque while(condición)
	{
	    a--; //Como vimos antes, esto resta 1 a lo que tiene a.
		Console.WriteLine(a);
	}
	//Entrará y restará 1 a la variable a. En el momento en que (a > b) sea igual a false, //el bloque dejará de ejecutarse. Exactamente en el momento en que a sea igual a b.
}

public static void Main()
{
	int a = 15;
	int b = 10;

	while(true) //esto es válido y es básicamente un bucle infinito.
	{
	    Console.WriteLine("SÁQUENME DE ACÁ");
	}
}

public static void Main()
{
	int a = 15;
	int b = 10;

	while(a == 15)
	{
	    //Si yo no hago nada para cambiar el resultado de la condición, sigue siendo     
		//un bucle infinito, ya que siempre será true. Se ha de tener mucho cuidado con esto.
	}
}
```

### Bloque Do-While(condición):

Una variante del bucle while. La diferencia principal radica en que el bloque while se ejecutará si y sólo si la condición que evalúa es igual a true. En cambio do-while ejecutará su bloque por lo menos una vez, luego de ejecutar la primera vez si la condición evaluada fuera igual a false no se volverá a ejecutar.

### Ejemplos:

```csharp
public static void Main()
{
	int a = 15;
	int b = 10;

	//La condición es que a sea igual a b, en un while común no entraría
	//pero en un do-while entrará al menos una vez, independientemente de la
	//condición
	do
	{
		Console.WriteLine("ENTRO UNA VEZ");
	}
	while(a == b); //Al final del while debe ir un punto y coma.
}
```

### Bloque For(asignación; condición; incremento/decremento):


El bucle for está diseñado para trabajar con una cantidad de iteraciones definida. Este bucle funciona al igual que los demás: ejecuta un bloque de código mientras una condición se cumpla.
El for consta de 3 partes ideales:
1. Asignación: Se asigna un valor a una variable. Usualmente a un int.
2. Condición: La condición que, mientras sea igual a true, hará que ejecute el bloque.
3. Incremento/Decremento: Se suma o resta al valor utilizado en la asignación. Esto suele ser la razón que hace que la condición en algún momento sea igual a false.
El bucle for es especialmente útil con los arrays.


### Ejemplos:

```csharp
public static void Main()
{
	for(int i = 1; i <= 10; i++) //Como nombre de la variable se suele usar la letra i
	{
	    Console.WriteLine("Iteracion numero: " + i); //Aprovecho el valor de i
	}
}

public static void Main()
{
	int[] array = new int[10]; //Un ejemplo con arrays. Se profundizará más adelante.

	for(int indice = 0; indice < 10; indice++) 
	{
	    array[indice] = indice; //Lleno el array con valores
	    Console.WriteLine("El indice " + indice + " contiene el valor: " + array[indice]);
	    //Muestro los valores del array por indice
	}
}
```

## Funciones:


Las funciones son bloques de código que pueden o no devolver un resultado. Independientemente de si devuelven o no un resultado, siempre ejecutarán el código que tengan adjunto. Siempre debe existir una función llamada Main() que representa el comienzo del programa.
Las funciones constan de ciertos modificadores (como puede ser public), de un tipo de dato (como puede ser int o void), de un nombre seguido de paréntesis, donde puede o no recibir parámetros.
Los parámetros son datos con los que la función puede operar. Variables, básicamente.


### Ejemplos:

```csharp
public static void Main()
{
	int a = DevolverUnNumero();
	
	Console.WriteLine(a); //a será igual a 3
}

//Devuelve un dato y no recibe nada
public static int DevolverUnNumero()
{
	return 3; //la palabra reservada ‘return’ sirve para devolver un dato por función
    		//se profundizará más adelante
}

public static void Main()
{
	Saludar(); //Mostrará "HOLA MAMA" en la consola.
}

//No devuelve nada ni recibe datos
public static void Saludar()
{
	Console.WriteLine("HOLA MAMA");
}

public static void Main()
{
    string variableDondeGuardoMiNombre = "Santiago";
	Saludar(variableDondeGuardoMiNombre); //Mostrará "HOLA Santiago"

	//Nótese que el nombre de la variable que envío a la función no tiene porque llamarse igual a la variable que la función maneja por dentro
}

//No devuelve nada y recibe un dato
public static void Saludar(string nombre)
{
	Console.Write("HOLA ");
	Console.WriteLine(nombre);
}

public static void Main()
{
	int a = SumarNumeros(10, 90);

	Console.WriteLine(a); //a será igual a 100
}

//Devuelve un dato y recibe dos datos
public static int SumarNumeros(int primerNumero, int segundoNumero)
{
	return primerNumero + segundoNumero;
}
```

## Sentencias de salto:

Las sentencias de salto son herramientas para redireccionar el flujo del programa.
Las sentencias posibles son:

### break

Esta sentencia rompe un bucle o un case del switch.

```csharp
public static void Main()
{
	for(int i = 0; i < 10; i++)
	{
	    if(i == 5)
	    {
	        Console.WriteLine("YA NO NECESITO NADA DE ESTE BUCLE");
	        break;
	    }
	}
}
```

### continue

Dentro de un bucle salta a la siguiente iteración del mismo.

```csharp
public static void Main()
{
	for(int i = 0; i < 10; i++)
	{
	    if(i == 5)
	    {
	            continue; //Si a mi me parece que el 5 no es un número groso
	                        //paso al siguiente. Lo que está después no se ejecuta.
	    }

	    Console.WriteLine("ESTE NUMERO ES GROSO: " + i);
	}
}
```

### return

Se utiliza en funciones o propiedades para retornar un valor. Si la función devuelve void entonces solo termina con la función sin devolver nada.

```csharp
public static int DevolverUnNumero()
{
	return 3;
}

public static void NoHacerNada()
{
	return; //Esta función no hace absolutamente nada.
}
```

### goto

Esta sentencia se suele considerar prohibida por muchas razones. Sin embargo en algunos pocos casos es aceptable usarla. Básicamente salta hacia una sentencia label creada en el programa. Los case del switch son sentencias label.

```csharp
public static void Main()
{
	string nombre;

	switch(nombre)
	{
	        case "Mariana": 
	                Console.WriteLine("Es buena chica, pero");
	                goto case "Roberta"; //Si el nombre es Mariana, entra a este caso
	          		//y luego salta al de Roberta también.
	        case "Roberta":
	                Console.WriteLine("es una conchuda");
	                break;
	        default:
	                Console.WriteLine("su nombre es " + nombre);
	                break;
	}

	//Si el nombre es roberta va a mostrar:

	//es una conchuda

	//Si el nombre es mariana va a mostrar:

	//Es buena chica, pero
	//es un conchuda
}
```

### throw
 
Permite arrojar excepciones que cortan el flujo de ejecución hasta que alguien "maneje" la excepción. Se profundizará sobre su uso más adelante.

## Arrays:

Los arrays son variables que guardan una cantidad finita de datos de un mismo tipo. Por ejemplo, se puede crear un array de int, char, bool, string o incluso de arrays. 
Las variables que tienen dentro no poseen nombres identificadores, sino que son accedidos mediante su número de índice. El índice comienza con el número 0, sin embargo los arrays poseen una propiedad llamada Length que representa la cantidad de índices que poseen.

### Ejemplos:

```csharp
public static void Main()
{
	int[] array = new int[4]; //Se inicializa utilizando la palabra reservada new

	array[0] = 3;
	array[1] = 5;
	array[2] = 10;
	array[3] = 12; //Absolutamente siempre el último índice es igual al Length - 1
}

public static void Main()
{
	int[] array = new int[10]; 

	for(int indice = 0; indice < array.Length; indice++) //Se accede al Length de un array mediante el punto
	{                                                        
	    array[indice] = indice; //Lleno el array con valores
	    Console.WriteLine("El indice " + indice + " contiene el valor: " + array[indice]);
	    //Muestro los valores del array por indice
	}
}
```

## Jagged Array

Un array de arrays se le conoce como Jagged Array.

### Ejemplo:

```csharp
public static void Main()
{
    int[][] jaggedArray = new int[3][4];
	//Esto es un array que contiene 3 arrays de enteros
	//A su vez, cada array de enteros tiene 4 enteros cada uno
	//Eso nos da un total de 12 enteros (3 x 4)
}
```

## Matrices

Una matriz es como un array de arrays. Tiene ciertas diferencias en la utilizacion y la performance.

### Ejemplo:

```csharp
public static void Main()
{
    int[,] miMatriz = new int[2, 3];
	//Una matriz de 2 dimensiones, de 2x3. La cantidad de ints que puede albergar es igual a 2x3 = 6.
}

public static void Main()
{
    int[,] miMatriz = new int[2, 3, 6];
	//Una matriz de 3 dimensiones, de 2x3x6. La cantidad de ints que puede albergar es igual a 2x3x6 = 36.
}
```
# Programación en C#

## Variables:

Las variables son espacios en memoria que guardan un valor un tipo determinado. A continuación un ejemplo de como declarar una variable:

```csharp
int miVariable = 3;
//[Tipo][Nombre] = [Valor]
```

La asignación de un valor es opcional en la creación de una variable. El siguiente ejemplo muestra como crear una variable a la que no se le asigna ningun valor:

```csharp
int miVariable;
```

Las variables dependen de la existencia de tipos de dato. En C#, así como en la mayoría de lenguajes de programación, nosotros podemos crear nuestros propios tipos de dato. Esto se explicará en profundidad mucho más adelante.

Por otro lado existen los llamados tipos "primitivos". Estos son tipos de datos que vienen con el lenguaje. A continuación se muestran todos los tipos de datos primitivos que existen en C#:

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

También existen las constantes. Se declaran con la palabra reservada **const** y se asignan en la misma línea en la que se declaran. Su valor no puede cambiar.

```csharp
public static void Main()
{
	const float gravedad = 9.81f;

	gravedad = 3.2f //Esto dará un error. Las constantes no pueden cambiar su valor.
}
```

## Operadores

Los operadores son símbolos que nos permiten realizar una operación particular entre datos constantes o variables. A continuación algunos de los operadores básicos de C#.

### Operadores Matemáticos:

Los operadores matemáticos nos permiten realizar operaciones matemáticas entre 2 valores numéricos. Las reglas del algebra lineal se aplican a la hora de crear cálculos combinados.

```csharp
int a = 3;
int b = 4;
int c = 5;

int resultado = a + b * c;
//Como en un calculo combinado comun se aplica la regla de separación de términos. La multiplicacion se realizará primero y luego la suma entre el resultado de la multiplicación y el valor restante. El resultado de esta operación es: 23
```

A continuación los posibles operadores:

- Suma ---> +
- Resta ---> -
- Multiplicación ---> *
- División ---> /
- Resto ---> %

### Ejemplos:

```csharp
public static void Main()
{
	int a = 7; //Defino 2 variables. "a" y "b"
	int b = 4;
	int suma = a + b; //suma 2 valores
	int resta = a -b; //resta 2 valores
	int multiplicacion = a * b; //multiplica 2 valores
	int division = a / b; //divide 2 valores. Da como resultado el cociente.
	int modulo = a % b; //divide 2 valores. Da como resultado el resto.
}
```

También es posible encontrar operadores matemáticos en otros contextos y con usos que no estén relacionados a la matemática. Por ejemplo, el operador suma (+) puede usarse con variables de tipo **string**. En este caso el operador de suma significa **concatenar**

```csharp
public static void Main()
{
	string nombre = "Santiago";
	string apellido = "Perez";

	string nombreYApellido = nombre + apellido; //concatenar
	//nombreYApellido tendrá dentro el valor: "Santiago Perez". Todo junto.
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
	a += 10; //Se suma 10 al valor que actualmente tiene a y se le asigna el resultado. Igual a poner a = a + 10;
	a -= 10; //Se resta 10 al valor que actualmente tiene a y se le asigna el resultado. Igual a poner a = a - 10;
	a *= 10; //Se multiplica por 10 el valor que actualmente tiene a y se le asigna el resultado. Igual a poner a = a * 10;
	a /= 10; //Se divide por 10 el valor que actualmente tiene a y se le asigna el resultado. Igual a poner a = a / 10;
	a %= 10; //Se divide por 10 el valor que actualmente tiene a y se le asigna el resto. Igual a poner a = a % 10;
	a++; //Esto es lo mismo que poner a += 1 ó a = a + 1;
	a--; //Esto es lo mismo que poner a -= 1 ó a = a - 1;
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
	respuesta = (a == b); //Evalua si a es igual a b, si son iguales el resultado será true, sino false.
	respuesta = (a != b); //Evalua si a no es igual a b, si no son iguales el resultado será true, sino false.
	respuesta = (a < b); //Evalua si a es menor a b, si es menor el resultado será true, sino false.
	respuesta = (a > b); //Evalua si a es mayor a b, si es mayor el resultado será true, sino false.
	respuesta = (a <= b); //Evalua si a es menor o igual a b, si es menor o igual el resultado será true, sino false.
	respuesta = (a >= b); //Evalua si a es mayor o igual a b, si es mayor o igual el resultado será true, sino false.
}
```

## Operadores Lógicos:

Son también operadores de comparación que sólo funcionan con bools. También retornan un bool como resultado.

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
	respuesta = (a < b) && (a == 9); //AND //Se deben cumplir TODAS las condiciones a la vez. a debe ser menor que b Y también igual a 9. Si TODAS se cumplen, retorna true, sino false. Si una sola condición NO se cumple, las siguientes no se evaluarán.
	Si una condición no se cumple, las condiciones que le siguen no se evaluarán.
	respuesta = (a < b) || (a == 9); //OR //Se debe cumplir AL MENOS UNA de las condiciones. Si CUALQUIERA de las condiciones se cumple retorna true, si NINGUNA se cumple retorna false. Si una condición se cumple, las condiciones que le siguen no se evaluarán.
	respuesta = !(a < b); //El operador NOT (! signo de exclamación) retornará al revés del resultado de la condición dada. Es decir, al agregarle el signo de exclamación antes de la condición hará que convierta el resultado en lo contrario. Si (a < b) es igual a true, !(a < b) sera igual a false y viceversa.
}
```

## Tabla de la verdad:

La siguiente tabla ilustra muestra, según la operación aplicada, que resultado se arroja en función de 2 valores dados.

### OPERADOR AND (&&):

![](https://github.com/Sammmte/Programacion-CSharp/blob/master/readme-resources/and-true-table.PNG)

### OPERADOR OR (||):

![](https://github.com/Sammmte/Programacion-CSharp/blob/master/readme-resources/or-true-table.PNG)

## Condicionales

### Bloque IF:

El bloque **if** evalúa bools dentro de sus paréntesis. Si lo que tiene dentro es igual a true, entra al bloque, sino no entra.
Un if puede ser seguido por un bloque **else if** o **else**.
El bloque **else if** se evalúa si el anterior bloque (que puede ser if u otro else if) obtuvó un false. Es necesario que la condición evaluada por este bloque sea igual a true para que entre al mismo, si es false no entrará.
El bloque else en cambio no evalúa nada, sino que entra sólo si el anterior bloque obtuvo como resultado false.

### Ejemplos:

```csharp
public static void Main()
{
	int a = 15;
	int b = 10;

	if(a == b) //si a es igual a b, entrará aquí
	{
	    Console.WriteLine("somos iguales");
	}
	else if(a < b) //si el anterior bloque dio false, evaluará en este si, en cambio, a es menor a b.
	{
	    Console.WriteLine("soy menor");
	}
	else //Si todas las anteriores dieron false, entrará aquí
	{
	    Console.WriteLine("soy mayor");
	}

	//Este conjunto de bloques se puede leer coloquialmente de la siguiente manera:
	//Si a es igual a b, muestra "somos iguales" en pantalla
	//Si, en cambio, a es menor a b, muestra "soy menor" en pantalla
	//Si ninguna de las anteriores fue verdadera, muestra "soy mayor" en pantalla.

	//Porque en el bloque else muestro "soy mayor"? Porque si a no es igual a b y tampoco es menor, inequivocamente es mayor a b.
}
```

```csharp
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
	else if(!(a < b))
	{
	    Console.WriteLine("a no es menor que b");
	}
}
```

```csharp
public static void Main()
{
	//Esto es válido, porque es una expresión bool
	//Este if siempre entrará, porque siempre es true
	//Por supuesto, hacer esto en un proyecto real no tiene sentido
	if(true)
	{
		Console.WriteLine("Que bueno que siempre vean esto");
	}

	//Esto también es válido, este if jamás entrará
	//Nuevamente, en un proyecto real no tiene sentido
	if(false)
	{
		Console.WriteLine("Que lastima que jamas vean esto");
	}
}
```

### Contextos y anidamiento

Las variables "viven" en contextos definidos. Los contextos se definen mediante las llaves ({}).
El **if**, así como el **switch, while, do while, for** que veremos más adelante, crean contextos.

Los contextos pueden anidarse dentro de otros contextos. 
Esto significa que puedo hacer un if dentro de otro, y luego otro dentro, y otro y otro.
Cuantos quiera, de hecho.

```csharp
public static void Main()
{
	if(true)
	{
		Console.WriteLine("Aca entro");
		
		if(true)
		{
			Console.WriteLine("Aca tambien");

			if(true)
			{
				Console.WriteLine("Y aca");
			}
		}
	}
}
```

### Scope (o contexto de vida) de las variables

Cuando el contexto de una variable es destruido, la variable también se destruye.
Una variable creada en un contexto puede ser accedida desde cualquier lugar del contexto o desde un subcontexto.
Veamos un ejemplo. **Una función es un contexto**. Dentro de una función se puede crear un **if, que también es un contexto**.
En este caso el contexto del if es un subcontexto del de la función.

```csharp
public static void Main()
{
	int unaVariable = 3;

	if(true)
	{
		//Puedo usar "unaVariable" porque pertenece a un contexto "padre"
		unaVariable = 5;
	}
}
```

Como dijimos, podemos usar variables en subcontextos del contexto en que fue creada, pero no podemos usarla en contextos superiores.
Si las cosas fueran al revés en el ejemplo anterior y la variable fuera declarada dentro del if **no podríamos usarla fuera de su contexto.**

```csharp
public static void Main()
{
	if(true)
	{
		int unaVariable = 5;
	}

	//Esto da error. Cuando se sale del if, es decir
	//el contexto del if es destruido, "unaVariable" también se destruye.
	unaVariable = 8;
}
```

```csharp
public static void Main()
{
	if(true)
	{
		int unaVariable = 5;

		if(true)
		{
			//Esto si es válido, ya que este segundo if es
			//un subcontexto del primer if
			//que fue donde se declaró "unaVariable"
			unaVariable = 8;
		}
	}
}
```

### Bloque SWITCH

El bloque **switch** evalúa si la expresión dada (la variable) es igual a alguno de los casos expuestos en el bloque. Los deben ser valores **constantes**. Para determinar un caso se utiliza la palabra reservada **case**. Si ninguno de los casos cumple se puede utilizar un caso por defecto, con la palabra reservada **default**. Al final de cada caso se debe cerrar con la palabra reservada **break**.

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
	    default: //Opcional. Puede no estar.
	        Console.WriteLine("a es igual a " + a);
	        break;
	}
}
```

```csharp
public static void Main()
{
	int a = 15;
	int b = 10;
	
	switch(a) //La expresión debe ser variable
	{
	    case b: //ESTO NO ESTA PERMITIDO. DARÁ ERROR.
			Console.WriteLine("Algo");
			break;
	}
}
```

## Bucles:

### Bloque WHILE:

El bloque while, al igual que el if, evalúa bools dentro de sus paréntesis. Si lo que tiene dentro es igual a true, entra al bloque, sino no entra. El bloque se ejecutará una y otra vez hasta que la condición dentro de sus paréntesis sean igual a false.

### Ejemplos:

```csharp
public static void Main()
{
	int a = 15;
	int b = 10;

	while(a > b) //Mientras que a sea mayor que b, ejecutará el bloque
	{
	    a--; //Como vimos antes, esto resta 1 a lo que tiene a.
		Console.WriteLine(a);
	}
	//Entrará y restará 1 a la variable a. En el momento en que (a > b) sea igual a false el bloque dejará de ejecutarse. Exactamente en el momento en que a sea igual a b.
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

public static void Main()
{
	while(true) //esto es válido y es básicamente un bucle infinito.
	{
	    Console.WriteLine("SÁQUENME DE ACÁ");
	}
}
```

### Bloque Do-While:

Una variante del bucle while. La diferencia principal radica en que el bloque while se ejecutará **si y sólo si la condición que evalúa es igual a true**. En cambio do-while ejecutará su bloque **por lo menos una vez**, luego de ejecutar la primera vez si la condición evaluada fuera igual a false no se volverá a ejecutar.

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

### Bloque For:

El bucle for está diseñado para trabajar con una cantidad de iteraciones definida. Este bucle funciona al igual que los demás: ejecuta un bloque de código mientras una condición se cumpla.
El for consta de 3 partes ideales:
1. Asignación: Se asigna un valor a una variable. Usualmente a un int.
2. Condición: La condición que, mientras sea igual a true, hará que ejecute el bloque.
3. Incremento/Decremento: Se suma o resta al valor utilizado en la asignación. Esto suele ser la razón que hace que la condición en algún momento sea igual a false.

### Ejemplos:

```csharp
public static void Main()
{
	//for(asignacion ; condición ; incremento / decremento)

	for(int i = 1; i <= 10; i++) //Como nombre de la variable se suele usar la letra i
	{
	    Console.WriteLine("Iteracion numero: " + i); //Aprovecho el valor de i
	}
}
```

## Funciones:

Las funciones son bloques de código que **pueden o no devolver un resultado y pueden o no recibir parámetros**. Independientemente de si devuelven o no un resultado, siempre ejecutarán el código que tengan adjunto. Siempre debe existir una función llamada Main() que representa el comienzo del programa.
Las funciones constan de ciertos modificadores (como puede ser public), de un tipo de dato (como puede ser int o void), de un nombre seguido de paréntesis, donde puede o no recibir parámetros.
Los parámetros son datos con los que la función puede operar. Variables, básicamente.

Las funciones que tienen como tipo de dato **void** (que significa vacío) no devuelven nada. Las funciones que tienen cualquier otro tipo de dato devuelven un valor y estan obligadas a usar la sentencia **return** para retornar el valor, resultado de un operación. **void** no puede usarse como tipo de dato de una variable, solamente como tipo de dato de retorno de una función.

### Ejemplos:

```csharp
//Devuelve un dato y no recibe nada
public static int DevolverUnNumero()
{
	return 3; //la palabra reservada ‘return’ sirve para devolver un dato por función
    		//se profundizará más adelante
}

//No devuelve nada ni recibe datos
public static void Saludar()
{
	Console.WriteLine("HOLA MAMA");
}

//No devuelve nada y recibe un dato
public static void SaludarPorNombre(string nombre)
{
	Console.Write("HOLA ");
	Console.WriteLine(nombre);
}

//Devuelve un dato y recibe dos datos
public static int RestarNumeros(int primerNumero, int segundoNumero)
{
	return primerNumero * segundoNumero;
}
```

Vimos como crear nuestras propias funciones. Para llamar/invocar esa función se debe escribir su nombre y seguidamente abrir y cerrar paréntesis. Si la función recibe parametros, estos van dentro de los paréntesis, en el orden en el que la función los recibe. Cuando una función recibe más de un parámetro, estos se deben separar con una coma. A continuación se muestra como llamarlas:

```csharp
public static void Main()
{
	int miNumero = DevolverUnNumero(); 
	//El valor que devuelve una funcion puede asignarse a una variable

	Saludar(); 
	//Esta funcion no recibe ni devuelve nada, asique se invoca como se explicó anteriormente sin más.

	SaludarPorNombre("Santiago");
	//Esta funcion recibe una string, asique le pasamos un valor string entre los paréntesis. Si no lo hacemos, nos arrojará error.

	int miResta = RestarNumeros(5, 3);
	//Esta funcion recibe 2 parámetros. Estos parametros deben pasarse en orden de como la función los pide. Por ejemplo, esta función resta números, y como vemos arriba en su código, resta el segundo número al primero, haciendo 5 menos 3. Si pasaramos los valores al revés, restaría 3 menos 5. Cuidado con el orden!

	//Adicionalmente devuelve un resultado, producto de una operación. En este caso una resta.
}
```

Por ahora no hablaremos sobre las palabras reservadas **public** y **static**. Por el momento pensemos que es magia.

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

Se utiliza en funciones o propiedades para retornar un valor. Si la función devuelve void entonces solo termina con la función sin devolver nada. En este último caso la palabra **return** no es obligatoria.

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

Esta sentencia se suele considerar prohibida por muchas razones. La principal de ellas es que hace que el flujo del programa sea un caos. Sin embargo en algunos pocos casos es aceptable usarla. Básicamente salta hacia una sentencia **label** creada en el programa. Los case del switch son sentencias label.

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
	                Console.WriteLine("es una estupida");
	                break;
	        default:
	                Console.WriteLine("su nombre es " + nombre);
	                break;
	}

	//Si el nombre es roberta va a mostrar:

	//es una estupida

	//Si el nombre es mariana va a mostrar:

	//Es buena chica, pero
	//es un estupida
}
```

### throw
 
Permite arrojar excepciones que cortan el flujo de ejecución hasta que alguien "maneje" la excepción. Se profundizará sobre su uso más adelante.

## Arrays:

Los arrays son variables que guardan una cantidad finita de datos de un mismo tipo. Por ejemplo, se puede crear un array de int, char, bool, string o incluso de arrays. 
Las variables que tienen dentro no poseen nombres identificadores, sino que son accedidos mediante su número de índice. El índice **siempre comienza con el número 0** y los arrays tienen una propiedad llamada **Length** que representa su cantidad de índices. El último índice **siempre es igual a su Length menos 1**. **ES MUY IMPORTANTE NO CONFUNDIR EL INDICE UN ARRAY CON EL VALOR QUE GUARDA DENTRO DE ÉL.**

### Ejemplos:

```csharp
public static void Main()
{
	int[] array = new int[4]; //Se inicializa utilizando la palabra reservada new
	//entre corchetes se le pasa la cantidad de espacios que se quiere que tenga

	//Asigno valor a los espacios del array
	array[0] = 3;
	array[1] = 5;
	array[2] = 10;
	array[3] = 12; //Absolutamente siempre el último índice es igual al Length - 1
	
	int ultimoIndice = array.Length - 1;

	int primerValor = array[0];
	int ultimoValor = array[ultimoIndice]; 
	//se puede usar una variable para referirse a un índice dinámicamente.
}

public static void Main()
{
	int[] array = new int[10]; 

	//Los bloques for son especialmente útiles con los arrays
	//Se accede al Length de un array mediante el punto
	for(int indice = 0; indice < array.Length; indice++) 
	{                                                        
	    array[indice] = indice; //Lleno el array con valores
		//En este caso el indice resulta ser igual al valor de su espacio. RECUERDA NO CONFUNDIR AMBAS COSAS
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

public static void Main()
{
	int[][] jaggedArray = new int[3][4];

	//Para obtener el Length de cada uno
	int lengthDelPrimerArray = jaggedArray[0].Length;
	int lengthDelSegundoArray = jaggedArray[1].Length;
	int lengthDelTercerArray = jaggedArray[2].Length;
}
```

## Matrices

Una matriz es como un array de arrays. Tiene ciertas diferencias en la utilizacion y la performance. Para obtener el Length de una dimensión de la matriz se usa la función GetLength, que recibe el numero de la dimensión de la que se quiere consultar, empezando por 0.

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

public static void Main()
{
	int[,] miMatriz = new int[3, 4, 5];

	//Para obtener el Length de una dimensión
	int lengthDeLaPrimeraDimension = miMatriz.GetLength(0);
	int lengthDeLaSegundaDimension = miMatriz.GetLength(1);
	int lengthDeLaTerceraDimension = miMatriz.GetLength(2);
}
```

## Clases y Structs

Las clases y structs son definiciones de un objeto. Básicamente nosotros podemos crear nuestros propios tipos de dato y luego utilizarlos para nuestros fines.

```csharp
//Asi declaramos una clase Perro. 
//Es decir, estamos creando una definición de lo que es un perro en nuestro programa
public class Perro
{
	//Las clases pueden tener variables
	public string nombre;
	//O constantes, tambien
	public const int cantidadDePatas = 4;

	//Esto es un constructor. Mas adelante hablaremos de ellos
	public Perro(string _nombre)
	{
		nombre = _nombre;
	}

	//Tambien muy seguramente tenga funciones o metodos. 
	//Comunmente en el contexto de una clase a una funcion se le llama metodo
	public void Ladrar()
	{
		Console.WriteLine("Guau!");
	}
}

//De la misma podemos crear un struct Posicion2D
public struct Posicion2D
{
	public int x;
	public int y;

	//Los structs también pueden tener constructores
	public Position2D(int _x, int _y)
	{
		x = _x;
		y = _y;
	}
	
	//Y por supuesto también métodos. Este es un ejemplo
	public Position2D SumarPosicion(Position2D otraPosicion)
	{
		return new Position2D(otraPosicion.x + x, otraPosicion.y + y);
	}
}
```

Las clases y los structs representan el molde de un objeto. Perse, no hacen nada, es necesario instanciarlos. Para ello utilizamos la palabra reservada **new** seguida del **constructor** de la clase o el struct, que lo que hará es crear un objeto a partir de su propia definición.

```csharp
public class Program
{
	public static void Main(string[] args)
	{
		//Creo mi objeto perro en funcion de su clase
		Perro miPerro = new Perro(); //Mas adelante hablaremos de constructores

		miPerro.Ladrar(); //ahora que tengo un objeto puedo llamar a su funcion Ladrar. Yupi!
	}
}

public class Perro
{
	public string nombre;
	public const int cantidadDePatas = 4;

	public void Ladrar()
	{
		Console.WriteLine("Guau!");
	}
}
```

### Objetos

Los objetos son instancias de una clase o un struct. 
Esto quiere decir que son un elemento útil creado en función de una definición (la clase o el struct). 
Para que nosotros podamos ejecutar comportamiento definido en una clase o struct, guardar información o leerla, debemos crear un objeto.
 Este puede tener valores diferentes a otros objetos de la misma clase o struct, pero nunca una estructura diferente. 
Por ejemplo, nuestra clase "Perro" tiene un nombre, osea que todos los perros de nuestro programa tendrán un nombre. 
Cuando creamos un objeto nosotros podemos ponerle el nombre que queramos. 
Hay que pensarlo como si estuvieramos hablando de objetos en la vida real, si creamos 2 objetos de la clase "Perro" **¡Estamos creando 2 perros!**. 
Y si bien nosotros definimos que todos los perros tienen nombre, **esto no significa que los perros que creemos deban llamarse igual.
Para acceder a las variables y métodos de un objeto se utiliza el operador "." (dot)**

```csharp
public class Program
{
	public static void Main(string[] args)
	{
		//Creo 2 objetos. Estos comparten clase y por lo tanto tendran las mismas caracteristicas, pero no necesariamente los mismos valores.
		Perro miPrimerPerro = new Perro();
		Perro miSegundoPerro = new Perro();

		miPrimerPerro.nombre = "Fido"; //Mi primer perro se llama Fido
		miSegundoPerro.nombre = "Firulais"; //Pero mi segundo perro se llama Firulais

		Console.WriteLine(miPrimerPerro.nombre);
		Console.WriteLine(miSegundoPerro.nombre);
	}
}

public class Perro
{
	public string nombre;
	public const int cantidadDePatas = 4;

	public void Ladrar()
	{
		Console.WriteLine("Guau!");
	}
}
```

En nuestro ejemplo anterior, todos los perros que creemos tendrán nombre, pero este puede ser diferente entre ellos. Por otro lado esta la constante **cantidadDePatas** que es igual a 4. Al ser constante no puede cambiarse, por lo que los perros que creemos indefectiblemente tendrán 4 patas. Esta decisión en nuestro diseño no nos deja, por ejemplo, crear perros cojos. ¿Es esto malo? Depende de vos. Vos sos quien define como se compone un perro en tu programa ¡Podés hacer lo que quieras!

En lo que respecta a métodos, los perros anteriormente creados comparten por definición el método **"Ladrar"**. Los métodos representan acciones que un objeto puede ejecutar. Esto significa que todos nuestros perros por definición pueden ladrar.

```csharp
public class Program
{
	public static void Main(string[] args)
	{
		Perro miPrimerPerro = new Perro();
		Perro miSegundoPerro = new Perro();

		miPrimerPerro.nombre = "Fido";
		miSegundoPerro.nombre = "Firulais";

		miPrimerPerro.Ladrar(); //La consola mostrara "Guau!" en ambos casos
		miSegundoPerro.Ladrar();
	}
}

public class Perro
{
	public string nombre;
	public const int cantidadDePatas = 4;

	public void Ladrar()
	{
		Console.WriteLine("Guau!");
	}
}
```

### Constructores

Los constructores son métodos especiales que poseen todas las clases y structs, implícita o explícitamente. 
**Esto significa que no es necesario definir a mano un constructor, ya que si no se hace siempre habrá uno por defecto.** 
A diferencia de los métodos comunes que vimos hasta ahora, los constructores se definen colocándole un modificador de acceso **(ej. public, private)** y el nombre de la clase, luego los paréntesis con parámetros si necesitara. 
Los constructores sirven para comunicar los datos necesarios para construir un objeto determinado. 
Por ejemplo, podríamos definir que nuestros perros **necesitan** un nombre para ser creados.
**Si nosotros no definimos un constructor siempre tendrá uno vacío por defecto.
Si en cambio definimos uno, se convertirá en obligatorio.**

```csharp
public class Program
{
	public static void Main(string[] args)
	{
		Perro miPrimerPerro = new Perro("Fido"); //paso parametros distintos para asi tener 2 perros con distinto nombre
		Perro miSegundoPerro = new Perro("Firulais");
	}
}

public class Perro
{
	public string nombre;
	public const int cantidadDePatas = 4;

	public Perro(string nombreDelPerro)
	{
		nombre = nombreDelPerro; //asigno el parametro pasado por el constructor a la variable del objeto
	}

	public void Ladrar()
	{
		Console.WriteLine("Guau!");
	}
}
```

### Diferencias entre clases y structs

### Clases como tipos de referencia

Las clases son denominadas **"Reference Types"** o **"Tipos de Referencia"**. Esto significa que las clases se manejan **por referencia**.
Las variables de clases **guardan una referencia a un objeto. No guardan el objeto en sí. O sea, las variables guardan la información de donde se encuentra ese objeto en la memoria.**
Cuando utilizamos la palabra **new** seguida del constructor de la clase estamos creando un objeto en la memoria.
La variable involucrada, llamemosla **miReferencia**, guardará la dirección a donde se encuentra el objeto.
Si nosotros luego asignamos a otra variable lo que **miReferencia** contiene, esta nueva variable también tendrá la dirección en memoria en donde se encuentra el objeto.
**Pero el objeto siempre es el mismo. No se crean más objetos en el proceso, sino que se crean referencias a un sólo objeto.**

**Cuando utilizamos el operador "." en una variable de clase, nos estamos refiriendo al objeto al que apuntan.**

```csharp
public class Program
{
	public static void Main(string[] args)
	{
		//Creo un objeto de perro, al usar la palabra "new"
		Perro miReferenciaAUnPerro = new Perro();

		//Al hacer esto las 2 variables pasan a "apuntar" al mismo objeto
		//Esto significa que podemos usar cualquiera de las 2 referencias para llamar
		//a métodos o variables de un mismo objeto
		Perro miOtraReferenciaAlMismoPerro = miReferenciaAUnPerro;

		//Cambio el nombre de mi perro con una de las referencias
		miReferenciaAUnPerro.nombre = "Firulais";

		//Y puedo leerlo con cualquiera de ellas. No importa que referencia use aquí
		//En la consola siempre se mostrará "Firulais"
		Console.WriteLine(miOtraReferenciaAlMismoPerro.nombre);
	}
}

public class Perro
{
	public string nombre;
	public const int cantidadDePatas = 4;

	public void Ladrar()
	{
		Console.WriteLine("Guau!");
	}
}
```

Esto es muy importante tenerlo en cuenta a la hora de pasar objetos a través de funciones como parámetros o devolviéndolos como resultado, con un return.

```csharp
public class Program
{
	public static void Main(string[] args)
	{
		Perro miReferenciaAUnPerro = new Perro();

		miReferenciaAUnPerro.nombre = "Firulais";

		CambiarNombreAlPerro(miReferenciaAUnPerro);

		//Aquí será "Hercules" el resultado, porque el objeto fue
		//cambiado dentro del a función, a través de otra referencia
		Console.WriteLine(miReferenciaAUnPerro.nombre);
	}

	static void CambiarNombreAlPerro(Perro unPerro)
	{
		//A pesar de que "unPerro" no es la misma variable que "miReferenciaAUnPerro"
		//estas apuntan al mismo objeto, así que puedo cambiar sus propiedades
		//desde cualquiera de ellas
		unPerro.nombre = "Hercules";
	}
}

public class Perro
{
	public string nombre;
	public const int cantidadDePatas = 4;

	public void Ladrar()
	{
		Console.WriteLine("Guau!");
	}
}
```

### Structs como tipos de valor

Los structs, por el contrario que las clases, son **"Value Types"** o **"Tipos de Valor"**. Esto significa que los structs se manejan **por valor**.
Las variables de structs **guardan el objeto en ellas, no una referencia**. Cuando asigno una variable de un struct a otra del mismo tipo **se crea un nuevo objeto del struct, una copia, y se asigna a la nueva variable.**

Veamos los mismos ejemplos para "Perro", pero ahora como un struct.

```csharp
public class Program
{
	public static void Main(string[] args)
	{
		//Creo un objeto de perro, al usar la palabra "new"
		Perro miPerro = new Perro();

		//Le cambio el nombre a mi perro
		miPerro.nombre = "Firulais";

		//Cuando asigno lo que hay en la primera variable a la segunda
		//el contenido se copia y se crea un nuevo objeto del struct
		//Esto significa que este segundo perro viene con el nombre "Firulais" también
		Perro miOtroPerro = miPerro;

		//Al cambiar el nombre del objeto de mi segunda variable de perro
		//cambio unicamente al perro que contiene "miOtroPerro"
		miOtroPerro.nombre = "Hercules";

		//Ahora "miOtroPerro" se llama Hercules
		//y "miPerro" se sigue llamando Firulais
		Console.WriteLine(miPerro.nombre);
		Console.WriteLine(miOtroPerro.nombre);
	}
}

public struct Perro
{
	public string nombre;
	public const int cantidadDePatas = 4;

	public void Ladrar()
	{
		Console.WriteLine("Guau!");
	}
}
```

```csharp
public class Program
{
	public static void Main(string[] args)
	{
		Perro miPerro = new Perro();

		miPerro.nombre = "Firulais";

		//Al pasar un struct por una funcion, este tambien se copia
		//Por lo tanto, lo que reciba "CambiarNombreAlPerro" sera similar
		//pero no sera el mismo objeto que hay dentro de "unPerro"
		CambiarNombreAlPerro(miPerro);
		
		//"miPerro" se sigue llamando "Firulais"
		//su valor no cambio
		Console.WriteLine(miPerro.nombre);
	}

	static void CambiarNombreAlPerro(Perro unPerro)
	{
		//Aunque el metodo diga que cambia el nombre del perro, esto no es cierto
		//porque "unPerro" es nuevo objeto de tipo Perro
		//Cuando se destruya el contexto de esta funcion
		//el objeto que tiene "unPerro" también lo hara
		unPerro.nombre = "Hercules";
	}
}

public struct Perro
{
	public string nombre;
	public const int cantidadDePatas = 4;

	public void Ladrar()
	{
		Console.WriteLine("Guau!");
	}
}
```



## Pilares de la Programación Orientada a Objetos

### Encapsulamiento

El encapsulamiento es la capacidad y práctica de ocultar la implementación de un objeto y obligar a que la utilización de este se realice mediante sus métodos públicos.

#### Modificadores de Acceso

Los modificadores de acceso determinan que clases pueden observar y utilizar los elementos de otras. Las variables y funciones que pertenecen a una clase tienen implícitamente modificadores de acceso.
Por defecto, si no le coloca un modificador de acceso será **private**.

#### Ejemplo:

```csharp
public void UnaFuncionPublica()
{
	Console.WriteLine("Soy publica!");
}

private string miVariablePrivada = "Soy privada!";
```

Los modificadores de acceso posibles son:

```csharp
public -> accesible desde cualquier clase.
private -> accesible únicamente desde la clase que lo declara.
protected -> accesible desde la clase que la declara y cualquier clase que herede de ella.
internal -> accesible como si fuera pública desde el mismo assembly, 
pero privada para otros assemeblies.
protected internal -> accesible desde la clase que la declara y sus derivadas 
dentro del mismo assembly, pero privada para clases que hereden de la clase 
que la declara y se encuentren en otro assembly.
private protected -> cuando un elemento tiene este modificador, las clases que hereden de 
la que lo declara heredarán este elemento y podrán acceder a el, pero no al mismo 
elemento perteneciente a otro objeto.
```

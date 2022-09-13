# aws_python apuntes

### Estandar PEP8 (flake8) -> valida que el codigo este bien escrito
~~~
La barra diagonal invertida final (\) en el valor de la variable del paso anterior se utiliza para mantener el cumplimiento de la guía de estilo Propuestas de Mejora de Python (PEP) 
~~~

## Tipos de datos
##### type() identifica que tipo de datos es la variable
~~~
 numerico 
        entero INT (200/-20)
        flotante FLOAT (1.4/-1.9)
        complejo COMPLEX (1+ 1j)
booleano BOOL              -> IsEmpty = True (buena practica Is...)
        True/False
Cadena de texto            -> son inmutables, cuando se manipula no se modifica, se crea una nueva cadena 
        sting STR        
~~~

~~~
·· Lista LIST                -> 
        myFrutList = ["apple", "banana"]
        print(myFrutList[0]) #imprime el dato de la posicion 0, en este caso -> apple 
                ** append() para agregar un nuevo valor a la lista

·· Tupla TUPLE                -> inmutable, no se puede cambiar despues de su creacion 
        color = ("red","green","blue")
        
·· Diccionario DICT             -> conformados por una clave/key y un valor
        myFavorite = {
                "Juan": "Apple",
                "Marta" : "Banana"
                }
                ** para añadir:
                        myFavorite["Paula"] = "cherry"
                        myFavorite["Creator"] = ["creator2","creato1"]

**para ordenar loteria.sort() / loteria.sort(reverse=true)
~~~

## Conversion/parseado/casteado de datos 
~~~
de string a numero float() int()
de numero a string str()
~~~

## Funciones integradas/nativas
#### Una funcion le indica a la computadora que realice una tarea especifica 
/n salto de linea ->slash invertido 
~~~
/ type() nos permite reconocer que tipo de datos es 

/ print() 
        print("Hola mundo")

/ input() nos permite recibir una entrada por parte de un usuario (siempre ingresan como cadena de texto)
        input("Ingresa un numero")
   
/ .format() / f' nos permite devolver variables en string
        name = "Roberto"
        print("Hola {}, como estas?" .format(name))
        print(f'"Hola {name}, como estas?")
   
/ .len() devuelve la longitud de la variable 
        ejemplo = "abcdefghijk"
        print(len(ejemplo))
        print(ejemplo[0:3]) -> devuelve porcion de la variable
        
/ .capitalize() convierte el primer carácter de una cadena en una letra mayúscula y todos los demás alfabetos en minúsculas

/ .upper() convierte todas las minusculas a mayusculas

/ .count() para ir contando catidades de  ...
/  sum()  suma los valores 

/ range(10,14) da una numero menos el 14

/ .get() trae informacion

/ .values()  obtener valores de un diccionario
/ .keys() obtener claves de un diccionario
/ .items() prar recorrer y tomar cada item del diccionario 
/ .del() para eliminar del diccionario 

/ .split() divide toda una variable de tipo texto, quiero que la variable se divida cada ves que encuntres un guion (-) o cualquier caracter que queramos 
        ejemplo = "pera-mañana-platano-piña"
        print(ejemplo.split("-") #devuelve una lista con esos datos : ["pera","mañana","platano","piña"]

/ .strip() elimina los espacios al comienzo y al final del archivo
        ejemplo= "          estos es una cadena    "
        print(ejemplo.strip()) #devuelve "estos es una cadena"

/ .replace() reemplaza una palabra con otra
        origen = "Esto es una cadena"
        print(origen.replace("una", "otra")) # imprime "Esto es otra cadena"
~~~
## Funciones creadas 
#### namefunction() -> forma de invocar una funcion 
~~~
SINTAXIS        
        def sumar_uno(x):
        return x + 1            -> return devuelve algo de la funcion 
        
        resultado = sumar_uno(5)
        print(resultado) #imprime 6 
        
* funcion fuctrifera 
        def getDoubleAlphabet(alphabet):
            doubleAlphabet = alphabet + alphabet
            return doubleAlphabet
~~~

## Condicionales 
~~~
·· IF ELIF ELS
        numero1 = 5
        numero2 = 7
        if numero1 > numero2:
                print("n1 es mayor que n2")
        elif numero1 = 0:
                print(n1 es igual a 0"=
        else:
                print("n2 es mayor que n1")
                
··FOR           -> for i in lista (i por cada valor en lista)
        frutas = ["manzana","pera","uva"]
        for fruta in frutas:
                print("la fruta es:" , fruta)
                

~~~
## List comprehension             
#### sintaxis newList = [expresion for item in items if condition=True]
#### algo que se va a iterar y una condicion que se va a cumplir / tercer argumento es opcinal ?

~~~
        #manera original
frutas = ["manzanaa","kiwi","piña","mango"]
nuevaLista = []
for fruta in frutas:
        if "a" in fruta:
                nuevaLista.append(fruta)

        #list comprehension    
nuevaLista2 = [fruta for fruta in frutas if "a" in fruta]  
~~~

## Import
~~~ 

·· importar archivos (permite trabajar con otros archivo )
        with open ("filesname.txt") as archivonuevo:
        data = archivonuevo.read()
        
·· importar funciones de otros archivos
       opc1
                 import operaciones 
                 resultado = operaciones.sumar(5)
       opc2
                 from operaciones.operacion import sumar,restar    -> ir ingresando a carpertas con operacion.newfiles.operaciones y asi 
                 reusltado = sumar(5)
~~~
##  MODULO import
~~~
 **puede utilizar funciones proporcionadas por otros desarrolladores a través de la instrucción import
 
 sintaxis->
        opc1 -> from modulo import function
        opc2 -> import modulo 
                modulo.funtion()
 
·· from math import pi -> importar una funcion en especifica en este caso pi 
https://docs.python.org/3/library/math.html
·· import math -> importar todas las funciones que tiene match 
        math.fabs() covertir de un valor negattivo a un valor positivo
        math.floor() toma el valor flotante y devuelve el valor entero
        
        
·· import random
        random.ranont(1,10) #devuelve un numero randon del 1 al 10 
        
·· import re 
        # sub() sirve para reemplazar las ocurrencias de un patrón en una cadena (como otra opcion tambien tenemos replace())
        # 1er argumento: patrón
        # 2do argumento: valor por el que voy a remplazar las ocurrencias
        # 3er argumento: cadena sobre la cual haré la búsqueda
        
        origen = "Esto es una cadena"
        pattern = r's'  (la r' respresenta que lo siguiente sera un patron para buscar)
        resultado = re.sub(pattern, 'f', origen)
        print(resultado) #imprime efto ef una cadena
        
        pattern2= r'[as]' (para buscar coincidenias de patrones de mas letras)
        pattern3= r'cadena' (busca la palabra completa)
~~~
## Control de flujo
#### excepciones 
~~~
atrapar y controlar los errores para que el codigo no se detenga
·· except IOError: -> cuando el archivo no existe
        print("el archivo no existe")

try/except -> manejar posibles errores para que el programa no se rompa 

 try:                                   -> si lo que esta en este bloque no se logra hacer, ingresar a except para ocuparse del error 
        with open(fileName) as json_file:
            data = json.load(json_file)
    except IOError:
        print("Could not read file")


~~~

## SO 
#### Python proporciona varios módulos que también puede utilizar para ejecutar comandos en la línea de comandos

~~~
·· SO : modulo del sistema operativo
        import os
        os.system("adduser newuser")
        os.system("whoami")
        os.system("ls")
   
·· SUBPROCESS           
        import subprocess
        subprocess.run(["ls"])
        subprocess.run(["ls","-l","README.md"])
~~~
## JSON 
#### notacion de objetos JavaScripts
#### import json 
~~~
tecnicas especialmente util cuando hay mas de un tipos de dato en un conjunto de datos 
json.dumps/dump convierten varios tipos de datos en una cadena
load/loads vuelven a convertir una cadena de datos estructurados
dump/load trabajan directamente con archivos
dumps/loas 

·· trabajando/leyendo archivos json
                import json                                     -> importar biblioteca json

                def readJsonFile(fileName):                     -> crear funcion para leer archivos json
                    data = ""
                    try:                                                
                        with open(fileName) as json_file:       -> leyendo archivo externo     
                            data = json.load(json_file)         -> convierte el archivo json una cadena de datos estructurados
                    except IOError:                             -> except para error (especificamente error de no leer archivos)        
                        print("Could not read file")            -> imprime para dar una respuesta en caso de error 
                    return data                                 -> devuelve respuesta de datos de json a un diccionario 

                print(readJsonFile("insulin.json"))             -> ejecuta funcion con el arcchivo json que queramos 
~~~

## PIP -> manejador de paquetes, para instalar codigo de 3ros que puedne contener librerias 
#### se llama a pip desde la linea de comando 

## Depuracion                   -> pdb
#### se realiza para identificar defectos en el propio codigo (logs)
~~~
python -m pdb <filename>
         *** aserciones
        afimacion, que permite validar, se cumple o no ? si se cumple devulve esto
        def loguserage(age):
                assert age <= 0, "Invalid age was supplied"
~~~
## LOGS         -> guarda regitros en python
#### monitoreo de registro 

## DevOps -> ingenieros de confiabilidad -> Development operations
https://devopslatam.com/tabla-periodica-de-herramientas-devops/
#### cultura (consjunto de buenas practica, guia de lo que se podria hacer )y practica de ingenieria de software, cuyo obj es unificar el desarollo dev  y operaciones ops de softare 
#### ayuda a apoyar estrategias para crear organizaciones de alto rendimiento 
#### para trabajar de forma continua entre ti tradicional , desarrollo de software y control de calidad

#### caracteristica principal, es permite la automatizacion y el monitoreo en todas las etapas de la creacion de software 
##### automatizacion 
##### lean -> lo justo y mecesario / eficaz
##### medicion -> tomar el tiempo de las cosas (tiempo de mejora)
##### uso compartido -> practicas y metodologia que se comparte y trabajo en equipo

~~~
###### metodologia agil ???? no secuencial
pequeñas mejoras continuas

integracion y entrega continuas CI/C :


implementacion
aumatizacion
     compilacion
     pruebas
     
riegos de la automatizacion
sobreautomatizacion
subautomatizacion
automatización deficiente

     
Integracion continua: asegurarse de que el codigo funciona con lo que ya se ha hecho 
                      asegurarse que LO QUE INTEGREMOS NO ROMPA EL CODIGO, SIGA FUNCIOANNDO CON NOSRMALIDAD 
Entrega continua : ya probe "eso funciona" ahora quiero lanzarlo e implementar
garantiza que se pueda desplegar de fomar correcta 
IMPLEMENTACION

infraestructura 
como organizo un repositorio de codigo para que las ersonals puedan trabajar
herramientas y plantillas
por estilo -> pylint : se encarga de ver que el codigo este bien escrito
por logica -> pytest : de que la logica del codigo este clara

administracion de la configuracion de software
-> control de versiones 
~~~

## BASE DE DATOS -> orientado a MySQL
#### DATOS: trosos de info en bruto / partes y fragmentos de info sin procesar (bits de infomacion)
#### una base de datos es un conjunto de datos que se organiza en archivos denominados TABLAS (son formas logicas de acceder a los datos gestionarlos y actualizarlos )
#### MODELO DE DATOS : estructura logica de una base de datos 

##### modelo no relacional : no requiere una definicion fija de la estructura de los datos 
     -estructura mucho mas flexible ante cambios de esquema
     -al ser mas flexible, permite añadir datos de forma mas dinamica

#### modelo relacional o SQL(Structured Query Language) : se creo para manejar mejor grandes cantidades de datos / conjunto de elementos de datos que tienen relaciones predefinidas entre ellos 

##### FILAS -
#### COLUMNAS |

## CRUD: CREATE READ UPDATE DELETE
#### operaciones que se utilizan en db / consulta/ peticion de datos 
 
## Sistema de gestion de base de datos (DBMS)
#### MOTORES DE BD RELACIONALES : MySQL , SQL Server, Postgres, Oracle SQL

 *
#### software qur proporciona funcionalidad de base de datos 
### BASE DE DATOS COMO SERVICIO (DBaaS)
### Interacion con los datos a traves de SQL 
*
## Grupo de instrucciones SQL

#### lenguaje de manipulacion de datos DML : SELECT, UPDATE, INSERT, DELETE
#### lenguaje de definicion de datos DDl : CREATE TABLE, DROP TABLE
#### lenguaje de control de datos DCL : REVOKE, GRANT

##Tipos de datos 
#### predefinidos: ya definido en un motor de plantilla (pueden ser no compatible con otros motores de plantillas, utilizar tipo de datos standar como sea posile )
#### construidos: 
#### definidos: 
~~~
     NUMERICOS
INTEGER: n entero  valor min y max dependiendo de motor de plantilla
SMALLINT: igual que tipo interget, porque contieneun rango de valor menor -999 999
BEGINT : igual que tipo interget,puede contener un rango de valor mayor
DECIMAL: (p,s) la escala no puede superar la precision
DECIMAL: almacenar los valores monetarios, en lugar de FLOAT o REAL(no ocuapr para tipo de datos exactos,para contabilidad no )
NUMERIC:(p,s) la precision depende de DBMS
FLOAT: 
REAL:
DATE: dd-mm-aaa
TIME: hh:mm:ss
DATETIME: fecha y hora
TIMESTAMP: fecha y hora y zona horaria de transaccion
INTERVAL: representa periodo de tiempo 60:00 interavalo o duracion 
~~~
~~~
     CHARACTER STRING
CHAR: cadena de caracter de longitud fija CHAR(2)
VARCHAR: cadena de caracter de longitud variable, longitud maxima fijada
CLOB: obj grande de caracter, referencia de una ubicacion(ruta drive, ruta de archivo)
~~~

#### Restricciones
+ NOT NULL : entrada obligatoria de datos /asegura que una columna no continene valor NULL
+ UNIQUE : requiere que una columna o conjunto de columnas tenga valores que sean exclusivos de esas columnas 
+DEFAULT: si no se ha definido nigun valor, default proporciona un valor cuando el DBMS inserta un registro 


#### a traves de la claves se comunican las tablas (una referencia a otra )
+ PRIMARY KEY : CLAVE PRINCIPAL tiene un valor unico / para relacionar datos y no tener redundancia 
+ FORENG KEY : CLAVE EXTERNA relacion con PRIMARY KEY 

+ Integridad referencial: DB en la que cada valor de clave externa no NULA coincide  con un valor de clave principal existente 

#### Tablas 
+ IF NOT EXISTS : comprobar/validar que no exista una base de datos con ese mismo nombre
##### sentencias 
+ CREATE TABLE employees
+ CREATE TABLE IF NOT EXIST employees
~~~
CREATE TABLE employees(
employee_is INTERGER NOT NULL PRIMARY KEY,
given_name varchar(20) DEFAUL NULL,
FAMILY_NAME VARCHAR(25) NOT NULL,
dept_is INTERGET NOT NULL
);

*sintaxis
INSERT INTO tableName (col_1,col_2,col_3)
VALUES("VAL_1","VAL_2","VAL_3");

INSERT INTO tableName 
VALUES("VAL_1","VAL_2","VAL_3");

INSERT INTO tableName (col_1,col_2,col_3)
VALUES("VAL_1","VAL_2","VAL_3"),
      ("VAL_11","VAL_52","VAL_23"),
      ("VAL_21","VAL_32","VAL_31");
 
* podemos insertar valor NULL, si no tiene restricciones 
~~~
#### DESCRIBE: proporciona una descripcion de la tabla (DESCRIBE tableName;)

#### Importacion CSV
#### archivo separado por comas(CSV)
~~~
LOAS DATA INFILE `rutadearchivo`
INTO TABLE `nameDB`,`loyalty`
COLUMN terminated by `.`
LINES TERMINATED BY `/n`
IGNORE 1 LINES;
~~~
#### SELECT
~~~
SELECT * FROM `pub`, `loyalty`;

SELECT COUNT(*) FROM `pub`, `loyalty`;  -> cuenta cantidad de filas

SELECT nameCol1, nameCol2 FROM nameTable; -> especifica que columnas devuelve

SELECT nameCol1, nameCol2 
FROM nameTable
WHERE nameCol1 = "SL";



~~~

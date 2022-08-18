# Desglose

Como base se uso el archivo que funciona(110R01.SVC) y en se fue siguiendo la secuencia que tiene con comentarios (lcsTest4.svc). En el archivo base si la linea coincidia con el otro se copio tal cual y si tenia un valor diferente se anoto como //Original [ValorOriginal]. Tambien hay bloques de codigo que no estan el archivo base y se anoto como //New.




## Primer bloque

Parar alarma + Conteo de parametros

## Segundo bloque

Establecer valores + Conteo de parametros + Conteo de valores + Valor ID + Deshabilitar prepocesamiento

## Tercer bloque

Limpiar display + Conteo de parametros

## Cuarto bloque

Control de parametrizacion + Conteo de valores + Empezar

## Quinto bloque

Iniciacion de configuracion guardada

## Sexto bloque

Cargar configuracion guardada, carga participantes con la siguiente estructura:

```JavaScript
#0x0{n}00# Logical device number
#0x{m}# Length code | Ident code
#0x0000# Device level
#0xFFFF# Group number | Alternative
```

## Septimo bloque

Terminar de cargar la configuracion guardada + Conteo de parametros + Automatic PCP channel configuration

## Octavo bloque

Cambio de acceso a variable ID + Habilitacion

## Noveno bloque

Asignacion de variables con el siguiente formato

```JavaScript
#0x{n}# Variable ID
#0x0000# [Nombre Variable]
#0x{m}# ..
```

## Decimo bloque

Cambio de acceso a variable ID + Deshabilitacion

## Undecimo bloque

Insersion del proceso de listado de descripcion de informacion + Mapeo de señales con el siguiente formato:

```JavaScript
#0x601{n}# PDD-Index
#0x0C0A# Direction | Datatype
#0x0000# Byteposition
#0x0001# Bitposition | Datalength
#0x00FF# Extension
```

## Duodecimo bloque

Fin de insersion del proceso de listado de descripcion de informacion

## Decimotercer bloque

Inicializacion de carga del proceso de listado de referenciado de informacion

## Decimocuarto bloque

Carga de del proceso de listado de referenciado de informacion

### Primeros 6

```JavaScript
x=[1,2,3,4,5,6]

#0x000{x}# PDRL-Index
#0x0200# Remote bus number | Local bus number
#0x601{n}# PDD-Index
#0x100{m}# Destination address (Byte)
#0x0002# Destination address (Bit) | Consistency
#0x00FF# Extension
```

### Ultimos 6

```JavaScript
x=[1,2,3,4,5,6]

#0x400{x}# PDRL-Index
#0x000{m}# Source address (Byte)
#0x0002# Source address (Bit) | Consistency
#0x0200# Remote bus number | Local bus number
#0x601{n}# PDD-Index
#0x00FF# Extension
```

## Decimoquinto bloque

Finalizacion de carga del proceso de listado de referenciado de informacion

## Decimosexto bloque

Control de parametrizacion

## Decimoseptimo bloque

Activacion de configuracion

## Decimooctavo bloque

Inicio de transferencia de datos

## Decimonoveno bloque

Cambio de derechos de exclusividad + Liberacion de derechos

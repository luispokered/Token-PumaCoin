# Token PumaCoin project
El proyecto define un nuevo token que se creó bajo el estándar ERC20 para la plataforma Ethereum
El token y los archivos necesarios están escritos en el lenguaje de programación Solidity, es necesario utilizar el [IDE Remix](https://remix.ethereum.org/) para observar el token en funcionamiento.

## Primeros pasos
Dentro de el link adjuntado anteriormente:
* Clickear el botón "Use previous version".
* Volver a cargar la página y clickear "Ok".
* Crear un nuevo archivo llamado PumaCoin.sol, en el que pegaremos el código del archivo PumaCoin.sol del repo
* Crear un nuevo archivo llamado PCXsale.sol, en el que pegaremos el código del archivo PCXsale.sol del repo
* En la parte derecha se encontrará el menú del compilador, seleccionar la versión 0.5.0 dado que en esa versión se escribió el código.
* Presionar el botón "Start to Compile" para compilar el programa.
* Ir a la pestaña "Run" para poder ejecutar el programa.

## Para ejecutar el código PumaCoin
Pasos a ejecutar:
* Compilar el código.
* Dar click en la ventana "Run" que se encuentra en la esquina superior derecha.
* Seleccionar el enviroment "JavaScript VM" (Esto se hace para hacer una simulacion local del funcionamiento del SmartContract en cuentas que tienen un saldo de Ethers).
* Seleccionar alguna de las cuentas disponibles en la seccion "Account" (Notar que para cada operacion se va a hacer un gasto de "gas", que es el costo computacional para hacer esa accion, se tendrá un limite por default de 3M de gas), esta cuenta será la cuenta owner que hará el deploy del SC.
* Clickear el boton "Deploy". El Smart contract ya se encuentra listo para ejecutar.
* Clickear el boton con el nombre "PumaCoin".
(antes de realizar esto, para evitar errores se recomienda desplegar cada funcion quen tenga una flecha a la derecha y meter en los cuadros los datos, ya que al desplegarse se separan los rubros y se evitan los errores).

### Pasos para ver el balance e información adicial de una cuenta

* Cambiar a la cuenta de la cual se quiere obtener informacion. 
* Copiar su direccion y pegarla en el recuadro adyacente de "balanceOf"
* Dar click al botón "balanceOf" para ver el balance de la cuenta
* Dar click al botón "decimals" para ver los ceros que se le agregan a los tokens que inicialmente se tienen.
* Dar click al botón "name" para ver el nombre del token
* Dar click al botón "symbol" para ver el nombre del token 
* Dar click al botón "totalSupply" para ver la cantidad total de tokens

### Pasos para hacer una transferencia a otra cuenta

La ejecución de todo este punto se debe hacer con la cuenta owner, solamente se cambia a otra cuenta para poder copiar su dirección.

* Seleccionar la segunda cuenta  y copiar la dirección de la cuenta (dando click al botón que se encuenta a la misma altura de "Account", es un simbolo negro con un cuadrado blanco que se llama "Copy value to the clipboard")
* Pegar la dirección en el recuadro adyacente al botón "transfer". 
* Poner una coma "," y despues poner la cantidad de tokens a transferir (Tomar en cuenta que se tienen 1000000000000000000000000 unidades inicialmente) o en su defecto en el primer recuadro la dirección y en el segundo la cantidad
* Dar click al botón "transfer" y checar en la consola de comandos que la transacción se hizo de manera correcta

### Pasos para darle permiso de utilizar una cantidad de tokens a cierta cuenta

La cuenta que dara todos los clicks en los botones de las funciones será el owner
* Cambiar a la cuenta que dará el permiso para obtener la direccion y poder copiarla

* Poner en el recuadro adyacente de "approve" la cuenta que tendrá el permiso y la cantidad máxima de tokens a las que tendrá permiso.
* Poner en el primer recuadro adyacente de "allowance" la cuenta que dará permiso, despues en el recuadro de abajo poner la cuenta que recibirá el permiso
* Dar click al botón "allowance" y checar en la consola de comandos que el permiso se concedió de manera correcta

### Pasos para Transferir de una cuenta a otra

* Cambiar a la cuenta que trasferirá los tokens (la que tiene permiso)
* En el recuadro adyacente del boton "transferFrom" poner las dos direcciones y la cantidad a tranferir separada por comas o al desplegarse cada recuadro poner:
     1. primero la cuenta de donde provienen los tokens y que dió permiso (owner),
     2. después a la cuenta donde se transferiran 
     3. por último la cantidad de tokens a transferir
* Dar click al botón "transferFrom" y checar en la consola de comandos que la transacción se hizo de manera correcta

***

## Pasos para ejecutar el código PCXsale
**Importante** (Primero se debe compilar y hacer deploy al programa PumaCoin para que este código funcione correctamente)

* Compilar el código PCXsale
* Dar click en la ventana "Run" que se encuentra en la esquina superior derecha.
* Seleccionar el enviroment "JavaScript VM" (Esto se hace para hacer una simulacion local del funcionamiento del SmartContract en cuentas que tienen un saldo de Ethers).
* Seleccionar el archivo PumaCoinSale para hacer su deploy
* Copiar la dirección del SC PumaCoin (dando click al botón que se encuenta a la misma altura de "PumaCoin at...(memory)", es un símbolo negro con un cuadrado blanco que se llama "Copy value to the clipboard").
* En el recuadro adyacente del botón "Deploy", poner el precio al que se pondrá
* el token (El equipo decidió que fuera 100 wei por token) y  la direccion que copiamos en el paso anterior.
* Clickear el boton "Deploy".
El SC ya se encuentra listo para ejecutar.

* Clickear el botón con el nombre "PumaCoinSale".
* Copiar la dirección del contrato PumaCoinSale
* Proceder a transferir tokens al SC, los suficientes para poder realizar compras

### Pasos para comprar tokens

* Seleccionar la cuenta con la que queremos comprar tokens
* En el campo adyacente al boton "buy",se pondrá la cantidad de tokens a comprar
* En el campo value se debe poner el costo del token multiplicado por la cantidad de tokens que queremos 
* (100*(cantidad de tokens))
* Clickear el botón "buy"
### Paso para dejar de vender tokens y transferir el sueldo total
* Cambiar a la cuenta owner que hizo deploy al SC PumaCoin
* Clikear el botón "endSold"
* Revisar en la linea de comandos que la transaccion fue correcta
* Revisar el saldo de wei (Unidad minima de un Ether)

 **Nota** Si queremos ver un cambio verdadero, se recomienda que 
 el costo total de wei´s sea mayor a 80000 para que no se vea 
 afectado por el gas utilizado en la transacción.
 

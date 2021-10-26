# Callback-Ubidots

Primero necesitamos crear una cuenta en Ubidots. Ir al siguiente link: 

https://stem.ubidots.com/accounts/signin/

y seleccionar Ubidots STEM. Seguir los pasos hasta crear nuestra cuenta. Una vez accedemos, tendremos el panel principal

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git1.png?raw=true)

Para conectar nuestros dispositivos Sigfox, debemos crear un conector, para esto ir a la pestaña DEVICES y despues PLUGINS

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git2.png?raw=true)

Seleccionamos CREATE DATA PLUGIN

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git3.png?raw=true)

ahora escogemos el plugin de SIGFOX

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git4.png?raw=true)

despues nos apareceran las instrucciones para la configuraion del callback. Damos clic en siguiente

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git5.png?raw=true)

en la seccion de "Ubidots Token", hacemos clic y seleccionaremos DEFAULT TOKEN. Damos clic en siguiente

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git6.png?raw=true)

Podemos cambiar el nombre y descripcion de nuestro plugin. Damos clic en finalizar

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git7.png?raw=true)

Una vez terminado, veremos nuestro plugin. 

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git8.png?raw=true)

Damos clic sobre nuestro plugin e iremos a la pestaña DECODER. Alli veremos la URL que necesitamos copiar para la configuracion del callback

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git9.png?raw=true)

Para la configuracion del callback, vamos a nuestra cuenta de backend, en la pestaña DEVICE y damos clic en el ID de nuestro dispositivo o tarjeta

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git10.png?raw=true)

nos aparecerá la información de nuestro dispositivo. Hacemos clic en el nombre que apararece en la parte de "Device type"

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git11.png?raw=true)

Nos aparecerá la informacion del device type y en la seccion del lado izquierdo, en la pestaña de CALLBACKS y despues en la parte superior derecha en la opcion NEW

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git12.png?raw=true)

Seleccionamos CUSTOM CALLBACK

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git13.png?raw=true)

Ahora debemos configurar el callback. 
  - Pegamos la URL que obtuvimos de ubidots
  - Seleccionamos POST como metodo http
  - Escribimos "application/json" en el content type
  - Pegamos el siguiente json en el body

        {
        "device_id" : "{device}",
        "data" : "{data}"
        }

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git14.png?raw=true)

damos clic en OK y si no hay ningun error, veremos nuestro callback creado

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git15.png?raw=true)

para comprobar que no hay ningun error, esperamos a que nuestro dispositivo transmita un nuevo mensaje. Si todo estuvo bien, el estatus del callback se pondrá de color verde, indicando que el dato se entregó correctamente a Ubidots

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git16.png?raw=true)

tambien podemos corroborarlo llendo a nuestra cuenta de ubidots, en nuestro plugin, en la pestaña LOGS, donde veremos los datos del mensaje o mensajes enviados despues de la creacion del callback

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git17.png?raw=true)

finalmente, si vamos a la pestaña de DEVICES, veremos que se creó un dispositivo con el ID de nuestra tarjeta o dispositivo

![devkit_pinout](https://github.com/Iotnet/Callback-Ubidots/blob/main/images/Ubidots_git18.png?raw=true)

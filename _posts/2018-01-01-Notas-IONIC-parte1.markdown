---
layout: post
title: "Notas IONIC parte 1"
img: himalayan.jpg # Add image post (optional)
date: 2018-01-01 20:00:00 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
tag: [Programacion, Blogging, Ionic]
---

# IONIC

##PRIMEROS PASOS.

Primero instalar GIT.

Después instalar Apache Cordova.

Instalar NodeJs.
 `$ sudo npm install -g cordova`

Instalar ionic.
`$ sudonpm install -g ionic`

Creando el proyecto.
`$ ionic start proyecto blank`

Cambiar la ruta a la del proyecto creado.
`$ cd  proycto`

Ahora hay que cear las plataformas.
`$ ionic cordova platform add ios`

`$ ionic cordova platform add android`


Para las preubas primero compilamos.

`$ ionic cordova build  ios/android`

Y mas tarde ejecutamos
`$ ionic cordova emulate ios/android`

También disponemos del comando prepare para hacer un update del proyecto, de esta forma se actuailizarán repositorios automáticamente.
`$ ionic cordova prepare ios/android`

Para hacer test de forma nativa.
`$ ionic cordova run android`
( si no funciona, revisa tener activo el modo debug en el dispositivo USB).
________________________________________________________
## PUBLICAR TU APP.

Lo primero necesitas generar una versión compilada de la aplicación, elegir la plataforma.
Después hay que tener cuidado de ajustar los plugins que durante el desarrollo han estado pero pueden no estar en el modo de producción.
Por ejemplo: posiblemente no quieras tener el plugin de consola debug habilitado, así que habría que quitarlo antes de generar la versión compilada.

`ionic cordova plugin rm cordova-plugin-console`


###Publicar en Android

Para generar la versión compilada para Android: 
`$ ionic cordova build --release android`

Esto se basa en la configuración de tu `config.xml` 

Una vez ejecutado se creará un archivo .apk en la ruta:
`platforms/android/build/outputs/apk`

Ahora el siguiente paso es firmar el APK y correr una herramienta de optimización.

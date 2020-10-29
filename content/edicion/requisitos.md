+++
title = "Requisitos"
weight = 1
+++

Para contribuir a la edición del sitio principal se necesita principalmente una cuenta en [GitHub](https://github.com). Para más información, revise la página del [GitHub Organization]({{< ref "../cuentas/github-organization.md" >}}). Ya teniendo una cuenta en la plataforma con acceso a la organización es que puede empezar a contribuir.

## Instalación de un cliente Git

[Git](https://git-scm.com/) es un sistema de control de versiones que permite interactuar con la plataforma *GitHub*. Normalmente se utiliza con una herramienta de consola pero existen clientes de interfaz gráfica. En este caso, se presenta como instalar [GitHub Desktop](https://desktop.github.com/). Primero, diríjase al sitio de [GitHub Desktop](https://desktop.github.com/) y descárguelo haciendo click en el botón **Download for ...**.

Al ejecutar el instalador se le presentará una pantalla como esta:

{{< figure src="/guia/img/edicion/github_desktop_1.png" >}}

Haga click en **Sign in to GitHub.com**. Se le abrirá una nueva ventana de su navegador de Internet, inicie sesión en *GitHub* y regrese al instalador.E

Esta nueva ventana se le presentará.

{{< figure src="/guia/img/edicion/github_desktop_2.png" >}}

Si sus datos están ingresados correctamente entonces haga click en **Continue**, sino ingrese en **Name** su nombre de usuario de *GitHub* y en **Email** su dirección de correo electrónico que utilizó para crear su cuenta y luego continue.

El instalador habrá entonces acabado y se le presentará con la ventana principal.

{{< figure src="/guia/img/edicion/github_desktop_3.png" >}}

En la parte derecha usted podrá encontrar todos los repositorios a los cuales tiene acceso. En esta liste, busque `manos-al-codigo/manos-al-codigo.github.io` y de click en **Clone**.

{{< figure src="/guia/img/edicion/github_desktop_4.png" >}}

Esta nueva pantalla se le aparecerá, en **Local path** seleccione dónde en su computadora desea guardar los datos del sitio. Finalmente, dele click en **Clone**.

Finalmente se le presentará esta pantalla:

{{< figure src="/guia/img/edicion/github_desktop_5.png" >}}

Este es su panel de control del repositorio del sitio. Para saber cómo subir cambios al proyecto, visite [esta página]({{< ref "./manejo-contenido" >}}).

## Instalación de Hugo

[Hugo](https://gohugo.io/) es el servicio utilizado para construir el sitio web en base a archivos de texto formateado en *Markdown*. Esta herramienta es la que le permite generar un sitio estático y estructurado a través de archivos *Markdown* sin tener que tocar una línea de código. Normalmente todo se genera automáticamente en la plataforma *GitHub* por lo que la única razón por la cual usted debería instalar *Hugo* es para probar el sitio al momento de su edición para asegurarse de que todo funcione bien antes de subir sus cambios.

Primeramente se debe descargar *Hugo* para su sistema operativo. Visite [esta página](https://github.com/gohugoio/hugo/releases). Se encontrará con una lista de descargas como esta:

{{< figure src="/guia/img/edicion/hugo_install_1.png" >}}

Seleccione la que corresponda a su sistema operativo. Si se encuentra en **Windows (64 Bits)** descargue la que se llama `hugo_extended_x.x.x_Windows-64bit.zip`. Si prefiere descargar la versión utilizada en este proyecto haga click [aquí](https://github.com/gohugoio/hugo/releases/download/v0.76.5/hugo_extended_0.76.5_Windows-64bit.zip) para descargar *Hugo* para **Windows (64 Bits)**.

Luego, cree una carpeta llamada `bins` en su **Disco Local C:** y transfiera el archivo llamado `hugo.exe` (que se encuentra en el archivo descargado) a esa carpeta.

{{< figure src="/guia/img/edicion/hugo_install_2.png" >}}

Ahora haga click derecho en `Este PC` o `This PC` y seleccione **Propiedades**. Se le presentará una ventana como esta:

{{< figure src="/guia/img/edicion/hugo_install_3.png" >}}

En la parte izquierda, seleccione la opción `Opciones de sistema avanzadas` o `Advanced system settings`. Se le presentará otra ventana similar a esta:

{{< figure src="/guia/img/edicion/hugo_install_4.png" >}}

En la parte superior, haga click en `Avanzado` y haga click en el botón al final que dice `Variables de entorno`. Se le presentará otra ventana similar a esta:

{{< figure src="/guia/img/edicion/hugo_install_5.png" >}}

En la primera lista donde dice `Variables de usuario` haga doble click en `Path`. Esta pantalla aparecerá:

{{< figure src="/guia/img/edicion/hugo_install_6.png" >}}

Haga click en `New` y escriba:

```text
C:\bins
```

Finalmente haga click en `OK`.

Ahora, abra el menú de inicio y escriba en la barra de búsqueda `cmd`, abra la opción llamada **Símbolo del sistema** o **Command Prompt**, una ventana negra le aparecerá donde podrá escribir comandos para el ordenador. Escriba en esta ventana:

```text
hugo version
```

Le deberá aparecer un mensaje semejante al siguiente:

{{< figure src="/guia/img/edicion/hugo_install_7.png" >}}

¡Listo!, *Hugo* ha sido instalado en su ordenador. Si al correr el comando mencionado previamente no le aparece un mensaje similar al que aparece en la imagen, vuelva a repetir los pasos previos.

## Editor de Markdown

*Markdown* es el lenguaje de formateo de texto que se utiliza para construir el contenido del sitio. No se necesita un programa especial para editar estos tipos de texto ya que son simplemente archivos de texto que se pueden editar con el **bloc de notas**. Sin embargo, para que su experiencia sea más placentera, se recomienda utilizar alguno de estos programas:

* [Atom](https://atom.io/)
* [Visual Studio Code](https://code.visualstudio.com/)
* [Sublime Text](https://www.sublimetext.com/)

Instale el editor de texto de su preferencia para editar estos archivos.

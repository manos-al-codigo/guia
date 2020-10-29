+++
title = "Manejo del contenido"
weight = 3
+++

En esta página encontrará una descripción instructiva acerca de la edición de la página principal.

## Estructura del sitio

Si siguió los pasos encontrados en [Requisitos]({{<ref "requisitos.md" >}}) entonces debería tener ya descargada la carpeta con los archivos del sitio web principal. En esta carpeta encontrará varios sub-directorios, entre ellos:

* `.github` Esta carpeta contiene un archivo responsable de que la plataforma automatice la construcción del sitio al momento de subirlo a *GitHub*. **No tocar.**
* `archtypes` Esta carpeta es propia de *Hugo* y se guardan los tipos de páginas que se pueden crear. **No tocar.**
* `content` En esta carpeta se guardan los archivos de texto que formarán el sitio web.
* `i18n` En esta carpeta se guardan configuraciones dependiendo del lenguaje del sitio. El sitio solo soporta el lenguaje español. **No tocar.**
* `layouts` Esta carpeta contiene templetas internas de *Hugo*. **No tocar.**
* `resources` Esta carpeta contiene archivos multimedia que son generadas por *Hugo*. **No tocar.**
* `static` Esta carpeta contiene varios archivos que formarán parte de la ruta del sitio. Por lo general se guardan imágenes aquí.
* `themes` Esta carpeta contiene los temas estéticos del sitio. **No tocar.**

Los demás archivos como son `.gitignore`, `.gitmodules`, `LICENSE` y `README.md` son archivos propios del repositorio y no representan nada en el sitio. `config.toml` por otro lado es el archivo de configuración del generador del sitio. Por lo general no tiene que editar este archivo.

## Agregar contenido

### Estructura de `content`

Como se mencionó previamente, este proyecto utiliza *Hugo* para generar el sitio a partir de archivos de texto formateado en *Markdown*, no requiere de ningún tipo de código. Los archivos de texto que forman el contenido del sitio se guardan en `content`.

Adentro de esta carpeta podrá encontrar algunas sub-carpetas y archivos de formato `.md` (*Markdown*). Cada sub-carpeta (incluyendo `content`) debe de contener un archivo llamado `_index.md` el cual será el archivo principal para esta ruta. Hay que entender que la estructura de la carpeta `content` corresponde a la estructura del sitio, es decir que el archivo `content/_index.md` será accesible a través de `https://manos-al-codigo.github.io/`, mientras que `content/parte1/_index.md` y `content/parte1/subparte1.md` serán accesibles a través de `https://manos-al-codigo.github.io/parte1` y `https://manos-al-codigo.github.io/parte1/subparte1` respectivamente.

El primer nivel de sub-carpetas es usualmente utilizado para los ítems principales del menú lateral izquierdo y los archivos (que no sean `_index.md`) serán subítems de ese elemento en la barra.

Para que sirva de ejemplo, la estructura de la carpeta `content` de esta página es:

* `_index.md`
* `cuentas/`
  * `_index.md`
  * `correo.md`
  * `youtube.md`
  * `github-organization.md`
  * `google-analytics.md`
* `edicion/`
  * `_index.md`
  * `requisitos.md`
  * `sintaxis.md`
  * `manejo-contenido.md`

> Nótese que están listados en el orden de aparición para mejor visualización.

## Iniciar el cliente git y crear una rama nueva

Antes de comenzar a editar el sitio, debe de abrir el cliente git *GitHub Desktop* que se instaló previamente (si no lo ha hecho, diríjase a [Requisitos]({{< ref "requisitos.md" >}})). Asegúrese de que en la parte superior izquierda diga `manos-al-codigo.github.io`.

Le deberá aparecer una ventana tal como esta:

{{< figure src="/guia/img/edicion/github_desktop_6.png" >}}

Luego, haga click en el botón superior del medio que dice **Current branch**. Una ventana listando todas las ramas del proyecto deberá aparecer:

{{< figure src="/guia/img/edicion/github_desktop_7.png" >}}

> La imagen muestra que actualmente existe la rama `master` la cual es la principal y es ahi donde se tendrá que mover todos los cambios cuando estos ya estén listos.

Dele click al botón **New branch** o **Nueva rama** e ingrese un nombre pertinente a los cambios que va a realizar (tenga en cuenta que este nombre no puede incluir espacios).

{{< figure src="/guia/img/edicion/github_desktop_8.png" >}}

Finalmente se regresará a la ventana inicial con el botón del medio superior donde dice **Current branch** con el nombre de la rama recién creada.

{{< figure src="/guia/img/edicion/github_desktop_9.png" >}}

Listo, ahora usted está listo para editar el contenido del proyecto. Puede dejar esta ventana abierta o cerrarla si desea.

## Creación del archivo

### Cabecera

El archivo debe tener una cabecera que va a especificar la metadata de la página. Si se trata de una página que en la barra lateral deba de ser un ítem principal (como `1. Cuentas` y `2. Edición del sitio` en este caso), se debe de agregar la siguiente cabecera:

```markdown
+++
title = "Título de página (aparece como el nombre del ítem en la barra lateral)"
chapter = true
weight = 1 # Reemplace este número por el número del orden en la que deba de aparecer. Borre el texto a partir del símbolo #.
pre = "<b>1. </b>" # Reemplace el número por el mismo que puso arriba. Borre el texto a partir del símbolo #.
+++
```

Para otro tipo de archivos, la cabecera debería ser:

```markdown
+++
title = "Título de la sub-página"
weight = 1 # Reemplace este número por el número del orden en la que deba de aparecer. Borre el texto a partir del símbolo #.
+++
```

### Contenido

Después de agregar la cabecera usted está listo para incluir cualquier tipo de contenido que desee escribir. Para una descripción de la sintáxis que se debe seguir para estructurar estos archivos, diríjase a [Sintáxis Markdown]({{< ref "sintaxis.md" >}}) para más información.

## Probar la página localmente

Antes de subir sus cambios debería asegurarse de que el sitio puede generarse sin ningún tipo de error y que el contenido se muestre apropiadamente. Para eso, abra la carpeta principal del sitio `manos-al-codigo.github.io` donde la haya guardado en su computadora.

Luego, mientras mantiene el botón **SHIFT IZQUIERDO** haga click derecho en cualquier lado adentro de la carpeta (no le haga click derecho a un archivo sino al espacio vacío). Entre las opciones que tiene, haga click en **Abrir ventana PowerShell aquí**.

En la nueva ventana azul que apareció, copie y pegue el siguiente comando:

```text
hugo server --minify --ignoreCache
```

Le deberá aparecer una ventana semejante a esta:

{{< figure src="/guia/img/edicion/powershell_1.png" >}}

Cuando obtenga este mensaje, usted podrá acceder en su navegador a la página web localmente en [http://localhost:1313](http://localhost:1313). Mientras que esta ventana esté abierta, usted podrá hacer cualquier cambio en los archivos del sitio y la página web en su navegador su actualizará automáticamente.

## Guardar los cambios en el cliente git

Mientras vaya editando el sitio, es recomendable ir guardando sus cambios en el cliente git de vez en cuando. Por lo general cuando haya terminado de cambiar un archivo, guárdelo en el cliente y siga con su trabajo.

Cuando tenga cambios guardados, los podrá ver en el cliente *GitHub Desktop*:

{{< figure src="/guia/img/edicion/github_desktop_10.png" >}}

La barra lateral izquierda muestra todos los archivos que han sido cambiados y la derecha muestra una comparación entre la versión vieja y nueva.

Para guardar sus cambios, escriba una descripción de lo que está guardando donde dice **Escriba una descripción aquí** y luego haga click en el botón `Commit to nommbre-de-la-rama`. Asegúrese de que el botón tenga el nombre de su rama recién creada y que no diga `master`.

Listo, sus cambios han sido guardados (pero no subidos todavía). Cuando siga haciendo cambios en esta misma rama, repita el proceso que realizo en esta sección.

## Subir los cambios a la plataforma

Ya cuando haya terminado sus cambios y haya guardado todo lo que ha hecho, está usted listo para subir esos cambios a la plataforma. En el mismo cliente *GitHub Desktop*, después de haber guardado su último cambio, se le presentará una pantalla así:

{{< figure src="/guia/img/edicion/github_desktop_11.png" >}}

De click en el botón que dice **Push origin** para subir sus cambios a la plataforma.

Una vez subidos, tendrá una nueva opción como lo presenta la pantalla siguiente:

{{< figure src="/guia/img/edicion/github_desktop_12.png" >}}

De click en el botón que dice **Create Pull Request**, una nueva ventana en su navegador se abrirá como esta:

{{< figure src="/guia/img/edicion/github_pr_1.png" >}}

Donde dice `Escriba una corta descripción aquí` debe usted escribir una descripción de los cambios que ha hecho (Ejemplo: *nueva página del curso creada*). En la caja inferior puede usted escribir una descripción más amplia de sus cambios (esto es opcional). Cuando esté listo, de click en el botón **Create pull request**.

Después, se le aparecerá una lista de nueva información acerca de su rama. Al final, encontrará un botón que dice **Merge pull request**.

{{< figure src="/guia/img/edicion/github_pr_2.png" >}}

Una vez aplastado, se le presentará una confirmación. De click en **Confirm merge**.

{{< figure src="/guia/img/edicion/github_pr_3.png" >}}

Ya cuando la página se haya tornado morada con el texto **Merged**, le puede dar click al botón que dice **Delete branch** para remover la rama de la plataforma. Hasta este entonces sus cambios ya se han integrado en la rama principal del proyecto.

{{< figure src="/guia/img/edicion/github_pr_4.png" >}}

Finalmente, sus cambios estarán disponibles en el [sitio principal](https://manos-al-codigo.github.io) después de algunos minutos.

{{< figure src="/guia/img/edicion/site_done.png" >}}

{{% notice note %}}
Si por alguna razón sus cambios no se ven reflejados, vaya a la página del [repositorio](https://github.com/manos-al-codigo/manos-al-codigo.github.io) y de click en la pestaña llamada **Actions**. Se le presentará una página similar a esta:
![github-actions](/guia/img/edicion/github_action_1.png)
Si su cambio se muestra con una cruz roja, significa que algo sucedió al momento de generar el sitio. Trate de [probar su sitio en su propia máquina](#probar-la-página-localmente) y mire si funciona. Para cambio que deba realizar debe de reproducir los pasos para [guardar](#guardar-los-cambios-en-el-cliente-git) y [subir](#subir-los-cambios-a-la-plataforma).
{{% /notice %}}

## Qué hacer después de subir

Después de haber subido sus cambios y que estos estén reflejados en el [sitio principal](https://manos-al-codigo.github.io), regrese al cliente *GitHub Desktop* y en la parte superior en el medio, de click al botón **Current branch** y cámbiese a `master`.

{{< figure src="/guia/img/edicion/github_desktop_12.png" >}}

Luego, en la parte superior, de click en el tercer botón que dice **Fetch origin**. Después de haberse cargado, este botón cambiará a **Pull origin**, de click nuevamente.

{{< figure src="/guia/img/edicion/github_desktop_13.png" >}}

Después de haber realizado esto, estará listo para reproducir los pasos vistos en las secciones [iniciar el cliente](#iniciar-el-cliente-git-y-crear-una-rama-nueva), [guardar los cambios](#guardar-los-cambios-en-el-cliente-git) y [subir los cambios](#subir-los-cambios-a-la-plataforma) para cada cambio subsiguiente que vaya a realizar.

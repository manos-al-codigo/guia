+++
title = "Sintáxis Markdown"
weight = 2
+++

En esta página se presenta un ejemplo de cada forma posible para formatear texto y cómo obtenerlo con *Markdown*.

## Títulos

Los títulos se construyen con un `#` por cada nivel del título.

Esto:

``` markdown
# Título h1
## Título h2
### Título h3
#### Título h4
##### Título h5
###### Título h6
```

Se renderiza así:

# Título h1
## Título h2
### Título h3
#### Título h4
##### Título h5
###### Título h6

## Reglas horizontales

Se puede separar contenido con una regla horizontal con cualquiera de las siguientes opciones:

```markdown
---
___
***
```

Cada uno de estos se renderiza así:

---

## Texto normal

Un párrafo de texto normal se escribe directamente sin ningún tipo de notación especial.

Esto:

```markdown
Lorem ipsum dolor sit amet, graecis denique ei vel, at duo primis mandamus. Et legere ocurreret pri, animal tacimates complectitur ad cum. Cu eum inermis inimicus efficiendi. Labore officiis his ex, soluta officiis concludaturque ei qui, vide sensibus vim ad.
```

Se renderiza así:

Lorem ipsum dolor sit amet, graecis denique ei vel, at duo primis mandamus. Et legere ocurreret pri, animal tacimates complectitur ad cum. Cu eum inermis inimicus efficiendi. Labore officiis his ex, soluta officiis concludaturque ei qui, vide sensibus vim ad.

## Énfasis de texto

### Negrita

Para escribir texto en **negrita** se lo puede realizar con:

```markdown
**esto está en negrita**
```

Lo cual se renderiza así:

**esto está en negrita**

### Itálicas

Para escribir texto en *itálica* se lo puede realizar con:

```markdown
*esto está en itálica*
```

Lo cual se renderiza así:

*esto está en itálica*

### Atravesado

Para escribir texto  ~~atravesado~~ se lo puede realizar con:

```markdown
~~esto está en atravesado~~
```

Lo cual se renderiza así:

~~esto está en atravesado~~

## Bloques de paráfrasis

Se puede formatear texto como un bloque independiente.

Esto:

```markdown
> Esto es un bloque independiente.
```

Se renderiza así:

> Esto es un bloque independiente.

Se pueden tener múltiples niveles de estos bloques:

Esto:

```markdown
> Esto es un bloque independiente.
> > Y este un bloque interno.
```

Se renderiza así:

> Esto es un bloque independiente.
> > Y este un bloque interno.

## Notas

Se puede agregar un recuadro de notas de distintos colores.

### Note

Esto:

```markdown
{{%/* notice note */%}}
Una nota.
{{%/* /notice */%}}
```

Se renderiza así:

{{% notice note %}}
Una nota.
{{% /notice %}}

### Info

Esto:

```markdown
{{%/* notice info */%}}
Una información.
{{%/* /notice */%}}
```

Se renderiza así:

{{% notice info %}}
Una información.
{{% /notice %}}

### Tip

Esto:

```markdown
{{%/* notice tip */%}}
Un tip.
{{%/* /notice */%}}
```

Se renderiza así:

{{% notice tip %}}
Un tip.
{{% /notice %}}

### Warning

Esto:

```markdown
{{%/* notice warning */%}}
Una alerta.
{{%/* /notice */%}}
```

Se renderiza así:

{{% notice warning %}}
Una alerta.
{{% /notice %}}

## Listas

### Sin orden

Una lista cuyo orden no importa se puede representar con cualquiera de los siguientes símbolos:

```markdown
* Elemento de la lista.
- Elemento de la lista.
+ Elemento de la lista.
```

Un elemento de una lista también puede ser otra lista.

Esto:

```markdown
+ Elemento 1.
+ Elemento 2.
+ Elemento 3.
  - Elemento 3.1.
  - Elemento 3.2.
+ Elemento 4.
```

Se renderiza así:

+ Elemento 1.
+ Elemento 2.
+ Elemento 3.
  - Elemento 3.1.
  - Elemento 3.2.
+ Elemento 4.

### Ordenada

Una lista cuyo orden importa se puede representar como una lista precedida por números por cada elemento.

Esto:

```markdown
1. Primero
2. Segundo
3. Tercero
4. Cuarto
```

Se renderiza así:

1. Primero
2. Segundo
3. Tercero
4. Cuarto

## Bloques de código

Se puede representar un bloque independiente para mostrar un ejemplo de código.

### Bloques en la misma línea

Una línea puede contener un `ejemplo de código en la misma línea`.

Esto:

```markdown
Aquí hay un `ejemplo` en la misma línea.
```

Se renderiza así:

Aquí hay un `ejemplo` en la misma línea.

### Bloques de múltiples líneas

Un bloque de código independiente se envuelve con ```` ``` ````.

Un texto envuelto con estos símbolos se renderiza así:

```text
Esto es un código
de múltiples líneas.
```

### Subrayado de sintáxis

Los bloques de código independientes pueden mostrar código con subrayado de sintáxis en base al lenguaje. Para esto, después del primer ```` ``` ```` que envuelve al código se le especifica el lenguaje del código (Ejemplo: `js`, `html`, `json`...). Se puede encontrar [aquí](https://highlightjs.org/download/#download-form) una lista de los lenguajes soportados.
 
Un texto `HTML` envuelto en estos símbolos se renderiza así:

```html
<html>
  <body>
    <p>Aquí hay un párrafo en HTML.</p>
  </body>
</html>
```

## Tablas

Se puede representar tablas agregando `|` entre cada columna y separando la primera fila por `---` por cada celda.

Esto:

```markdown
| Primera columna | Segunda columna |
| --------------- | --------------- |
| Celda 1,1       | Celda 1,2       |
| Celda 2,1       | Celda 2,2       |
| Celda 3,1       | Celda 3,2       |
```

Se renderiza así:

| Primera columna | Segunda columna |
| --------------- | --------------- |
| Celda 1,1       | Celda 1,2       |
| Celda 2,1       | Celda 2,2       |
| Celda 3,1       | Celda 3,2       |

## Links (Hipervínculos)

### Recurso externo

Se puede agregar un hipervínculo a un recurso externo.

Esto:

```markdown
[Texto del Link](http://link-al-recurso.com)
```

Se renderiza así:

[Texto del Link](http://link-al-recurso.com)

### Recurso interno

Se puede agregar un hipervínculo a un recurso interno. El recurso interno se resuelve desde el documento que se está editando.

Sea una estructura de documentos así:

+ pagina1.md
+ pagina2/
  + pagina2-1.md
  + pagina2-2.md

Si desde `pagina2-2.md` se quiere agregar un hipervínculo a `pagina1.md`, se realiza esto:

```markdown
[Texto del Link]({{</* ref "../pagina1.md" */>}})
```

Se renderiza así:

[Texto del Link]("#")

{{% notice warning %}}
Si el `ref` apunta a un archivo que no existe, el compilador del sitio mostrará un error.
{{% /notice %}}

### Recurso de la misma página

Se puede agregar un hipervínculo a un recurso que se encuentra en la misma página. Este recurso debe ser un título en la misma página para el cual se le debe poner todo en minúsculas y reemplazar cualquier espacio por un guión `-`.

Esto:

```markdown
[Link a la misma página](#énfasis-de-texto)
```

Se renderiza así:

[Link a la misma página](#énfasis-de-texto)

> Este link apunta a la sección **Énfasis de texto** en esta misma página.

## Imágenes

Se puede agregar imágenes a la página.

### Imagen externa

Una imagen externa es una imagen que no se encuentre guardada en los archivos de este sitio, se obtiene generalmente por su URL.

Esto:

```markdown
![texto para cuando no se puede presentar la imagen](https://raw.githubusercontent.com/manos-al-codigo/assets/master/logo_with_text/logo_with_text_2000x1000-black.png)
```

Se renderiza así:

![texto para cuando no se puede presentar la imagen](https://raw.githubusercontent.com/manos-al-codigo/assets/master/logo_with_text/logo_with_text_2000x1000-black.png)

### Imagen interna

Una imagen interna es una imagen que se encuentre guardada en los archivos de este sitio, más específicamente adentro de la carpeta `static`.

La dirección de la imagen local se obtiene al sumar las siguientes cosas:

+ `/` Para apuntar al inicio del sitio. En este caso, es `https://manos-al-codigo.github.io/`
+ `guia/` Si es que el sitio es parte de la guia, en caso contrario no se agrega nada.
+ `la dirección/hasta/la/imagen`. La dirección para encontrar la imagen desde la carpeta `static`. Si la imagen se llama `analytics_3.png` y se encuentra adentro de la carpeta `cuentas` que está dentro de `img` que a su vez está adentro de `static`, la dirección de la imagen será: `static/img/cuentas/analytics_3.png`.

Esto:

```markdown
{{</* figure src="/guia/img/cuentas/analytics_3.png" title="Páginas más visitadas." */>}}
```

Se renderiza así:

{{< figure src="/guia/img/cuentas/analytics_3.png" title="Páginas más visitadas." >}}

### Desactivar la presentación de la imagen al hacerle click

Cuando se le hace click a una imagen en este sitio por lo general se presenta en grande en una ventana independiente. Para eliminar este comportamiento, se agrega: `?featherlight=false` al URL de la imagen.

Esto:

```markdown
![texto para cuando no se puede presentar la imagen](https://raw.githubusercontent.com/manos-al-codigo/assets/master/logo_with_text/logo_with_text_2000x1000-black.png?featherlight=false)
```

Se renderiza así:

![texto para cuando no se puede presentar la imagen](https://raw.githubusercontent.com/manos-al-codigo/assets/master/logo_with_text/logo_with_text_2000x1000-black.png?featherlight=false)

Hacerle click a la imagen no hace nada.

### Cambiar el tamaño de la imagen

Por defecto, las imágenes toman su tamaño normal en la página a menos que esta sea muy pequeña para la imagen, en cuyo caso la imagen tomará todo el espacio horizontal que pueda, manteniendo su relación con el tamaño vertical para que no se vea estirada.

Se puede cambiar el tamaño de la imagen agregando al final de la URL de la imagen `?height=<tamaño>` para cambiar la altura de la imagen o `?width=<tamaño>` para cambiar su largo. Se pueden encadenar estos parámetros, reemplazando el `?` en los parámetros que no sean el primero por `&`.

Las unidades del tamaño son las de `CSS`, más información sobre estas unidades se puede encontrar [aquí](https://uniwebsidad.com/libros/css/capitulo-3/unidades-de-medida).

```markdown
![texto para cuando no se puede presentar la imagen](https://raw.githubusercontent.com/manos-al-codigo/assets/master/logo_with_text/logo_with_text_2000x1000-black.png?featherlight=false&with=200px&height=100px)
```

Se renderiza así:

![texto para cuando no se puede presentar la imagen](https://raw.githubusercontent.com/manos-al-codigo/assets/master/logo_with_text/logo_with_text_2000x1000-black.png?featherlight=false&with=200px&height=100px)

## Videos de YouTube

Se pueden agregar videos de *YouTube* en las páginas. Lo único que se debe conocer es el identificador del video el cual es la cadena alfanumérica al final del link del video.

Ejemplo: Para el video `https://www.youtube.com/watch?v=y-C6nRCbkSA` el identificador es `y-C6nRCbkSA`.

Para agregar el video, se utiliza esto:

```markdown
{{</* youtube y-C6nRCbkSA */>}}
```

Lo cual se renderiza así:

{{< youtube y-C6nRCbkSA >}}

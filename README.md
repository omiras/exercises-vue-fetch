# Ejercicios Vue que usan fetch

Abre con Live Server cada uno de los ficheros index.html del ejercicio a realizar.

## ¿Algo va mal?

0. Intenta no pedir la solución directa a la IA.
1. Asegúrate de que has hecho bien el [setup](https://vuejs.org/guide/quick-start.html#using-the-global-build), englobando todo el HTML por un contenedor `<div id="app"></div>`.
2. Echa un vistazo a la consola del navegador. Normalmente sucede que nos olvidamos de importar algo o hay un error de sintaxis.
3. Para este tipo de ejercicios, mira también la pestaña "Red" o "Network" en el navegador web. Puede que encuentres un error en el momento de realizar la llamada a la URL.

<img src="https://oscarm.tinytake.com/media/17910d3?filename=1753086794204_TinyTake21-07-2025-10-33-00_638886835924646084.png&sub_type=thumbnail_preview&type=attachment&width=615&height=486" title="Powered by TinyTake Screen Capture"/>

### 0-random-joke-api-category

[Demo parecida](https://omiras.github.io/random-joke-api-project/)

Amplía las funcionalidades de la app que muestra "chistes" de Chuck Norris. 
Permite que un usuario pueda escoger la categoría del chiste. Esto lo conseguimos mediante el parámetro _category_ de la _query string_.
Por ejemplo, si hacemos una peticion con esta URL https://api.chucknorris.io/jokes/random?category=animal obtendremos un chiste aleatório de la categoría _animal_ 
Tan solo hay que implementar adecuadamente la función _getJoke_ para que funciona la app.

**Bonus (no hacer los bonus hasta no acabar todos los ejercicios)**

1. Obtén todas las categorías disponibles de forma dinámica, haciendo una petición a `https://api.chucknorris.io/jokes/categories` y mediante la directiva v-for, crea tantos 'option' como categorías existan (vas a necesitar también usar el hook [onMounted](https://vuejs.org/api/composition-api-lifecycle#onmounted)).
2. Verifica la documentación de la [API de Chuck Norris](https://api.chucknorris.io/). Por ejemplo, con esta petición podemos obtener todos los chistes que contienen [el término "potatoe"](https://api.chucknorris.io/jokes/search?query=potatoe). ¿Podrías añadir un input que permita también realizar peticiones a la API dado un término de búsqueda? ¿Puedes hacer que funcione el selector de categoría y este input a la vez?

### 1-random-photos

[URL ejercicio original](https://www.100jsprojects.com/project/photo-gallery)
[Demo](https://demo.100jsprojects.com/photo-gallery)

<details>
  <summary>URL de la petición</summary>
  <p>La URL que tenéis que usar es `https://api.unsplash.com/photos?per_page=1&client_id=aMKCCPd9KAQml9r1-a8DuvO6La76rT2Gg54XhDmtiz4`. En el parámetro _per_page_ se indica cuántas fotografías quieres recuperar. Esta API necesita de registro para obtener un *client_id*. Se pide usar la API con moderación ya que está registrada a mi nombre.</p>
</details>

1. Haz que cada vez que hagamos clic en el botón, se cargue 1 foto aleatoria de https://unsplash.com/ (ignora el input por el momento). Usa la directiva v-for para mostrar dicha imagen.
2. Luego, usa la directiva v-model adecuadamente para gobernar el input.
3. Asocia la directiva @click al botón para que haga un _fetch_ a la URL correspondiente teniendo en cuenta el número de imágenes que queremos recuperar.
3. Investiga el JSON devuelto de la petición para saber cómo obtener la URL de la imagen.

**Ideas para funcionalidades extra**

- Si investigas el JSON verás que aparece el nombre del autor de la imagen, texto alternativo de la imagen y otra información de interés. [Ejemplo](https://api.unsplash.com/photos?per_page=1&client_id=aMKCCPd9KAQml9r1-a8DuvO6La76rT2Gg54XhDmtiz4). Usa esa información para enriquecer la app.

### 2-image-search-app

[URL ejercicio original](https://www.100jsprojects.com/project/photo-gallery)
[Demo](https://demo.100jsprojects.com/photo-gallery)

1. Configura Vue para que gobierne adecuadamente el input de búsqueda mediante la directiva v-model.
2. Al hacer clic en el botón, se obtienen 10 imágenes de la API que cumplan con el criterio de búsqueda.
3. Usa adecuadamente la directiva v-for para generar tantos `<div class="results">` como imágenes recuperamos de la API.

<details>
  <summary>URL de la petición</summary>
  <p>La URL que tenéis que usar es `https://api.unsplash.com/search/photos?page=1&query=dog&client_id=aMKCCPd9KAQml9r1-a8DuvO6La76rT2Gg54XhDmtiz4`.
  En el parámetro _query_ se indica el término de búsqueda. En el ejemplo anterior, queremos obtener imágenes de la API que contengan la palabra "dog". Esta API necesita de registro para obtener un *client_id*. Se pide usar la API con moderación ya que está registrada a mi nombre.</p>
</details>




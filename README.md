# Despliegue en GH Pages
## Paso 1
Modificamos los siguientes ajustes en el fichero `_config.yml`:
```yaml
url                      : https://ull-mii-sytws-2223.github.io
baseurl                  : "/intro2sd-claudio_nestor-yanes-mesa-alu0101229942/"
```
## Paso 2
Habilitamos GH pages en los ajustes del repo, seleccionando la rama que creamos conveniente.
![image](https://user-images.githubusercontent.com/9874071/195960484-f2ed6a5a-d461-49fa-81da-5ebfc9c143d0.png)
##Paso 3
Editar el fichero `_posts/2022-10-01-informe.md` para añadir el resumen del libro.
##Paso 4
Listo, la página esta dispnible en https://ull-mii-sytws-2223.github.io/intro2sd-claudio_nestor-yanes-mesa-alu0101229942/post%20formats/informe/.
# Despligue Netlify
El despligue a Netlify rquiere que el repo sea publico.
Los paso para añadir el proyecto son los siguientes:

Selecionar el importar proyecto de Git.

![image](https://user-images.githubusercontent.com/9874071/195960649-2cfd0b59-275f-44d4-8837-d8163194e32a.png)

Seleccionar Github.

![image](https://user-images.githubusercontent.com/9874071/195960671-f80ac306-539a-44d5-9572-47ff066cb0ec.png)

Añadir otro organización.

![image](https://user-images.githubusercontent.com/9874071/195960686-6bd70f45-c961-4a14-94cd-6d943ab03893.png)

Seleccionar la organización de clase.

![image](https://user-images.githubusercontent.com/9874071/195960699-9e4f1adb-3e9b-452d-93aa-a11d29b2ac46.png)
Solo dar permisos al repostiro deaseado (opcinal pero recomendado).

![image](https://user-images.githubusercontent.com/9874071/195960729-8468a188-5696-4c9a-b050-8f9e6a51bc85.png)
Configurar los parametros tal y como se ven en la imagen.

![image](https://user-images.githubusercontent.com/9874071/197417219-27f1bc04-3bcf-4ab6-a0bb-6ecb55d58772.png)

Listo, ahora solo queda esperar y el sitio estara dispnible en Netlify. URL de ejemplo: https://intro2sd-cy.netlify.app/


# Despliegue de la ágina personal con Github
## Paso 1
Crear un repositorio con el nombre `usuario.github.io`, donde usuario es el usuario de Github, en mi caso alu0101229942.
![image](https://user-images.githubusercontent.com/9874071/195961290-a3ed31b8-9522-4b58-8820-7b0f81854fb9.png)
## Paso 2
Subimos un archivo HTML que sirva como raiz de nuestro sitio.
![image](https://user-images.githubusercontent.com/9874071/195961397-9f38a285-d1f1-488c-968a-08a7fffd204b.png)
![image](https://user-images.githubusercontent.com/9874071/195961434-982f639e-ef70-4831-be1a-81065361d1e0.png)
![image](https://user-images.githubusercontent.com/9874071/195961449-858fc1fe-b163-4813-ae32-0dcd922498f7.png)
# Paso 3
Siga el paso 2 de [Despliegue en GH Pages](#paso-2)
# Paso 4
Listo, visite el sitio en https://alu0101229942.github.io/.

# Crear una colección
Lo primero es modifical el archivo `_config.yml` y editar la entrada de `collections` para añadir las siguientes lineas:
```yaml
micoleccion:
    output: true
    permalink: /:collection/:path/
```
Luego tenemos que crear una carpeta llamada `_micoleccion` en la raiz del proyecto.

Añadiremos entradas a nuestra colleción creando archivos en dicha carpeta, uno por entrada. Para seguir la convencion del tema, deberemos añadir un frontmatter a cada archivo con un  titulo en la clave `title` y un resumen en la clave `excerpt`, aunque no es obligtorio.

Podremos acceder a nuestra colección desde cualquier lugar usando `site.micoleccion`. Por ejemplo podemos crear tarjetas de la colleción con el siguiente códgio
```liquid
    {% for e in site.portfolio %}
        <div class="card">
            {% if e.header.image %}
            <img src="{{site.baseurl}}{{e.header.image}}" alt="" />
            {% endif %}
            <h3>{{e.title}}</h3>
            {{e.excerpt}}
        </div>
    {% endfor %}
```
Notese que en este ejempo `e.header.image` y `e.title` son propiedades definidas en el frontmatter de las entradas de la colleción.
# Acceder a datos de un archivo
Podemos acceder a ifnormación que tengamos guardada en archivos de datos en formato JSON y YANL, entre otros. Para ello solo tenemos que guardarlos en el directorio `_data` y ya podremos acceder a su infromación usando `site.data.my-nombre-de-archivo`. lA información la podemos trbajar con liquid de la misma forma que hacemos con las colleciones, por ejemplo podemos interar sobre una lista de la siguiente forma:
```liquid
<ul>
    {% for spell in site.data.spells-phb.spell %}
    <li>{{spell.name}}</li>
    {% endfor %}
</ul>
```
# Personalizando la configuración
## Configuración basica
Lo primero es modifcar el nombre del autor, el titulo del sitio, el lenguaje, el repositorio y sobre todo la *url* y *baseurl*. Esto se cambia en las primeras lineas de la configuración.
En mi caso lo he dejado así:
```yaml
locale                   : "es-ES"
title                    : "Introducción al Desarrollo de Sistemas"
title_separator          : "-"
subtitle                 : "A Jekyll site"
name                     : &name "Claudio Yanes"
description              : &description "A Jekyll site with minimal-mistakes theme."
url                      : https://ull-mii-sytws-2223.github.io
baseurl                  : "/intro2sd-claudio_nestor-yanes-mesa-alu0101229942" 
repository               : "ULL-MII-SYTWS-2223/intro2sd-claudio_nestor-yanes-mesa-alu0101229942"
```
## Tema
Podemos cambiar la *skin* del tema con la propiedad `minimal_mistakes_skin`.
Acepta los sisguientes valores:
* air
* aqua
* contrast
* dark
* dirt
* neon
* mint
* plum
* sunrise
En mi caso he usado el tema neon asi que mi configuación luce así:
```yaml
minimal_mistakes_skin    : "neon" 
```
## Activar comentarios
Para esot tenemos que ir a la sección `comments`de la configración. Ahí elegiremos utterances como proveedor y configuraremos los ajustes relativos a este.
```yaml
comments:
  provider               : "utterances" # false (default), "disqus", "discourse", "facebook", "staticman_v2", "staticman", "utterances", "giscus", "custom"
  # snipped
  utterances:
    theme                : "github-dark" # "github-light" (default), "github-dark"
    issue_term           : "pathname" # "pathname" (default)
    label                : "Comments"
```
Recordar que es importante darle acceso al repositorio a la apliación de utterances en Github y que el campo `repository` que se encuenra al principio de la configuración apunte a nuestro repositorio.
## Información del autor
en el apartado `twitter`, `author` y `footer` podemos cambiar los enlaces a redes sociales que aparecen en la página, así como información relacionada con nosotros.
```yaml
twitter:
  username               : &twitter "claudio4"

author:
  name             : *name # *name is a YAML reference pointing to the &anchor earlier
  avatar           : "https://www.claudio4.com/assets/profile.jpg"
  bio              : "A Student"
  location         : "Islas Canarias"
  links:
    - label: "Website"
      icon: "fas fa-fw fa-link"
      url: "https://claudio4.com"
    - label: "Twitter"
      icon: "fab fa-fw fa-twitter-square"
      url: "https://twitter.com/claudio4sv"
    - label: "GitHub"
      icon: "fab fa-fw fa-github"
      url: "https://github.com/claudio4"


footer:
  links:
    - label: "Twitter"
      icon: "fab fa-fw fa-twitter-square"
      url: "https://twitter.com/claudio4sv"
    - label: "GitHub"
      icon: "fab fa-fw fa-github"
      url: "https://github.com/claudio4"
```
## Página 404 personalizada
Los contenidos del archivo `_pages/404.md` seran los que se muestren en el caso de no encontrarse la página solicitada por el usuario. En mi caso se ha editado para cargar imagenes aaleatorias publicadas en [r/ProgrammerHumor](https://www.reddit.com/r/ProgrammerHumor). Esto se hace con el siguiente código
```javascript
async function getPost() {
  // Obtener un post random
  const post = await fetch("https://www.reddit.com/r/ProgrammerHumor/random.json")
    .then( resp => resp.json())

  // Si el post no tiene imagen devolvemos null
  const postEntry = post.find(e => e?.data?.children?.[0]?.data?.url_overridden_by_dest)
  if (!postEntry) {
    return null
  }
  const postData = postEntry.data.children[0].data

  return {image: postData.url_overridden_by_dest, url: postData.url}
}
async function loadMeme() {
  let post = null

  // pedimos posts hasta que obtengamos uno con imagen.
  while (!post) {
    post = await getPost()
  }
  
  // Preparamos el html a insertar
  let a = document.createElement('a')
  a.href = post.url
  a.rel = "noreferrer noopener"
  a.target = "_blank"
  let img = document.createElement('img')
  // Si la imagen es invalida y falla al cargar reiniciamos la operación.
  img.addEventListener('error', loadMeme)
  img.src = post.image
  a.appendChild(img)
  document.getElementById('meme-container').replaceChildren(a)
}
```
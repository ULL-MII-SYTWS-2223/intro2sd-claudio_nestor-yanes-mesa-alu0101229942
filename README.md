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
El despligue a Netlify no es posible ya que require una cuenta premiun, que no viene incluida en el Github student pack. Es posible que se pueda circunventar esta limimitación usando la herramienta de CLI de Netlify y GH Actions, pero se ha considerado muy complejo para esta prática.

A continuación se muestran los pasos a tomar hasta encontrarse con el *paywall*.
![image](https://user-images.githubusercontent.com/9874071/195960649-2cfd0b59-275f-44d4-8837-d8163194e32a.png)
![image](https://user-images.githubusercontent.com/9874071/195960671-f80ac306-539a-44d5-9572-47ff066cb0ec.png)
![image](https://user-images.githubusercontent.com/9874071/195960686-6bd70f45-c961-4a14-94cd-6d943ab03893.png)
![image](https://user-images.githubusercontent.com/9874071/195960699-9e4f1adb-3e9b-452d-93aa-a11d29b2ac46.png)
![image](https://user-images.githubusercontent.com/9874071/195960729-8468a188-5696-4c9a-b050-8f9e6a51bc85.png) 
![image](https://user-images.githubusercontent.com/9874071/195960784-c60e0e9c-717b-4759-8624-feaa441cf0fa.png)
![image](https://user-images.githubusercontent.com/9874071/195960852-3d285373-e979-4b33-b86e-ca78a9c0e0a0.png)

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
Siga el paso 2 de [Despliegue en GH Pages]()
# Paso 4
Listo, visite el sitio en https://alu0101229942.github.io/.

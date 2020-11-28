# GitHub

---

## Entorno de trabajo Ramas y Tags

### Creando una rama:

A continuación se mostrara una descripción breve de como crear una rama en git y enviarla a github. Es importante que este proceso solo lo haga 1 persona por equipo. 

**Paso 1 :**

Se pueden crear las ramas de dos formas, como se muestra a continuación

```docker
git branch nombre-de-la-rama 
git checkout -b nombre-de-la-rama
```

**Paso 2 :**

Conocer cuales son las ramas que existen, se puede observar la información con alguno de los siguientes comandos

```docker
git branch
git show-branch
git show-branch --all
```

**Paso 3 :**

Enviar las ramas a github, este paso se debe hacer con cada una de las ramas que se fueron creadas en el paso numero 1

```docker
git push origin nombre-de-la-rama
```

**Paso 4 :** 

Entrar a una rama especifica

```docker
git checkout nombre-de-la-rama
```

Luego de ello, puede tomar la decisión de subir un archivo a esa rama especifica.

**Paso 5 :**

Enviar archivos que se encuentran en la rama especifica

```docker
git pull origin nombre-de-la-rama
git push origin nombre-de-la-rama
```

---

### Tags y versiones en Git y GitHub

Los tags o etiquetas nos permiten asignar versiones a los commits con cambios más importantes o significativos de nuestro proyecto.

**Paso 1:**

Antes de crear un tag, debemos obtener el id del commit que haga referencia la información que deseamos enviar al tag.

```docker
git log --all
```

Seleccionar y copiar el Id del commit

**Paso 2 :**

Creamos el tag, le ponemos un nombre con el prefijo **-a** nombre_del_tag, le pasamos una descripción al tag (-m) y por ultimo le agregamos el id del commit que se obtuvo en el paso numero 1

```docker
git tag -a nombre-del-tag id-del-commit.
```

**por ejemplo:**

```docker
git tag -a v0.1 -m "Resultado del primer script de la API de Facebook" 1d30481d2e339166b2384ef5961e67df27d6db46
```

**Paso 3 :**

Visualizar todos los tags que se han creado

```docker
git tag
```

**Paso 4 :**

Publicar los tags en el repositorio remoto:

```docker
git push origin --tags
```

**Comandos para trabajar con etiquetas:**

- Crear un nuevo tag y asignarlo a un commit: **`git tag -a nombre-del-tag id-del-commit`**.
- Borrar un tag en el repositorio local: **`git tag -d nombre-del-tag`**.
- Listar los tags de nuestro repositorio local: **`git tag`** o **`git show-ref --tags`**.
- Publicar un tag en el repositorio remoto: **`git push origin --tags`**.
- Borrar un tag del repositorio remoto: `git tag -d nombre-del-tag` y **`git push origin :refs/tags/nombre-del-tag`**.
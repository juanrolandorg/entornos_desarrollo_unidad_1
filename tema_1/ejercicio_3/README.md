# Trabajo con ramas en Git
Trabajo con Ramas en Git
**La gestion de ramas es exclusiva de Git?**

No, otros sistemas de control de versiones tambien usan ramas, pero Git las maneja de forma mas eficiente gracias a su sistema de referencias ligeras.

**En que consiste el trabajo con ramas?**

Consiste en crear lineas de desarrollo independientes para trabajar en nuevas funciones, sin afectar la rama principal.

**Caracteristicas del trabajo en ramas de Git**

Crear ramas es rapido y ocupa poco espacio.

Permite trabajar de forma paralela.

Facilita fusionar (merge) cambios entre ramas.

Permite probar cosas sin romper la version estable.

**Metadatos que almacena un commit**

Un commit guarda:

Autor

Fecha

Mensaje descriptivo

Hash (identificador unico)

Referencia a los padres (commits anteriores)

**Padres de un commit**

Un commit puede tener:

1 padre = commit normal

2 o mas padres = commit de fusion (merge)

 **Que es una rama?**

Una rama es un apuntador (puntero) a un commit especifico. Es como una linea de tiempo separada para trabajar en una caracteristica o idea.

**Rama por defecto**

Se llama main.
Se crea automaticamente al iniciar un repositorio con git init.

**Como avanza una rama?**

La rama avanza cuando haces nuevos commits.

**Comandos basicos d rama**
Git actualiza el puntero de la rama para que apunte al ultimo commit.
| Descripcion                                  | Comando                                      |
| -------------------------------------------- | -------------------------------------------- |
| Crear una rama (sin cambiarte a ella)        | `git branch nombre-rama`                     |
| Cambiar de rama                              | `git checkout nombre-rama`                   |
| Ver ramas en modo grafico                    | `git log --graph --oneline --decorate --all` |
| Crear y saltar a una nueva rama              | `git checkout -b nombre-rama`                |
| Fusionar cambios de otra rama                | `git merge nombre-rama`                      |
| Ver ramas                                    | `git branch`                                 |
| Borrar una rama                              | `git branch -d nombre-rama`                  |
| Forzar el borrado (aunque no este fusionada) | `git branch -D nombre-rama`                  |
| Ver ultima confirmacion de cada rama         | `git branch -v`                              |
| Filtrar ramas fusionadas                     | `git branch --merged`                        |
| Mostrar ramas remotas                        | `git branch -r`                              |

r
**Tipos de fusiones**
*Fast Forward (avance rapido)*
Cuando la rama actual no tiene commits nuevos, Git simplemente mueve el puntero al final de la otra rama.
No crea un commit nuevo.

*Fusion a tres bandas*
Ocurre cuando ambas ramas tienen commits diferentes. Git necesita comparar las tres versiones:
El ancestro comun
La rama actual
La rama que se fusiona
Crea un nuevo commit de fusion.
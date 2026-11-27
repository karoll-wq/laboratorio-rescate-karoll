# Bitácora del laboratorio de rescate.

- ¿qué muestra cada comando?
información sobre los commit que se han echo.

- ¿Qué es el código que aparece al inicio de cada
commit?
el identificador de cada commit.

- ¿Por qué el segundo git diff no mostró nada?
Porque git add ya pasó los cambios al staging y git diff solo muestra los que no están preparados.

- ¿Qué muestra --staged?
Los cambios preparados que irán en el próximo commit.

- ¿Qué hace git restore? 
restaura los archivos eliminados por accidente.

- ¿Funcionaría si nunca hubieras hecho commit de ese archivo?
si.

- ¿Qué diferencia hay entre git restore y git restore --staged?
git restore: descarta tus cambios y vuelve al último commit (los pierdes).

git restore --staged: quita el archivo del staging (deshace el git add), pero conserva tus cambios.

- ¿Git revert borró el commit equivocado o creó uno nuevo?
Creó uno nuevo. El commit equivocado sigue en el historial; el nuevo commit solo deshace sus cambios.

- ¿Por qué es la opción segura después de un push?
Porque no reescribe el historial. Los demás integrantes ya pueden tener ese commit, y con git revert pueden hacer git pull sin conflictos. En cambio, git reset borraría commits que otros ya descargaron y rompería el repositorio compartido.

- ¿Qué diferencia hay entre git reset --soft y git revert?
  `git reset --soft` mueve la rama a un commit anterior y borra commits del historial, pero deja los cambios en el staging. `git revert` no borra nada: crea un commit nuevo que deshace los cambios de otro commit.

- ¿Cuándo se usa cada uno?
  `git reset --soft` se usa en commits locales que aún no se han subido con push (por ejemplo, para corregir un mensaje o juntar commits). `git revert` se usa cuando el commit ya se subió, porque no reescribe el historial y es seguro para el equipo.

  - ¿Para qué sirve git stash?
  Guarda temporalmente los cambios sin commit y deja la carpeta de trabajo limpia, para poder cambiar de rama sin perder nada.

- ¿Qué hace git stash pop?
  Recupera los últimos cambios guardados con `git stash`, los vuelve a aplicar en tu carpeta de trabajo y los elimina de la lista del stash.
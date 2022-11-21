# ejemploGit3

1.Creamos un repositorio nuevo en GitHub con un README y un .gitignore.

![ejGit3_captura_1](https://user-images.githubusercontent.com/95747897/203097965-a7da5004-560b-48a5-a540-60691b8467e9.png)

2. Creamos un proyecto nuevo (se me olvidó marcar "Create Git Repository", pero luego hize un git init en la carpeta del proyecto).

![ejGit3_captura_2](https://user-images.githubusercontent.com/95747897/203098238-4500f6cc-f234-4c37-98c9-ad6aadbfe722.png)

```
a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (master)
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   .idea/.gitignore
        new file:   .idea/misc.xml
        new file:   .idea/modules.xml
        new file:   .idea/vcs.xml
        new file:   ejercicioGit3.iml
        new file:   src/Main.java
´´´
3. Añadimos el repositorio de GitHub como remoto e intentamos hacer un pull:

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (master)
$ git remote add origin https://github.com/brimacias/ejemploGit3.git

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (master)
$ git pull origin main
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), 838 bytes | 0 bytes/s, done.
From https://github.com/brimacias/ejemploGit3
 * branch            main       -> FETCH_HEAD
 * [new branch]      main       -> origin/main
 
 4. Quitamos los cambios del stage:

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (master)
$ git rm --cached -r .
rm '.gitignore'
rm '.idea/.gitignore'
rm '.idea/misc.xml'
rm '.idea/modules.xml'
rm '.idea/vcs.xml'
rm 'README.md'
rm 'ejercicioGit3.iml'
rm 'src/Main.java'

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (master)
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    .gitignore
        deleted:    README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        .idea/
        README.md
        ejercicioGit3.iml
        src/

5. Ahora los cambios están sin trackear.Hacemos de nuevo el pull.

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (master)
$ git pull origin main
From https://github.com/brimacias/ejemploGit3
 * branch            main       -> FETCH_HEAD
Already up to date.

6. Ya está descargado lo que estaba en remoto (el README y el .gitignore de GitHub) en la rama main (rama por defecto en GitHub) a nuestra rama master local. Ahora commiteamos el proyecto local y lo subimos al repositorio.

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (master)
$ git add .
warning: in the working copy of 'src/Main.java', LF will be replaced by CRLF the next time Git touches it

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (master)
$ git commit -m "primer commit local"
[master bebf7d7] primer commit local
 6 files changed, 39 insertions(+)
 create mode 100644 .idea/.gitignore
 create mode 100644 .idea/misc.xml
 create mode 100644 .idea/modules.xml
 create mode 100644 .idea/vcs.xml
 create mode 100644 ejercicioGit3.iml
 create mode 100644 src/Main.java

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (master)
$ git log --oneline
bebf7d7 (HEAD -> master) primer commit local
bb912e3 (origin/main) Initial commit

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (master)
$ git push -u origin master
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 4 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (10/10), 1.49 KiB | 108.00 KiB/s, done.
Total 10 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'master' on GitHub by visiting:
remote:      https://github.com/brimacias/ejemploGit3/pull/new/master
remote:
To https://github.com/brimacias/ejemploGit3.git
 * [new branch]      master -> master
branch 'master' set up to track 'origin/master'.

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (master)
$ git log --oneline
bebf7d7 (HEAD -> master, origin/master) primer commit local
bb912e3 (origin/main) Initial commit

7. Se ha subido correctamente en la rama main:

![ejGit3_captura_3](https://user-images.githubusercontent.com/95747897/203100885-e0657f9a-4ea9-4730-a8d9-0ffb5865404a.png)

![ejGit3_captura_4](https://user-images.githubusercontent.com/95747897/203100673-1293ec5c-adc2-4625-959c-6165a5354683.png)

8. Cambios la rama por defecto de "main" a "master" y elinamos "main" (la eliminé después de acabar el resto de los pasos).

![ejGit3_captura_6](https://user-images.githubusercontent.com/95747897/203101108-0cac10df-8b53-4c5b-8f33-82cdaf5238c7.png)

9. Modificamos el proyecto local(se hacen añade un clase y se modifica Main):

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (master)
$ git commit -m"añadiendo código para probar las propiedades de Java"

10. Creamos otra rama para corregir un bug:

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (master)
$ git checkout -b fixBug1
Switched to a new branch 'fixBug1'

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (fixBug1)

11. Corregimos el problema, commiteamos la corrección en la rama y la pusheamos:

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (fixBug1)
$ git add .
warning: in the working copy of 'src/Main.java', LF will be replaced by CRLF the next time Git touches it

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (fixBug1)
$ git status
On branch fixBug1
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   src/Empleado.java
        modified:   src/Main.java


a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (fixBug1)
$ git commit -m"bug corregido y testeado"
[fixBug1 5925926] bug corregido y testeado
 2 files changed, 7 insertions(+), 4 deletions(-)

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (fixBug1)
$ git push -u origin fixBug1
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 4 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 502 bytes | 45.00 KiB/s, done.
Total 5 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), completed with 3 local objects.
remote:
remote: Create a pull request for 'fixBug1' on GitHub by visiting:
remote:      https://github.com/brimacias/ejemploGit3/pull/new/fixBug1
remote:
To https://github.com/brimacias/ejemploGit3.git
 * [new branch]      fixBug1 -> fixBug1
branch 'fixBug1' set up to track 'origin/fixBug1'.

12. Mergeamos a master la rama con el bug ya solucionado:

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (fixBug1)
$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.

a21brigittemmp@W10N-I9E25 MINGW64 /z/PDAW/Nuevo/Código/codigo_git/ejercicioGit3 (main)
$ git merge fixBug1
Updating bb912e3..5925926
Fast-forward
 .idea/.gitignore  |  4 ++++
 .idea/misc.xml    |  6 ++++++
 .idea/modules.xml |  8 ++++++++
 .idea/vcs.xml     |  7 +++++++
 ejercicioGit3.iml | 11 +++++++++++
 src/Empleado.java | 15 +++++++++++++++
 src/Main.java     | 12 ++++++++++++
 7 files changed, 63 insertions(+)
 create mode 100644 .idea/.gitignore
 create mode 100644 .idea/misc.xml
 create mode 100644 .idea/modules.xml
 create mode 100644 .idea/vcs.xml
 create mode 100644 ejercicioGit3.iml
 create mode 100644 src/Empleado.java
 create mode 100644 src/Main.java

13. Añado este README y la carpeta de imágenes.

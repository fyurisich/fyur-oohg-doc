## Procedimiento b�sico para construir una aplicaci�n:

1. Aseg�rese que el PATH del sistema incluye la carpeta C:\OOHG, en caso contrario deber� agregarla.
2. Abra una ventana de comandos y c�mbiese a la carpeta que contiene el c�digo fuente (archivos .prg).
3. Ejecute el siguiente comando:
   ```
   compile myApp
   ```
4. Para generar un archivo de preprocesador utilice:
   ```
   compile myApp /p
   ```
5. Si la aplicaci�n est� programada en modo consola utilice:
   ```
   compile myApp /c
   ```
6. Si desea a�adir el debugger de Harbour utilice:
   ```
   compile myApp /d
   ```

#### Notas:

* Si la aplicaci�n tiene m�s de un archivo fuente (ej.: myApp.prg y myFuncs.prg), para construirla con �xito necesitar� agregar al final de myApp.prg:
   ```
   #include "myFuncs.prg"
   ```
* Para incluir un archivo de recursos (.rc) deber� nombrarlo myApp.rc y colocarlo en la misma carpeta donde est� ubicado myApp.prg.
* Para utilizar un archivo de recursos adicionales deber� agregar al final de myApp.rc:
   ```
   #include "otro.rc"
   ```
* Por defecto, el proceso de construcci�n del ejecutable __incluye__ autom�ticamente el archivo de recursos de ooHG (archivo oohg.rc de la carpeta include).
* Este m�todo de construcci�n tambi�n funcionar� con la distribuciones basada en xHarbour y BCC.


## Procedimiento alternativo para quienes utilizan Harbour y MinGW:

1. En lugar de "compile" utilice "buildapp".

#### Notas:

* Para la construcci�n del ejecutable se utilizar� la utilidad HBMK2.EXE de Harbour.
* Aplican todas las notas del procedimiento b�sico.
* Con este procedimiento tambi�n se puede utilizar un archivo myApp.hbp conteniendo:
   ```
   #include "myApp.prg"
   #include "myFuncs.prg"
   ```


## Otro procedimiento alternativo para quienes utilizan Harbour y MinGW:

1. Aseg�rese que el PATH del sistema incluye C:\OOHG\HB30\BIN y C:\OOHG\HB30\COMP\MINGW\BIN para la distribuci�n basada en Harbour 3.0, o C:\OOHG\HB32\BIN y C:\OOHG\HB32\COMP\MINGW\BIN para la distribuci�n basada en Harbour 3.2.
2. Si la aplicaci�n trabaja en modo GUI o en modo mixto, copie el archivo BUILD_GUI.HBP en la carpeta donde est�n los archivos fuente (archivos .prg).
3. Abra una ventana DOS y cambie a la carpeta de la aplicaci�n.
4. Ejecute el siguiente comando:
   ```
   HBMK2 BUILD_GUI.HBP
   ```
5. Si la aplicaci�n trabaja en modo consola, copie el archivo BUILD_CON.HBP en la carpeta donde est�n los archivos fuente.
6. Abra una ventana DOS y cambie a la carpeta de la aplicaci�n.
7. Ejecute el siguiente comando:
   ```
   HBMK2 BUILD_CON.HBP
   ```

#### Notas:

* Se puede agregar un archivo de recursos (archivo .rc) en la secci�n '# Source' del archivo .HBP, si la aplicaci�n utiliza uno.
* Para utilizar archivos de recursos adicionales, agr�guelos al final del primer archivo de recursos utilizando #include "otro.rc".
* Por defecto, el proceso de construcci�n __no incluye__ autom�ticamente el archivo de recursos de OOHG.
* Si la aplicaci�n utiliza recursos de este archivo, debe agregarlo mediante alguno de los m�todos antes mencionados, especificando su nombre completo (C:\OOHG\RESOURCES\OOHG.RC).

# Autohotkey Scripts
My autohotkey scripts

<h1> Hotkey para cambiar de pantalla</h1>
<p>
Este script solo se ha probado con una pantalla secundaria a la derecha de la principal.
Los shortcuts son AltGr+1 para cambiar el puntero al centro de la primera pantalla y AltGr+2 para cambiar el puntero al centro de la segunda pantalla.
</p>

<h2> Paso #1, Instalar Autohotkey </h2>
<p>
Ir a https://www.autohotkey.com/ y descargar el instalador para su sistema operativo.
</p>

<h2> Paso #2, Crear el script </h2>
<p>
Hacer click derecho en el escritorio y crear un nuevo script de AutoHotkey. (New>AutoHotkey Script).
Debera abrirse una ventana de Notepad.
</P>

<p>En la nueva ventana escribir o pegar el siguente codigo:</p>

```
  #NoEnv  ; Recommended for performance and compatibility with future AutoHotkey releases.
  ; #Warn  ; Enable warnings to assist with detecting common errors.
  SendMode Input  ; Recommended for new scripts due to its superior speed and reliability.
  SetWorkingDir %A_ScriptDir%  ; Ensures a consistent starting directory.

  <^>!2::
  SysGet, Mon2, Monitor, 2
  Mon2CenterH := Round((Mon2Right-Mon2Left)/2+Mon2Left)
  Mon2CenterV := Round(Mon2Bottom/2)
  ;MsgBox, Left: %Mon2Left% -- Right: %Mon2Right% -- CenterH: %Mon2CenterH% -- CenterV: %Mon2CenterV% -- Bottom: %Mon2Bottom%.
  DllCall("SetCursorPos", "int", Mon2CenterH, "int", Mon2CenterV)
  return
  <^>!1::
  SysGet, Mon1, Monitor, 1
  Mon1CenterH := Round((Mon1Right-Mon1Left)/2+Mon1Left)
  Mon1CenterV := Round(Mon1Bottom/2)
  ;MsgBox, Left: %Mon1Left% -- Right: %Mon1Right% -- CenterH: %Mon1CenterH% -- CenterV: %Mon1CenterV% -- Bottom: %Mon1Bottom%.
  DllCall("SetCursorPos", "int", Mon1CenterH, "int", Mon1CenterV)
  return
```
<p> Es importante guardar el script con extension .ahk </p>

<h2> Paso #3: Correr el script </h2>
<p>Ahora que el script esta completo debería de poder correrse como cualquier otro programa. Un pequeño icono en la barra de tareas mostrara que el script está activo.</p>

## TOOLBOX   

<ins>**https://www.cleanpng.com**</ins>:  PNG images without backgrounds.   
<ins>**https://www.remove.bg**</ins>:  REMOVE BACKGROUND on image (png and jpeg).   
<ins>**https://www.adobe.com/express/feature/image/remove-background**</ins>:  ADOBE BACKGROUND REMOVER on image (png and jpeg).   
   
<ins>**https://github.com/danielgatis/rembgd**</ins>:  REMBG // BACKGROUND REMOVER en maquina local. Funciona también con carpetas.     
Instalar con ```pip install rembg[cli]``` y luego con el siguiente BACKGRONDRM.BAT (en Windows) se puede hacer "Drag and Drop":      
 ```
@REM 1
@echo off
setlocal
if "%~1"=="" (
  echo Drag an image file onto this batch file to process it.
  pause
  goto :EOF
)
set "input=%~1"
set "output=%~dp1%~n1_r.png"
rembg i "%input%" "%output%"
echo Processing complete: "%output%"
```


## VFX and CGI REOSURCES

### TEXTURES, MODELS and HDRI:   
<ins>**https://polyhaven.com/**</ins>: Texturas, modelos y HDRs gratis. De mucha calidad.   
<ins>**https://ambientcg.com/**</ins>: Materiales y texturas gratis. De mucha calidad.   
<ins>**https://www.openfootage.net/**</ins>: HDRi y footage. Hay bastante gratis (los de baja resolución)  

### FILM references:   

**https://beta.flim.ai** : Busqueda de referencias en peliculas    


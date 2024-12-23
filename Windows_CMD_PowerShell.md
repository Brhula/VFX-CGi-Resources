## Power SHell
### Rename multiple files in bulk

```powershell
ls | %{Rename-Item $_ -NewName ("NEW-FILE-NAME-{0}.EXTENSION" -f $nr++)}
```
### Random rename files in a folder

Navegar hasta el directorio en `PowerShell` y ejecutar el script:

```powershell
Get-ChildItem | ForEach-Object {
    $randomName = "name_"+[System.IO.Path]::GetRandomFileName()+$_.Extension
    Rename-Item $_.FullName $randomName
}
```
Le añadirá una "extension" random, aparte de la suya propia.

### KILL a process

```powershell
# con un ID conocido
Stop-Process -Id 41548
# con un nombre conocido
Stop-process -Name Chrome
```


## CMD
### Renombrar y trimar

https://www.windowscentral.com/how-rename-multiple-files-bulk-windows-10

"*" : representa un "wildcard" de cualquier cosa.   
"?" : representa un caracter del nombre original   


TRIMAR. Renombramos todo lo que hay la carpeta actual con los primeros 8 digitos (se preserva extensión)    
```CMD
ren *.* ????????.*
```

Renombramos todos los ficheros `jpg` preservando los 3 primeros caracteres e incorporamos `-raw` como parte del nombre. Si hay duplicados, no los procesa.   
```cmd
ren *.jpg ???-raw.*
```

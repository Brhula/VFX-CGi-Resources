## Power SHell
### Rename multiple files in bulk

```powershell
ls | %{Rename-Item $_ -NewName ("NEW-FILE-NAME-{0}.EXTENSION" -f $nr++)}
```


## CMD
### Renombrar y trimar

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

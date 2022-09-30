### FFMPEG codificador de linea de comando   
   
   
   

**Sintaxis basica:**   
   
```CMD
ffmpeg -i <infile> <outfile>
```   



**Codificar en mp4 a HD 1080 un fichero, con calidad:**   
```CMD
ffmpeg -i <infile> -preset slow -b:a 128k -codec:v libx264 -pix_fmt yuv420p -b:v 4500k -minrate 4500k -maxrate 9000k -bufsize 9000k -vf scale=-1:1080 <outfile>.mp4
```   

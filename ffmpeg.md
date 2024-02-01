### FFMPEG codificador de linea de comando   
   
[GUI tool to create complex FFmpeg filtergraphs](https://ffmpeg.guide/)   
   

**Sintaxis basica:**   
   
```CMD
ffmpeg -i <infile> <outfile>
```   

**Codificar para que Davinci Resolve lo importe sin problemas**   
Se utiliza un codec mp4de video antiguo. el parámetro `-q:v 3` intenta poner la calidad del video. en este caso, mas alto es menos calidad.   
```CMD
ffmpeg -i .\untitled.avi -q:v 3 -vcodec mpeg4 -acodec aac .\untitled.mp4
```   

**Codificar un mp4 con calidad**   
donde pone `-crf` se indica la calidad: 0 es "lossless", 51 lo comprime a saco. Poner 20 o 16 para alta calidad.   

```CMD
ffmpeg.exe -i "input file.mov" -c:v libx264 -crf 16 -c:a aac -strict -2 "output file.mp4"
```   

**Codificar en mp4 a HD 1080 un fichero, con calidad:**   
```CMD
ffmpeg -i <infile> -preset slow -b:a 128k -codec:v libx264 -pix_fmt yuv420p -b:v 4500k -minrate 4500k -maxrate 9000k -bufsize 9000k -vf scale=-1:1080 <outfile>.mp4
```   

**Recortar video del minuto 1 segundo 04, con duración de 11 segundos** 
```CMD
ffmpeg -ss 00:01:04.0 -i <infile> -c copy -t 00:00:11.0 <outfile>
```   

### Cortar video y audio SIN recodificar   
 
Use this to cut video from [start] for [duration]:

`ffmpeg -ss [start] -i in.mp4 -t [duration] -c copy out.mp4`

Use this to cut video from [start] to [end]:

`ffmpeg -ss [start] -i in.mp4 -to [end] -c copy -copyts out.mp4`

Here, the options mean the following:   
    `-ss` specifies the start time, e.g. `00:01:23.000` or `83` (in seconds)   
    `-t` specifies the duration of the clip (same format).   
    Instead of `-t`, you can also use `-to`, which specifies the end time (needs -copyts if `-ss` is before `-i`, for faster seeking). Note that if you've used `-ss`, you have to subtract this from the `-to` timestamp. For example, if you cut with `-ss 3 -i in.mp4 -to 5`, the output will be five seconds long.   
    `-c copy` copies the first video, audio, and subtitle bitstream from the input to the output file without re-encoding them. This won't harm the quality and make the command run within seconds.   

For more info, see https://trac.ffmpeg.org/wiki/Seeking

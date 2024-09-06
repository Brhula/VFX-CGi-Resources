## YT-DLP.exe (Youtube download)

Utilizar las intrucciones de "youtube-dl. tiene practicamente los mismos parqametros (es un fork) 

<ins>**https://github.com/yt-dlp/yt-dlp**</ins>: Sitio oficial.  

### Download mp4 BEST SETTINGS:   

Para hacer download de lo mejor posible en mp4 utilizar   
`yt-dlp.exe -f 'bestvideo[ext=mp4]+bestaudio[ext=m4a]/mp4' url`

Si queremos bajar el mejor mp4 pero con restricción de resolución (en este caso 1080):   
`yt-dlp.exe -f bestvideo[ext=mp4][height<=?1080]+bestaudio[ext=m4a]/best url`

### Download from available formats

Para saber que formatos hay disponibles utilizar el parámetro `-F` :
```
yt-dlp.exe -F 'http://www.youtube.com/watch?v=P9pzm5b6FFY' 
```  
Esto vomita un codigo como lo que sigue
```
[youtube] P9pzm5b6FFY: Downloading webpage
[youtube] P9pzm5b6FFY: Downloading android player API JSON
[info] Available formats for P9pzm5b6FFY:
ID  EXT   RESOLUTION FPS │  FILESIZE  TBR PROTO │ VCODEC       VBR ACODEC      ABR ASR MORE INFO
────────────────────────────────────────────────────────────────────────────────────────────────────────
sb2 mhtml 48x27          │                mhtml │ images                               storyboard
sb1 mhtml 80x45          │                mhtml │ images                               storyboard
sb0 mhtml 160x90         │                mhtml │ images                               storyboard
139 m4a   audio only     │   1.62MiB  48k https │ audio only       mp4a.40.5   48k 22k low, m4a_dash
249 webm  audio only     │   1.65MiB  49k https │ audio only       opus        49k 48k low, webm_dash
250 webm  audio only     │   2.24MiB  67k https │ audio only       opus        67k 48k low, webm_dash
140 m4a   audio only     │   4.29MiB 129k https │ audio only       mp4a.40.2  129k 44k medium, m4a_dash
251 webm  audio only     │   4.53MiB 136k https │ audio only       opus       136k 48k medium, webm_dash
17  3gp   176x144      7 │   2.23MiB  67k https │ mp4v.20.3    67k mp4a.40.2    0k 22k 144p
160 mp4   256x144     30 │   1.75MiB  52k https │ avc1.4d400c  52k video only          144p, mp4_dash
278 webm  256x144     30 │   1.93MiB  58k https │ vp9          58k video only          144p, webm_dash
133 mp4   426x240     30 │   3.80MiB 114k https │ avc1.4d4015 114k video only          240p, mp4_dash
242 webm  426x240     30 │   3.03MiB  91k https │ vp9          91k video only          240p, webm_dash
134 mp4   640x360     30 │   7.14MiB 215k https │ avc1.4d401e 215k video only          360p, mp4_dash
18  mp4   640x360     30 │  12.42MiB 375k https │ avc1.42001E 375k mp4a.40.2    0k 44k 360p
243 webm  640x360     30 │   5.23MiB 157k https │ vp9         157k video only          360p, webm_dash
135 mp4   854x480     30 │  12.48MiB 377k https │ avc1.4d401f 377k video only          480p, mp4_dash
244 webm  854x480     30 │   8.30MiB 250k https │ vp9         250k video only          480p, webm_dash
22  mp4   1280x720    30 │ ~30.40MiB 895k https │ avc1.64001F 895k mp4a.40.2    0k 44k 720p
136 mp4   1280x720    30 │  25.41MiB 767k https │ avc1.4d401f 767k video only          720p, mp4_dash
247 webm  1280x720    30 │  17.13MiB 517k https │ vp9         517k video only          720p, webm_dash
```

Y entonces podemos bajar lo que queramos con el parametro `-f` y el ID correspondiente .   
- Por ejemplo `yt-dlp.exe -f 22 http://www.youtube.com/watch?v=P9pzm5b6FFY`   

Si queremos mezclar audio y video (porque en YT estan separados) lo hacemos poniendo un `+` entre formatos. Necesitamos que `FFMPEG` este instalado o en el mismo directorio que `YT-DPL`. 
- Un ejemplo con lo de arriba seria `yt-dlp.exe -f 136+139 http://www.youtube.com/watch?v=P9pzm5b6FFY` que pillara el video 132 y lo mezclara con el audio 139 en un unico mp4.

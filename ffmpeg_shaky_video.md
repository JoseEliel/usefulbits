# This makes a new video that has a somewhat realistic camera shake.
```console
ffmpeg -i in.mp4 -vf "split[a][b];[b]scale=iw:ih[v];[a][v]overlay=x='if(lt(mod(t,1),1), random(1)*2\
+random(1)*(-2)+random(1)*(-3) + random(1)*2)':y='if(lt(mod(t,1),1), random(1)*2\
+random(1)*(-2)+random(1)*(-3) + random(1)*2)',rotate='if(lt(mod(t,1),1), (random(1)-0.5)*0.01)'" out.mp4
```

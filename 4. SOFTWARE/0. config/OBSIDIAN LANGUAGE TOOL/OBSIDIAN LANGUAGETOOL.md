Pull al contenedor de Language Tool en docker con 

```
docker pull erikvl87/languagetool
```

Instalar el plugin Language Tool Integration de Clemens-E, configurar la opcion Custom Server con http://localhost:8010. Desactivar el Speelling de Obsidian

Cada vez que se desee usar, correr el contenedor con

```
sudo docker run --rm -p 8010:8010 erikvl87/languagetool
```

---
### LECTURES
- https://hub.docker.com/r/erikvl87/languagetool/
- https://github.com/Clemens-E/obsidian-languagetool-plugin

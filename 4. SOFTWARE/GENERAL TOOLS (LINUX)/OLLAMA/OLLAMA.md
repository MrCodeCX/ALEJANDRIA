### INSTALLATION SCRIPT
Su script identifica la arquitectura y verifica si es am64 o arm64, limpia posibles versiones anteriores y verifica la existencia de unos comandos mínimos necesarios. Tras ello descarga y coloca sus binarios y librerías en /usr/local.

Luego configura el usuario ollama y el grupo ollama, y crea un servicio a iniciarse con dicho usuario y grupo, este servicio ejecuta el comando ollama serve, y es corrido por el daemon de systemd, se ubica en /etc/systemd/system/ollama.service. Se configura como default.target por lo que se inicia automáticamente

Finalmente verifica que tenga nvidia-smi y se finaliza.

### CONFIG ENVIRONMENT VARIABLES
Para configurar sus variables de entorno correr

```
sudo systemctl edit ollama.service
```

Añadir el encabezado Service, y asignar las variables de entorno

```
[Service]
Environment="VARIABLE=VALUE"
### Edits below this comment will be discarded
```

Recargar el demonio y reiniciar el servicio de ollama

```
systemctl daemon-reload
systemctl restart ollama
```

Para forzar el uso de CPU configurar la variable de entorno CUDA_VISIBLE_DEVICES=-1

---
### LECTURES
- https://github.com/ollama/ollama/blob/main/docs/faq.md

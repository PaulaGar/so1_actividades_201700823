# Servicio de Impresión de Saludo y Fecha

Este es un servicio systemd que ejecuta un script para imprimir un saludo y la fecha actual.

## Instalación

1. Crea y abre el archivo `hola.sh` en una ubicación de tu elección con el siguiente contenido:
    ```
    #!/bin/bash
    echo "Hola desde el servicio."
    echo "Fecha $(date +%d/%m/%Y)"
    ```

2. Crea y abre el archivo `hola.service` y agrega la siguiente informacion:
    ```
    [Unit]
    Description=Hola y Fecha

    [Service]
    Type=simple
    ExecStart=/usr/bin/bash /home/hola.sh

    [Install]
    WantedBy=multi-user.target
    ```
(En la ruta agregar la ruta donde se coloco el archivo .sh)  

3. Copia el archivo `hola.service` en el directorio `/etc/systemd/system/` usando `sudo cp hola-date.service /etc/systemd/system/`.

4. Ejecuta los siguientes comandos para habilitar y arrancar el servicio:

   ```bash
   sudo systemctl daemon-reload
   sudo systemctl enable print-date.service
   sudo systemctl start print-date.service
   ```

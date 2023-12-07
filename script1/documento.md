## Crea un script que añada un puerto de escucha en el fichero de configuración de Apache. El puerto se recibirá como parámetro en la llamada y se comprobará que no esté ya presente en el fichero de configuración

#!/bin/bash

# Verificar que se proporciona un puerto como argumento
if [ $# -eq 0 ]; then
    echo "Uso: $0 <puerto>"
    exit 1
fi

puerto=$1
archivo_configuracion="/etc/apache2/apache2.conf"  # Ajusta la ruta según la ubicación de tu archivo de configuración

# Verificar si el puerto ya está presente en el archivo de configuración
if grep -q "Listen $puerto" "$archivo_configuracion"; then
    echo "El puerto $puerto ya está presente en el archivo de configuración."
else
    # Añadir el puerto al archivo de configuración
    echo "Listen $puerto" | sudo tee -a "$archivo_configuracion" > /dev/null
    echo "Se ha añadido el puerto $puerto al archivo de configuración."
fi

# Reiniciar Apache para aplicar los cambios (puedes ajustar esto según tu sistema operativo)
sudo service apache2 restart  # Ajusta el comando según tu sistema operativo y método de gestión de servicios

exit 0

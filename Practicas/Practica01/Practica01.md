# Instalacion de Odoo

> [!NOTE]
> Las practicas se desarrollaran desde el [entorno web de Odoo](https://www.odoo.com/es_ES/web/login). La instalacion solo se utilizara en momentos muy puntuales.

- [Instalacion de Odoo](#instalacion-de-odoo)
  - [Instalacion en local - Ubuntu/Debian](#instalacion-en-local---ubuntudebian)
  - [Usando contenedores Docker](#usando-contenedores-docker)
  - [Instalacion en local - Windows](#instalacion-en-local---windows)

## Instalacion en local - Ubuntu/Debian

> [!CAUTION]
> Es importante seguir el orden de los pasos.

Instalamos las dependencias

```bash
sudo apt install postgresql -y
```

Añadimos el repositorio y la clave GPG de Odoo

```bash
wget -q -O - https://nightly.odoo.com/odoo.key | sudo gpg --dearmor -o /usr/share/keyrings/odoo-archive-keyring.gpg
echo 'deb [signed-by=/usr/share/keyrings/odoo-archive-keyring.gpg] https://nightly.odoo.com/17.0/nightly/deb/ ./' | sudo tee /etc/apt/sources.list.d/odoo.list
```

Instalamos Odoo

```bash
sudo apt-get update && sudo apt-get install odoo
```

Entra en el navegador

```bash
firefox localhost:8069
```

> [!WARNING]
> Guarda la contraseña maestra que te da el navegador.
> En caso de que no te la muestre o la hayas perdido, comenta la linea `admin_passwd =` con un `;` en el archivo `/etc/odoo/odoo.conf` y reinicia el servicio con `sudo systemctl restart odoo`.

## Usando contenedores Docker

> [!NOTE]
> Esta forma de instalacion es igual para todos los sistemas operativos.
> Ten en cuenta que es necesario tener instalado [Docker](https://github.com/Xabierland/AS/blob/main/Ejercicios/Tema3/Tema3.1/Ejercicio1.md).

Descargamos el docker-compose.yml

```bash
wget https://raw.githubusercontent.com/Xabierland/SGE/master/Practicas/Practica01/docker/docker-compose.yaml
```

Ejecutamos el contenedor

```bash
docker-compose up -d
```

Entra en el navegador

```bash
firefox localhost:8069
```

> [!WARNING]
> Guarda la contraseña maestra que te da el navegador.
> En caso de que no te la muestre o la hayas perdido, comenta la linea `admin_passwd =` con un `;` en el archivo `config/odoo.conf` y reinicia el servicio con `docker compose restart`.

## Instalacion en local - Windows

¿Que te has creido que iba a poner como instalarlo en Windows?

<img src="https://gist.githubusercontent.com/LoLei/7a90b6f4f6e4571dea4ae578dbe78b86/raw/e760dd809f213dcabff38c9d62989bab4825b07f/tux.png" alt="Viva GNU/Linux" width="32" height="38">
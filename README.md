# Mi configuración inicial de Ubuntu

Este documento lo estoy realizando, debido a que acabo de echar a perder mi Ubuntu 18.04.1 (que por cierto tenía unos días que lo estaba presumiendo por lo genial que había quedado, y que aún creo que puedo dejar como antes). Comenzaré desde el principio, osea desde una instalación de Ubuntu 16.04 LTS a la que posterioemente haré el upgrade a la versión 18.04 LTS.

- [Mi configuración inicial de Ubuntu](#mi-configuraci%C3%B3n-inicial-de-ubuntu)
  - [Lo primero apt-get](#lo-primero-apt-get)
  - [Instala VLC](#instala-vlc)
  - [Upgrade to version 18.04 LTS](#upgrade-to-version-1804-lts)
  - [Configura Git](#configura-git)
  - [Configurando VSCode](#configurando-vscode)

## Lo primero apt-get

Antes de iniciar a hacer cualquier cosa en Ubuntu, abre tu terminal y escribe los siguientes comandos:

```bash
sudo apt-get update
sudo apt-get upgrade
sudo apt update
sudo apt upgrade
```

## Instala VLC

```bash
sudo apt-get install vlc
```

## Upgrade to version 18.04 LTS

Siguiendo este [tutorial](https://linuxconfig.org/how-to-upgrade-to-ubuntu-18-04-lts-bionic-beaver), pude hacer el upgrade de manera sencilla con los siguientes comandos:

```bash
sudo apt update 
sudo apt upgrade
sudo apt dist-upgrade
sudo apt autoremove
```

Después de esto, teclea los siguientes comandos:

```bash
sudo apt install update-manager-core
sudo do-release-upgrade
# En caso que no se haya podido con el comando anterior, teclea el siguiente:
sudo do-release-upgrade -d
```

## Configura Git

Al querer usar el comando `git` en mi instalación me dió el error de que no conoce el comando, por lo tanto, tuve que hacer la instalación desde la terminal:

```bash
sudo apt install git

# Después de esto, ya puedes hacer las configuraciones globales iniciales
git config --global user.name "username" # De Github en mi caso
git config --global user.email "email@domain.com" # De Github en mi caso

# Para comprobar que todo quedó listo
git config --list
```

Ahora tenemos que ligar nuestra compu con Github (en mi caso), siguiendo lo siguiente:

```bash
ssh-keygen
# Tecleas enter hasta terminar
cat ~/.ssh/id_rsa.pub
# Seleccionas toda la cadena de caracteres que te muestre y la copias (`ctrl + shift + c` en la Terminal)
```

- Entra a tu cuenta de **Github**
- En tu avatar seleccionas *Settings*
- Una vez allí, seleccionas *SSH and GPG Keys*
- Ahora en *New SSH Key*
- En el primer `prompt` escribe el nombre que quieras para identificarla
- Por último pega la cadena de carateres que conseguiste con el comando `cat`, y listo!

## Configurando VSCode

Una de las primeras cosas que observé al instalar VSCOde y de las cuales estoy acostumbrado a hacer, es el duplicar líneas hacia arriba o hacia abajo con tan solo presionar `shift + alt + (up or down arrow)`. Bueno, al parecer tenemos que hacerlo manualmente, no te preocupes, es sencillo:

- File + Preferences + Keyboards Shortcuts
  - O con shrotcuts, presiona `ctrl + k y ctrl + s`
- Ahí buscas Copy line down y Copy line up y al darle doble click, puedes configurarlo a tu gusto (en mi caso `shift + alt + (up or down arrow)` funciona genial)
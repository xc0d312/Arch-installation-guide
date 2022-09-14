<h1 align="center">Guia de instalación de ArchLinux dualboot UEFI</h1>

###
<img href="https://github.com/xc0d312/xc0d312/blob/output/snake.svg" alt="Snake animation" />

###
<h6 align="center">Link de Descargar de ArchLinux https://archlinux.org/download/</h6>

###
<h6 align="center">Antes de haber iniciado ArchLinux debio haver creado previamente una partición donde instalará arch junto a windows 10. el espacio es relativo al que usted deseè darle a us arch.</h6>

###
<h6 align="center">despues de iniciar ArchLinux desde un live Usb nos mostrará una pantalla similar a esta.</h6>

###
<div align="center">
  <img height="100" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:36:20.png"  />
</div>
<h6 align="center">verificaremos el modo de arranque, si aparece algo parecido es porque estamos usando UEFI</h6>

###
<div align="center">
  <img height="100" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:52:28.png"  />
</div>

###
###
<h6 align="center">configuraremos el teclado a nuesto idioma nativo, de paso le daremos un tamaño ala tty para poder tener mejor manejo dentro de la terminal.</h6>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:38:01.png"  />
</div>

###
<h6 align="center">Luego de haber echo lo anterior comencemos por listar las particones de nuestro disco.</h6>

###
<div align="center">
  <img height="100" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:36:34.png"  />
</div>

###
<h6 align="center">Con la utilidad fdisk que viene por defecto con arch, crearemos nuestras particiones que tendra el sistema operativo</h6>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:38:59.png"  />
</div>

###
<h6 align="center">Luego de ejecutar lo anterior, presionaremos el parametro g, para crear una tabla de particiones gpt, que es la recomendada para UEFI </h6>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:39:54.png"  />
</div>

###
<h6 align="center">luego presionaremos el parametro n, para crear las particiones correspondientes, la primera sera la boot, pero ojo si queremos compartir el arranque de windows con linux podemos usar la de windows, siempre es una que pesa como 100M.  Si ustedes estan instalando en maquina virtual o nativo pero sin dualboot, tienen que crear la partición boot. la creación seria de la siguiente manera, le daran un espacio de 512M y especificaran el tipo de partición en este caso System Efi.</h6>

###
<div align="center">
  <img height="50" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-09-14_13:16:40.png"  />
</div>

###
<h6 align="center">Luego de haber creado la partición con el parametro t, especificarán el tipo de partición de la siguiente manera eligirán el tipo de partición</h6>

###
<div align="center">
  <img height="50" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-09-14_13:18:33.png"  />
</div>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-09-14_13:18:58.png"  />
</div>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-09-14_13:19:18.png"  />
</div>

###
<h6 align="center">Luego con el parametro p, imprimiremos las particones creadas</h6>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:43:01.png"  />
</div>

###
<h6 align="center">ahora crearemos la partición de intercambio, igual le daremos la mitad de espacio de nuestra ram, si la ram es de 8 le daremos 4G, yo en este caso le dí 1G, igual no es obligatorio crear la partición de intercambio. Luego igual que en la partición boot le cambie el tipo de partición con el parametro t, sino saben  cual es el numero para el tipo de partición, lo pueden ver con el parametro L.</h6>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:44:17.png"  />
</div>

###
<div align="center">
  <img height="50" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:46:43.png"  />
</div>

###
<h6 align="center">Luego de haber echo lo anterior con el parametro p listaremos las particiones creadas.</h6>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:46:04.png"  />
</div>

###
<h6 align="center">Luego igual crearemos la partición root donde instalara el sistema ArchLinux.Este caso luego de aver seleccionado el parametro n, dejaremos por defecto el primer sector y el ultimo sector para que ocupe todo lo que sobra del espacio del disco el tipo de partición sera file system con el Parametro t puede especificarle el tipo de partición seleccionnado el la particion y luego con el parametro L desplegar una lista del tipo de particiones y ver que numero corresponde para el tipo de partición que pretendemos crear. en este caso no crearemos la particion home aparte. Luego de crear la partición root selecionaremos el parametro w, para escribir todos los cambio echos en el disco, es importante verificar que todas las particones se han creado correctamente y que tienen el tipo de particiòn cada una.</h6>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:47:14.png"  />
</div>

###
<h6 align="center">Listaremos las particiones con el comando lsblk para confirmar que todo ha ido bien</h6>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:47:34.png"  />
</div>

###
<h6 align="center">Ahora formatiaremos todas las particiones, ojó si esta instalando en dualboot y quiere compartir el arranque de windows con arch, no debe formatiar la partición de arranque de windows, siempre es una que pesa como 100M, mucho cuidado  con eso. pero si estan en maquina virtual si tienen que formatearla como acontinuación.</h6>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:48:34.png"  />
</div>

###
<h6 align="center">Activaremos el area de intercambio.</h6>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:50:38.png"  />
</div>

###
<h6 align="center">Crearemos la carpeta boot en mnt y luego montaremos la partición boot, si lo que desea es compartir el arranque de windows pues montará la particion de arranque de windows en la carpeta mnt/boot la partición de arranque de windows es una que casi siempre pesa como 100M.</h6>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:50:07.png"  />
</div>

###
<h6 align="center">Luego montaremos la partición root en mnt/</h6>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:51:05.png"  />
</div>

###
<h6 align="center">ahora instalaremos el kernel de linux y otros paquetes bases </h6>

###
<div align="center">
  <img height="20" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_12:54:48.png"  />
</div>

###
<h6 align="center">Vamós a crear el archivos fstab, para la configuración de las particiones.</h6>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_13:02:05.png"  />
</div>

###
<h6 align="center">accederemos al sistema operativo</h6>

###
<h1 align="center"></h1>

###
<div align="center">
  <img height="50" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_13:03:00.png"  />
</div>

###
<h6 align="center">configuraremos la zona y otras configuraciones, buscaremos nuestra zona horaria y la descomentaremos quitandole el # y guardaremos cambios y generaremos el archivo</h6>

###
<div align="center">
  <img height="20" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_13:03:57.png"  />
</div>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_13:04:14.png"  />
</div>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_13:04:37.png"  />
</div>

###
<div align="center">
  <img height="50" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_13:04:56.png"  />
</div>

###
<h6 align="center">Seguiremos con las demas configuraciones del sistema</h6>

###
<div align="center">
  <img height="50" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_13:05:59.png"  />
</div>

###
<div align="center">
  <img height="100" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_13:07:38.png"  />
</div>

###
<div align="center">
  <img height="50" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_15:32:59.png"  />
</div>

###
<h6 align="center">instalaremos el bootctl en /boot</h6>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_15:33:41.png"  />
</div>

###
<h6 align="center">Abriremos con nano el archivo que estan en /boot/loader/loader.conf y le pondremos las siguientes configuraciones </h6>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_15:34:36.png"  />
</div>

###
<h6 align="center">Luego ejecutaremos el siguiente comando.</h6>

###
<div align="center">
  <img height="70" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_15:37:05.png"  />
</div>

###
<h6 align="center">abriremos el archivo que creamos en el comando anterior y le pondremos las siguientes configuraciones </h6>

###
<div align="center">
  <img height="70" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_15:57:31.png"  />
</div>

###
<h6 align="center">Luego de haber echo lo anterior ejecutaremos el siguiente comando y si todo ha salido bien senos mostrará algo parecido</h6>

###
<div align="center">
  <img height="200" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_15:57:48.png"  />
</div>

###
<h6 align="center">Instalaremos los siguientes paquetes, para las configuraciones de la red</h6>

###
<div align="center">
  <img height="100" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_15:58:19.png"  />
</div>

###
<h6 align="center">establecremos una contraseña para el usuario root</h6>

###
<div align="center">
  <img height="50" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_16:34:04.png"  />
</div>

###
<h6 align="left">sino queremos usar bootctl  como cargador de arranque, podemos instalar GNU grub, instalamos el programa con la siguiente instrucción. pacman -S grub efibootmg.despues de eso ejecutamos el siguiente comando grub-install --target=x86_64-efi  --efi-directory=/boot/EFI</h6>

###
<h6 align="center">Despues de haber echo eso, ejecutamos el comando exit, para salir de la instalación y desmontamos todas las particiones con el comando umount -R /mnt</h6>

###
<h6 align="center">Despues de hacer eso reiniciamos el equipo, despues de aver arrancado el equipo iniciamos los demonios Network.manager y wpa_supplicant para tener acceso a internet</h6>

###
<div align="center">
  <img height="80" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_16:46:34.png"  />
</div>

###
<h6 align="center">instalaremos xorg como servidror grafico para poder montar un entorno de escritorio en ArchLinux, luego instalaremos gnome como entorno de escriorio</h6>

###
<div align="center">
  <img height="80" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_16:47:55.png"  />
</div>

###
<div align="center">
  <img height="80" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_16:48:13.png"  />
</div>

###
<h6 align="center">Faltó configurar el archivo etc/hosts</h6>

###
<div align="center">
  <img height="80" src="https://github.com/xc0d312/Arch-installation-guide/blob/main/src/screensht_22-08-26_16:51:32.png"  />
</div>

###

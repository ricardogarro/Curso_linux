# Introducción práctica a Linux usando contenedores

## 1. Objetivo de la clase

- Comprender qué es Linux, sus componentes básicos y su filosofía.
- Aprender a usar un entorno Linux real sin necesidad de instalar máquinas virtuales.
- Practicar comandos fundamentales en un contenedor de Ubuntu.

---

## 2. Diferencia entre **Unix**, **Linux** y **GNU/Linux**

| Concepto  | Descripción |
|:----------|:------------|
| **Unix** | Es un sistema operativo multitarea y multiusuario desarrollado en los años 70 en los laboratorios Bell. Fue originalmente propietario y sentó las bases de muchos sistemas modernos. |
| **Linux** | Es el **kernel** (núcleo) de un sistema operativo, compatible con Unix, creado por **Linus Torvalds** en 1991. Es libre y de código abierto. |
| **GNU**   | Es un proyecto iniciado por **Richard Stallman** en 1983 para crear un sistema operativo completamente libre. Incluye utilidades como `bash`, `ls`, `cp`, `gcc`, etc. |
| **GNU/Linux** | La combinación práctica de GNU + Linux: el kernel Linux con las herramientas y utilidades del proyecto GNU. Es lo que hoy usamos como \"distribuciones\" como Ubuntu, Debian, Fedora, etc. |

✅ **Conclusión**: Técnicamente usamos sistemas **GNU/Linux**, aunque coloquialmente decimos \"Linux\". Además, tanto GNU/Linux como Linux fueron fuertemente inspirados en Unix.


---

## 3. ¿Qué es Linux?

- **Sistema operativo libre** basado en Unix.
- Utilizado en servidores, móviles, IoT, supercomputadoras y PC de escritorio.
- **Filosofía Unix**: programas pequeños que hacen una sola cosa bien y se combinan.
- **Todo es un archivo**: dispositivos, procesos, configuraciones.

---

## 4. Componentes principales de un sistema Linux

- **Kernel**: se comunica con el hardware.
- **Shell**: interfaz de línea de comandos (`bash`).
- **Sistema de archivos**: estructura jerárquica (`/`, `/home`, `/etc`, `/var`, etc).
- **Gestor de paquetes**: permite instalar y actualizar software (`apt`, `dnf`, `yum`, `pacman`).

---

## 5. ¿Qué es un contenedor de Ubuntu?

- Una forma **liviana** de correr un sistema operativo dentro de tu computadora.
- Comparado con una máquina virtual, **usa menos recursos**.
- Permite practicar Linux **sin instalar** Ubuntu real ni afectar tu sistema operativo.

---

## 6. Instalación del entorno Ubuntu usando Docker

### Pre-requisitos

- Tener instalado **Docker**:
  - En Windows/Mac: instalar **Docker Desktop**.
  - En Linux: instalar Docker Engine (`sudo apt install docker.io`).

---

### Comandos básicos

```bash
# 1. Descargar la imagen oficial de Ubuntu
docker pull ubuntu

# 2. Crear y entrar a un contenedor interactivo
docker run -it --name mi-ubuntu ubuntu bash
```

**Explicación**:
- `-it`: modo interactivo.
- `--name mi-ubuntu`: nombre del contenedor.
- `ubuntu`: imagen base.
- `bash`: acceso a la terminal bash.

---

### ¿Cómo salir del contenedor?

```bash
exit
```

O presionar `Ctrl+D`.

---

### ¿Cómo volver a entrar a un contenedor?

```bash
docker start -ai mi-ubuntu
```
**Explicación**:
- `-docker start`: Inicia un contenedor que ya existe pero está detenido.
- `-a (attach)`: Se conecta al output del contenedor (muestra lo que el contenedor imprime).
- `-i (interactive)`: Mantiene la entrada estándar (stdin) abierta para que puedas escribir dentro del contenedor.
- `mi-ubuntu`: nombre del contenedor.

---

### ¿Cómo borrar el contenedor?

```bash
docker rm mi-ubuntu
```

---

## 7. Primera práctica en Linux

Una vez dentro del contenedor `mi-ubuntu`, practicar:



```bash


# Ver el kernel
uname -a

# Actualizar el índice de paquetes
apt update

# Instalar paquetes simples 
apt install nano
apt install lsb-release

# Ver información del sistema
lsb_release -a

# Crear una carpeta y navegar
mkdir practica
cd practica

# Crear un archivo de texto
nano hola.txt
# (Escribir algo, guardar con Ctrl+O, salir con Ctrl+X)

# Listar archivos
ls -l

# Mostrar el contenido de un archivo
cat hola.txt

# Ver el usuario actual
whoami

apt install adduser
# Crear un nuevo usuario
adduser estudiante

# Cambiar a ese usuario
su estudiante

# Cambiar a ese usuario
exit

```
---

## 8. Mini-desafíos sugeridos

- Crear un archivo llamado `linux.txt` con una definición breve de Linux.
- Crear una carpeta `scripts` y dentro un pequeño script que imprima `Hola Mundo` usando bash.
- Instalar `htop` (`apt install htop`) y explorar los procesos del sistema.

---

## 9. Filosofía Unix (aplicada en Linux)

- **Haz una cosa y hazla bien**.
- **Conecta programas** mediante pipes (`|`).
- **Trata todo como archivo**.
- **Simplifica**: menos es más.

---

## 10. Comandos básicos de Linux

| Comando | Descripción |
|:--------|:------------|
| `ls` | Listar archivos y carpetas |
| `cd` | Cambiar directorio |
| `pwd` | Mostrar la ruta actual |
| `mkdir` | Crear una carpeta |
| `touch` | Crear un archivo vacío |
| `nano` | Editor de texto en terminal |
| `cat` | Mostrar contenido de un archivo |
| `cp` | Copiar archivos o carpetas |
| `mv` | Mover o renombrar archivos o carpetas |
| `rm` | Borrar archivos o carpetas |
| `sudo` | Ejecutar un comando como administrador |
| `apt update` | Actualizar el índice de paquetes |
| `apt install <paquete>` | Instalar un paquete nuevo |

---


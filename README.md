# 🥔 potato-wall (v0.0.1)

**potato-wall** es un firewall adaptativo para Linux, construido como una capa de automatización sobre `ufw` (Uncomplicated Firewall). Está diseñado para simplificar la gestión de reglas dinámicas y fortalecer la seguridad del sistema mediante un enfoque de infraestructura como código.

Parte del ecosistema de herramientas de **[potatoLabs.tech](https://potatolabs.tech)**.

---

## 🚀 Características Principales
* **Abstracción de Reglas:** Gestión simplificada de políticas de seguridad complejas sin interactuar directamente con la sintaxis cruda de iptables o nftables.
* **Soporte Nativo para Arch Linux:** Integración limpia con el gestor de paquetes `pacman` a través de su `PKGBUILD`.
* **Ligero y Eficiente:** Desarrollado en Shell para garantizar compatibilidad y un consumo mínimo de recursos.

## 📂 Arquitectura del Proyecto
* `potato-wall`: Script ejecutable y motor principal del firewall.
* `potato-wall.install`: Script de post-instalación para la configuración de hooks y permisos en el sistema.
* `PKGBUILD`: Receta de construcción para empaquetado en distribuciones basadas en Arch.
* `PBK`: Archivo base para configuración o gestión de llaves del entorno.

## 🛠️ Instalación

### Arch Linux / Derivados (Recomendado)
Puedes compilar e instalar el paquete localmente usando `makepkg`:

```bash
git clone [https://github.com/TU_USUARIO/potato-wall.git](https://github.com/TU_USUARIO/potato-wall.git)
cd potato-wall
makepkg -si
```

### Instalación Manual
Asegúrate de contar con `ufw` instalado y habilitado en el sistema antes de proceder:

```bash
chmod +x potato-wall
sudo ./potato-wall.install
```

## 📖 Menú de Ayuda (`--help`)
Puedes consultar las opciones disponibles directamente en la terminal ejecutando `potato-wall --help`:

```text
Uso: potato-wall [OPCIÓN] [ARGUMENTOS]

Opciones:
  --init        Inicializa el estado base del firewall y aplica políticas por defecto.
  --status      Muestra el estado actual de las reglas adaptativas y de ufw.
  --add [IP]    Agrega una IP a la lista blanca temporal/permanente.
  --block [IP]  Bloquea una IP de forma inmediata.
  --help        Muestra este menú de ayuda.
```
*(Nota: La versión 0.0.1 se encuentra en fase de desarrollo inicial. Los parámetros y comandos están sujetos a cambios).*

## ⚙️ Ejemplos de Uso

**Inicializar las políticas por defecto:**
```bash
sudo potato-wall --init
```

**Verificar el estado actual del firewall:**
```bash
sudo potato-wall --status
```

**Bloquear una IP sospechosa rápidamente:**
```bash
sudo potato-wall --block 192.168.1.100
```

## 🔒 Consideraciones de Seguridad
Este proyecto se desarrolla aplicando principios de seguridad proactiva. Se recomienda encarecidamente auditar las reglas generadas en `/etc/ufw/` en un entorno de pruebas (como tu homelab) antes de su despliegue en servidores de producción.

---
**Ingeniería y Desarrollo:** Jherom | 🇨🇷

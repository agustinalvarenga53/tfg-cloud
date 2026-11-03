# Gestoría Sur S.L.

## 1. Situación Inicial
Gestoría Sur S.L. es una empresa de vehículos y tráfico con unos 15 empleados y 200 clientes. Manejan datos sensibles como DNIs y permisos de circulación.
Actualmente sufren los siguientes problemas:
- Intercambio de archivos por correo y memorias USB.
- Sin copias de seguridad probadas ni externas.
- Red sin segmentar (todo mezclado, sin aislamiento).
- Servidores instalados a mano, sin monitorización ante caídas.

## 2. Requisitos de la Nueva Infraestructura
- **Almacenamiento en red:** Nube privada segura (Nextcloud) para erradicar los USBs.
- **Web corporativa:** Servidor web rápido (Nginx) para la página de la gestoría.
- **Automatización (IaC):** Infraestructura como código (Terraform, Ansible) para poder destruirla y reconstruirla idéntica sin fallos humanos.
- **Seguridad y Monitorización:** Segmentación de red, acceso por SSH y paneles de vigilancia en tiempo real.

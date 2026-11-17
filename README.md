# ☁️ Gestoría Sur S.L. - Infraestructura Cloud Segura y Automatizada

![Estado](https://img.shields.io/badge/Estado-En%20Desarrollo-blue)
![Stack](https://img.shields.io/badge/Stack-KVM%20%7C%20OpenTofu%20%7C%20Ansible%20%7C%20Docker-success)
![Coste](https://img.shields.io/badge/Presupuesto-0%20%E2%82%AC-red)

Proyecto Intermodular (TFG) para el ciclo de **Administración de Sistemas Informáticos en Red (ASIR)**. 
Diseño y despliegue de una arquitectura híbrida (Local-First + AWS) orientada a la seguridad, alta disponibilidad y coste cero para una pyme del sector administrativo.

## 🎯 El Problema (Situación Inicial)
Gestoría Sur S.L. es una empresa de vehículos y tráfico con 15 empleados y ~200 clientes. Manejan datos altamente sensibles (DNI, permisos de circulación), pero sufren de:
- Dispersión documental (memorias USB y correos).
- Ausencia de copias de seguridad estandarizadas y externas.
- Red plana sin segmentar y servidores levantados a mano (sin tolerancia a fallos ni monitorización).

## 💡 La Solución (Arquitectura)
Para erradicar estos problemas técnicos bajo una estricta limitación de hardware (16 GB RAM) y presupuesto (0,00 €), se implementa una solución basada en **Infraestructura como Código (IaC)**:

1. **Virtualización (KVM/libvirt):** Segmentación estricta en 3 máquinas virtuales (DMZ, Red Interna y Monitorización).
2. **Aprovisionamiento (OpenTofu & Ansible):** Creación y configuración desatendida del hardware virtual y sistema operativo.
3. **Servicios Core (Docker Compose):** 
   - **Nextcloud + MariaDB:** Centralización documental segura.
   - **WireGuard:** VPN de alto rendimiento para teletrabajo.
   - **Nginx Proxy:** Terminación TLS para cifrado en tránsito.
4. **Observabilidad Activa:** Stack Prometheus + Grafana con alertas automatizadas.
5. **Continuidad de Negocio (Disaster Recovery):** Backups automatizados y cifrados enviados a la capa gratuita de **AWS S3**.

## 📂 Estructura del Repositorio
- `.github/workflows/`: Pipelines de CI para validación de código estático (Linting).
- `docs/`: Documentación, esquemas Mermaid/Draw.io y requisitos.
- `infra/`: Código IaC separado por responsabilidades (`tofu/` para KVM y `ansible/` para configuración).
- `scripts/`: Automatizaciones en Python/Bash (Backups offsite y gestión de VPN).
- `servicios/`: Archivos de orquestación de contenedores (`docker-compose.yml`).

---
*Desarrollado por Agustín Alvarenga.*

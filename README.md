# Laboratorio de Ciberseguridad Aplicada

Proyecto educativo con cinco prácticas de protección de datos y manejo de estado usando Spring Boot. Los endpoints `/vuln` muestran fallas de seguridad de forma intencional; los endpoints `/safe` muestran una alternativa mitigada.

## Requisitos

- JDK 17 o superior
- Maven
- OpenSSL para generar las llaves de prueba

## Ejecutar

Genera dos llaves distintas de 256 bits y mantenlas solo en tu terminal. No las guardes en el repositorio:

```bash
export LAB_AES_KEY="$(openssl rand -hex 32)"
export LAB_JWT_KEY="$(openssl rand -hex 32)"
mvn spring-boot:run
```

En PowerShell:

```powershell
$env:LAB_AES_KEY = (openssl rand -hex 32)
$env:LAB_JWT_KEY = (openssl rand -hex 32)
mvn spring-boot:run
```

La aplicación queda disponible en `http://localhost:8080`. Las prácticas 1 a 3 no requieren estas llaves; las rutas protegidas de las prácticas 4 y 5 sí.

## Cuentas de demostración

- `ana@itson.mx` / `Ana-2026` — usuario
- `admin@itson.mx` / `Admin-2026` — administrador

Usa la aplicación solo en `localhost` con fines educativos. La práctica 5 conserva una clave débil de demostración en su ruta vulnerable para permitir reproducir la falla; no es una llave de producción.

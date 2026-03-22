# [Nombre de la Feature] - Casos de Uso

## Información General de la Feature

| Campo              | Descripción                                      |
|--------------------|--------------------------------------------------|
| Nombre             | [nombre-corto-kebab-case o camelCase]            |
| Nombre amigable    | [Nombre que se muestra al usuario / en el menú]  |
| Objetivo principal | [una frase clara de qué valor entrega al usuario]|
| Área / Dominio     | [ej: Onboarding / Monetización / Social / Editor] |
| Tipo               | [Funcionalidad principal / Mejora UX / Core / etc] |
| Prioridad / Épica  | [P0 / P1 / Épica XYZ / Roadmap Q3]               |
| Estado actual      | [En producción / En beta / En desarrollo / Idea] |

## Casos de Uso Principales

### 1. [Verbo en infinitivo + sustantivo clave]

**Usuario principal / Rol:**  
[Usuario nuevo / Usuario free / Creador de contenido / Admin / etc]

**¿Qué problema resuelve? / Valor entregado:**  
[2–4 líneas. Enfócate en el beneficio para el usuario o para el negocio]

**Flujo principal (happy path):**

1. El usuario [acción inicial]
2. El sistema muestra / pide [elemento]
3. El usuario selecciona / ingresa [dato]
4. Se ejecuta la feature → resultado visible: [qué ve o recibe]

**Escenarios alternativos importantes:**

- **Usuario ya hizo esto antes**  
  - Comportamiento: [redirige, muestra mensaje, salta paso, etc.]

- **Usuario viene desde X lugar** (deep link, notificación, etc.)  
  - Diferencia: ...

**Casos de error / Estados no felices manejados:**

- [Condición] → Mensaje / Acción / HTTP status
- Usuario sin permisos → "Actualiza a Premium para usar esta función"
- Límite alcanzado → "Has alcanzado el límite diario de 10 publicaciones"

**Reglas de negocio clave:**

- Solo usuarios con plan ≥ Pro
- Máximo 3 usos gratis por cuenta
- Expira después de 7 días de inactividad
- ...

**Ejemplos reales de uso en la vida diaria del producto:**

- Usuario nuevo que quiere probar la IA sin registrarse
- Creador que necesita exportar en 4K rápidamente

---

### 2. [Otro caso de uso importante]

(Repetir estructura)

## Casos de Uso Secundarios / Edge cases

- **Caso:** Recuperar sesión después de cerrar app  
  Prioridad: Media  
  Descripción: ...

- **Caso:** Cambio de idioma en medio del flujo  
  ...

## Dependencias y Conexiones con otras Features

| Feature relacionada     | Tipo de dependencia   | Detalle / Qué necesita                          |
|-------------------------|-----------------------|-------------------------------------------------|
| Autenticación           | Obligatoria           | userId + roles                                  |
| Planes y Suscripciones  | Condicional           | Verificar si tiene acceso a "Pro"               |
| Notificaciones          | Opcional              | Enviar push cuando se completa la acción        |
| Exportador de archivos  | Integración           | Llama al endpoint /export cuando termina        |

## Eventos que dispara / Escucha

- Dispara evento: `feature.nombre-completada` → payload { userId, duration, success }
- Escucha evento: `user.upgraded` → habilitar opciones premium
- Publica métrica: `feature_usage` con tags { plan: "free", country: "MX" }

## Métricas clave sugeridas

- Uso diario / semanal (por tipo de plan)
- Tasa de completitud (inicio → fin con éxito)
- Tasa de abandono en cada paso del flujo
- Latencia p95 del flujo principal
- Errores más frecuentes (por mensaje o código)

## Notas / Consideraciones / Deudas

- [Limitaciones actuales conocidas]
- [Mejoras planeadas: dark mode, accesibilidad, etc.]
- [Deuda técnica: refactor pendiente del hook useX]
- [Posible impacto en performance: carga de 3 MB extra]

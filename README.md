# FPS Demo 3D

Un prototipo de FPS en primera persona corriendo **100% en el navegador** con **Three.js**.
Sin instalación, sin motores externos: puro **JavaScript y WebGL**.

Inspirado en la jugabilidad frenética de **Call of Duty: Zombies**, el combate táctico de juegos web como **Krunker.io** y **Shell Shockers**, y la acción en primera persona de títulos indie de culto del género.

# 🎮 Controles

**Mover** → `W A S D`
**Apuntar** → Mouse
**Disparar** → Click izquierdo
**Recargar** → `R`
**Bullet Time** → `F`
**Cambiar arma** → Rueda del mouse / `1` `2`
**Recapturar mouse** → Click en el lienzo

# 🔫 Armas

## Pistola táctica

**Balas:** 25 / 25
**Modo:** Semi-automático
**Daño por bala:** 3 HP
**Tiempo de recarga:** ~1.8 seg

### Diseño

• Slide verde
• Frame blanco/crema
• Luz táctica
• Serraciones

## Rifle de asalto (HK416)

**Balas:** 30 / 30
**Modo:** Automático (mantén click)
**Daño por bala:** 2 HP
**Tiempo de recarga:** ~2.5 seg

### Accesorios

• Supressor FDE
• Mira holográfica + lupa
• Empuñadura frontal vertical
• Stock Magpul CTR
• Linterna táctica

# ⚡ Mecánicas

## Bullet Time

Presiona `F` para activar.

El tiempo se ralentiza a aproximadamente **28%** de la velocidad normal.
Consume una barra de energía que se recarga automáticamente al desactivarlo.

## Ragdoll al morir

Cuando un enemigo recibe daño letal:

• Sale volando en la dirección del disparo
• Física de gravedad y rotación
• Partículas de sangre en cada impacto

## Sistema de Oleadas (estilo CoD Zombies)

• Cada 8 bajas sube el wave
• Los enemigos de oleadas superiores tienen más HP
• Los enemigos de oleadas superiores se mueven más rápido
• Al morir un enemigo, reaparece uno nuevo tras ~1.8 segundos
• El objetivo es sobrevivir el mayor tiempo posible

## IA enemiga

Los enemigos:

• Persiguen al jugador
• Animan sus extremidades al caminar
• Disparan proyectiles cuando están a menos de 22 unidades de distancia

# 🛠 Stack técnico

**Motor 3D** → Three.js r128
**Renderizado** → WebGL (vía Three.js)
**Física ragdoll** → Manual (vectores + gravedad)
**Modelos** → Geometrías primitivas (BoxGeometry, CylinderGeometry)
**Iluminación** → AmbientLight + DirectionalLight + PointLights
**Niebla** → `THREE.Fog`
**Animación** → `requestAnimationFrame`

# 📂 Estructura del código

```text
fps_demo_3d
├── HTML/CSS
│   ├── Canvas
│   ├── HUD overlays
│   └── Pantalla de inicio
│
├── Configuración de escena
│   ├── Luces
│   ├── Suelo
│   ├── Techo
│   ├── Paredes
│   └── Obstáculos
│
├── Modelo de pistola
│   └── ~15 geometrías
│
├── Modelo de rifle
│   └── ~25 geometrías
│
├── Sistema de armas
│   ├── Array de armas
│   ├── Switch con scroll
│   └── Stats por arma
│
├── Sistema enemigo
│   ├── Spawn
│   ├── IA de persecución
│   ├── Animación
│   └── Ragdoll
│
├── Sistema de balas
│   └── Pool de proyectiles
│
├── Estado del jugador
│   ├── HP
│   ├── Munición
│   ├── Bullet time
│   ├── Recarga
│   └── Movimiento
│
└── Game loop
    └── requestAnimationFrame con delta time y bullet time
```

# 🎯 Inspiraciones

**Call of Duty: Zombies**
Sistema de oleadas y enemigos que escalan en dificultad

**Krunker.io**
FPS ligero corriendo en navegador

**Shell Shockers**
Combate rápido, controles simples y efectivos

**BrowserQuest**
Demostración de que juegos complejos caben en el navegador

**Juegos indie FPS de culto**
Bullet time, ragdoll exagerado y acción sin filtros

# ⚠️ Limitaciones actuales (y cómo resolverlas en UE5)

**Demo (navegador)** → **Producción (Unreal Engine 5)**

Geometrías primitivas → Modelos 3D reales (.fbx, .uasset)
Física ragdoll manual → Physics Asset + Chaos Physics
IA básica (perseguir + disparar) → Behavior Trees + EQS
Sin audio → FMOD / Wwise
Sin animaciones de personaje → Skeletal Mesh + Animation Blueprint
Sin sombras dinámicas complejas → Lumen + Ray Tracing

# 🚀 Próximas mejoras sugeridas

• Sonidos de disparo, recarga y pasos
• Más tipos de enemigos con comportamientos distintos
• Barra de HP visual con colores y efectos
• Granadas y habilidades especiales
• Mapa / minimapa
• Sistema de puntuación con puntuación más alta persistente
• Animación de cambio de arma
• Modo móvil con joystick táctil

# 👤 Créditos

Prototipo desarrollado por **LEGNA (@angelepsq)** con asistencia de inteligencia artificial para la generación de código, diseño de mecánicas y documentación.

El concepto, la dirección creativa, las decisiones de diseño y todas las iteraciones del proyecto fueron definidas por el desarrollador.

La IA actuó como herramienta de apoyo técnico a lo largo del proceso.

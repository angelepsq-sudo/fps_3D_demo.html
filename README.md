FPS Demo 3D
Un prototipo de FPS en primera persona corriendo 100% en el navegador con Three.js. Sin instalación, sin motores externos — puro JavaScript y WebGL.
Inspirado en la jugabilidad frenética de Call of Duty: Zombies, el combate táctico de juegos web como Krunker.io y Shell Shockers, y la acción en primera persona de títulos indie de culto del género.

Controles
AcciónTecla / InputMoverW A S DApuntarMouseDispararClick izquierdoRecargarRBullet TimeFCambiar armaRueda del mouse / 1 2Recapturar mouseClick en el canvas

Armas
Pistola táctica

Balas: 25 / 25
Modo: Semi-automático
Daño por bala: 3 HP
Tiempo de recarga: ~1.8 seg
Diseño: Slide verde, frame blanco/crema, luz táctica, serrations

Rifle de asalto (HK416)

Balas: 30 / 30
Modo: Automático (mantén click)
Daño por bala: 2 HP
Tiempo de recarga: ~2.5 seg
Accesorios: Supressor FDE, holographic sight + magnificador, grip frontal vertical, stock Magpul CTR, linterna táctica


Mecánicas
Bullet Time
Presiona F para activar. El tiempo se ralentiza a ~28% de la velocidad normal. Consume una barra de energía que se recarga automáticamente al desactivarlo.
Ragdoll al morir
Cuando un enemigo recibe daño letal, sale volando en la dirección del disparo con física de gravedad y rotación. Las partículas de sangre aparecen en cada impacto.
Sistema de Oleadas (estilo CoD Zombies)
Cada 8 kills sube el wave. Los enemigos de oleadas superiores tienen más HP y se mueven más rápido. Al morir un enemigo, reaparece uno nuevo tras ~1.8 segundos. El objetivo es sobrevivir el mayor tiempo posible.
IA enemiga
Los enemigos persiguen al jugador, animan sus extremidades al caminar y disparan proyectiles cuando están a menos de 22 unidades de distancia.

Stack técnico
ComponenteTecnologíaMotor 3DThree.js r128RenderizadoWebGL (vía Three.js)Física ragdollManual (vectors + gravedad)ModelosGeometrías primitivas (BoxGeometry, CylinderGeometry)IluminaciónAmbientLight + DirectionalLight + PointLightsNieblaTHREE.FogAnimaciónrequestAnimationFrame

Estructura del código
fps_demo_3d
├── HTML/CSS         → Canvas, HUD overlays, pantalla de inicio
├── Scene setup      → Luces, suelo, techo, paredes, obstáculos
├── Pistol model     → ~15 geometrías (slide, frame, grip, barrel, sights...)
├── Rifle model      → ~25 geometrías (receiver, handguard, suppressor, stock...)
├── Weapon system    → Array de armas, switch con scroll, stats por arma
├── Enemy system     → Spawn, IA de persecución, animación, ragdoll
├── Bullet system    → Pool de proyectiles para jugador y enemigos
├── Player state     → HP, ammo, bullet time, recarga, movimiento
└── Game loop        → requestAnimationFrame con delta time y bullet time

Inspiraciones
JuegoQué tomamosCall of Duty: ZombiesSistema de oleadas, enemigos que escalan en dificultadKrunker.ioFPS ligero corriendo en navegadorShell ShockersCombate rápido, controles simples y efectivosBrowserQuestDemostración de que juegos complejos caben en el browserJuegos indie FPS de cultoBullet time, ragdoll exagerado, acción sin filtros

Limitaciones actuales (y cómo resolverlas en UE5)
Demo (navegador)Producción (Unreal Engine 5)Geometrías primitivasModelos 3D reales (.fbx, .uasset)Física ragdoll manualPhysics Asset + Chaos PhysicsIA básica (perseguir + disparar)Behavior Trees + EQSSin audioFMOD / WwiseSin animaciones de personajeSkeletal Mesh + Animation BlueprintSin sombras dinámicas complejasLumen + Ray Tracing

Próximas mejoras sugeridas

Sonidos de disparo, recarga y pasos
Más tipos de enemigos con comportamientos distintos
Barra de HP visual con colores y efectos
Granadas y habilidades especiales
Mapa / minimap
Sistema de puntuación con highscore persistente
Animación de cambio de arma
Modo mobile con joystick táctil


Créditos
Prototipo desarrollado por LEGNA (@angelepsq) con asistencia de inteligencia artificial para la generación de código, diseño de mecánicas y documentación.
El concepto, dirección creativa, decisiones de diseño y todas las iteraciones del proyecto fueron definidas por el desarrollador. La IA actuó como herramienta de apoyo técnico a lo largo del proceso.

# 🚀 Nave — Proyecto de Aprendizaje en Godot 4

Un juego de naves espaciales tipo *Asteroids* desarrollado como proyecto de aprendizaje con **Godot 4** y **GDScript**. El objetivo es explorar los conceptos fundamentales del motor mientras se construye un juego funcional y divertido.

---

## 🎮 ¿De qué trata el juego?

Dos jugadores compiten en una pantalla compartida pilotando sus naves por el espacio. Deben esquivar y destruir asteroides disparando proyectiles, mientras el fondo estrellado se desplaza en paralaje.

### Controles

| Acción       | Jugador 1       | Jugador 2   |
|--------------|-----------------|-------------|
| Girar izq.   | ← Flecha        | A           |
| Girar der.   | → Flecha        | D           |
| Impulso      | ↑ Flecha        | W           |
| Disparar     | Enter           | Espacio     |

---

## 📚 Conceptos de Godot aprendidos

Este proyecto cubre los siguientes temas del motor:

### Nodos y escenas
- Composición de escenas reutilizables (`player.tscn`, `asteroide.tscn`, `bala.tscn`)
- Instanciación dinámica de escenas con `instantiate()` y `add_child()`
- Árbol de nodos y referencias con `@onready`

### GDScript
- Variables exportadas con `@export` para configurar desde el inspector
- `_ready()`, `_process()` y `_physics_process(delta)`
- Uso de `await` para temporizadores asincrónicos (`create_timer`)
- Grupos (`is_in_group`) para detectar tipos de objetos en colisiones

### Física y movimiento
- `CharacterBody2D` con `move_and_slide()`
- Movimiento inercial con damping (simulación de inercia en el espacio)
- Velocidad angular acumulada para rotación suave
- *Screen wrap-around*: la nave reaparece al cruzar los bordes de pantalla

### Colisiones
- `Area2D` para detección de impactos (balas y asteroides)
- Señales `_on_area_entered` y `_on_body_entered`
- Desactivación diferida de colisiones con `call_deferred`

### Efectos visuales y audio
- Partículas con `CPUParticles2D` para el propulsor y explosiones
- Fondo con efecto parallax usando `ParallaxBackground`
- Sonidos con `AudioStreamPlayer2D` (disparo, propulsor, explosión)
- Música de fondo en loop

### Multijugador local
- Sistema de prefijos de input (`p1_`, `p2_`) para manejar dos jugadores con el mismo script
- Textura de nave configurable por inspector para diferenciar jugadores

---

## 🗂️ Estructura del proyecto

```
├── assets/
│   ├── sounds/       # Efectos de sonido y música
│   └── sprites/      # Sprites de naves, asteroides y fondo
├── scenes/
│   ├── player.tscn       # Escena de la nave (reutilizable para P1 y P2)
│   ├── asteroide.tscn    # Escena del asteroide con vida y explosión
│   ├── bala.tscn         # Proyectil disparado por las naves
│   └── TestSceneP2.tscn  # Escena principal con dos jugadores
└── scripts/
    ├── player.gd              # Movimiento, disparo y wrap-around
    ├── asteroide.gd           # Vida, daño y destrucción del asteroide
    ├── bullet.gd              # Movimiento y detección de impacto de la bala
    ├── explosion.gd           # Instanciación de efecto de explosión
    └── parallax_background.gd # Desplazamiento del fondo en parallax
```

---

## 🛠️ Requisitos

- [Godot 4.x](https://godotengine.org/download) (probado con 4.6)

---

## ▶️ Cómo ejecutar

1. Clona el repositorio:
   ```bash
   git clone <url-del-repo>
   ```
2. Abre Godot 4 e importa la carpeta del proyecto.
3. Presiona **F5** o el botón ▶ para ejecutar.

---

## 🧠 Próximas ideas

- [ ] Sistema de puntuación
- [ ] Asteroides que se dividen al recibir daño
- [ ] Vidas y pantalla de game over
- [ ] Asteroides con movimiento aleatorio
- [ ] Efectos de cámara (shake al explotar)

---

## 📄 Créditos

- Música: *Observing The Star* (ObservingTheStar.ogg)
- Sonido de explosión: *Nenad Simic — Muffled Distant Explosion*
- Motor: [Godot Engine](https://godotengine.org) — MIT License

# Recorrido de bienvenida UNSM con realidad aumentada

## 1. La idea en una frase
Un **folleto de bienvenida** con el mapa de la Ciudad Universitaria. El ingresante lo escanea con su celular y **los edificios salen en 3D sobre el mapa**. Al tocar un edificio o un pin, ve qué facultad o servicio es, y puede seguir un **recorrido guiado** paso a paso.

## 2. ¿Qué problema resuelve?
Los ingresantes no conocen el campus: no saben dónde está su facultad, el comedor, el centro médico o por qué puerta entrar. Un mapa en papel es difícil de entender. En 3D se entiende al toque, y funciona **sin instalar ninguna app**.

## 3. ¿Qué se muestra?
- Los 9 bloques de facultades (A a I) en 3D, con su forma real según el croquis oficial.
- Edificios estilo maqueta (paredes claras y techos de teja), árboles, piscina con agua, el monumento y la portada de la Puerta 1, inspirados en la maqueta física y la vista satelital del campus.
- Pines de servicios: Comedor, Cafetín 1, Cafetería saludable, Piscina, Campo deportivo, Losas deportivas, Centro Médico, Auditorio de Videoconferencias, Monumento Carlos Vidaurre, Puerta 1 y Puerta 2.
- Una ficha con información al tocar cada lugar.
- Un **recorrido guiado** de 20 pasos, desde la Puerta 1 hasta la Puerta 2.
- Un botón **❄️ Congelar** para tocar todo tranquilo sin mover el celular.

## 4. Herramientas (todas gratuitas, en lugar de Adobe Aero, que fue descontinuado)
| Para qué | Herramienta |
|---|---|
| Reconocer el folleto con la cámara | MindAR (código abierto) |
| Maqueta 3D, pines y animaciones | A-Frame (basado en Three.js) |
| Publicar la página con HTTPS | GitHub Pages |
| Abrir la página | Link o código QR |

## 5. ¿Cómo funciona por dentro?
1. El folleto se convierte en una "huella" (`targets.mind`) con miles de puntos de referencia.
2. Al apuntar la cámara, MindAR busca esos puntos en el video y calcula dónde está el folleto y cómo está inclinado.
3. A-Frame dibuja la maqueta 3D encima, usando el folleto como piso.
4. Un estabilizador evita que la maqueta tiemble, y se corrigió el ángulo de cámara de MindAR (de 45° a 65°) para que coincida con la cámara real del celular.

## 6. Datos utilizados (reales)
- Ubicación de bloques, servicios y puertas: **croquis oficial de la Ciudad Universitaria UNSM**.
- Estilo de los edificios y lugares extra (monumento, cafetines): maqueta física del campus y vista satelital (usadas solo como referencia; el mapa es un dibujo propio).
- Facultades y escuelas: información pública de la UNSM.
- Los horarios se pueden agregar en `index.html` (sección DATOS, campo `horario`).

## 7. Cómo publicarlo
1. Crear un repositorio público en GitHub (por ejemplo `recorrido-unsm`).
2. Subir los archivos: `index.html`, `targets.mind`, `mindar-image-aframe.prod.js`, `escudo.png`.
3. Settings → Pages → rama `main`, carpeta `/ (root)` → Save.
4. Abrir `https://TU-USUARIO.github.io/recorrido-unsm/` en Chrome (Android) o Safari (iPhone).

## 8. Consejos para la demo
- Imprime `folleto-bienvenida-A4.pdf` en papel mate (que no brille).
- Pon el folleto sobre la mesa y sostén el celular **en horizontal** para que entre todo el mapa.
- Muévete despacio. Para mostrar las fichas, toca **❄️ Congelar** y luego toca los edificios.
- Usa **🧭 Recorrido** para mostrar el paso a paso.

## 9. Guion corto para exponer (2 minutos)
1. "Cuando ingresamos a la UNSM no sabíamos dónde quedaba nada."
2. "Hicimos un folleto de bienvenida con realidad aumentada, que funciona desde el navegador, sin instalar apps."
3. *(Escanear)* "Al apuntar con el celular, los edificios salen en 3D sobre el mapa."
4. *(Tocar un bloque)* "Si toco un edificio, veo qué facultad es y qué escuelas tiene."
5. *(Recorrido)* "Y con el recorrido guiado, el ingresante conoce el campus paso a paso."
6. "Usamos herramientas gratuitas: MindAR y A-Frame, como alternativa a Adobe Aero, que fue descontinuado."

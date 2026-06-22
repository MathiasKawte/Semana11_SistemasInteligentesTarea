Laboratorio: Minimax y Poda Alfa-Beta
Descripción
Este proyecto implementa los algoritmos Minimax y Poda Alfa-Beta para la toma de decisiones en juegos adversariales. Se realizó una comparación entre ambos algoritmos para analizar su funcionamiento y eficiencia en la exploración de árboles de búsqueda.

Objetivo
Implementar los algoritmos Minimax y Poda Alfa-Beta en Python, comparar sus resultados y analizar cómo la poda reduce la cantidad de nodos evaluados sin afectar la decisión final.

Instalación
Clonar el repositorio.
Crear un entorno virtual:
python -m venv .venv
Activar el entorno virtual:
.venv\Scripts\Activate.ps1
Instalar dependencias:
pip install -r requirements.txt
Ejecución
python -m src.main
Pruebas
Ejecutar las pruebas unitarias:

pytest
Ejecutar las pruebas con cobertura:

pytest --cov=src --cov-report=term-missing --cov-report=xml
Resultados obtenidos
Sample Tree
Valor Minimax: 3
Valor Alpha-Beta: 3
Medium Tree
Valor Minimax: 7
Valor Alpha-Beta: 7
Ordered Tree
Valor Minimax: 8
Valor Alpha-Beta: 8
Se comprobó que ambos algoritmos producen la misma decisión final, pero Alfa-Beta evalúa menos nodos gracias a la poda de ramas innecesarias.

Preguntas de análisis
1. ¿Por qué Alfa-Beta obtiene el mismo resultado que Minimax si no evalúa todo el árbol?
Porque Alfa-Beta elimina únicamente las ramas que no pueden influir en la decisión final. De esta manera conserva el mismo resultado que Minimax, pero realizando menos evaluaciones.

2. ¿Qué representa alpha dentro del algoritmo?
Alpha representa el mejor valor encontrado hasta el momento para el jugador MAX. Sirve como límite inferior durante la búsqueda.

3. ¿Qué representa beta dentro del algoritmo?
Beta representa el mejor valor encontrado hasta el momento para el jugador MIN. Funciona como límite superior durante la exploración del árbol.

4. ¿En qué casos la Poda Alfa-Beta ahorra más trabajo?
La poda es más eficiente cuando los mejores movimientos se exploran primero, ya que permite descartar más ramas que no afectarán la decisión final.

5. ¿Por qué el orden de exploración afecta el rendimiento?
Porque un buen orden permite encontrar rápidamente valores límite para alpha y beta, aumentando la cantidad de ramas que pueden ser podadas.

6. ¿Qué pasaría si el rival no juega de manera racional?
Minimax asume que ambos jugadores toman siempre la mejor decisión posible. Si el rival juega de manera irracional, el resultado obtenido podría no reflejar el comportamiento real del juego.

7. ¿Cómo se relaciona este algoritmo con motores de ajedrez?
Los motores de ajedrez utilizan variantes de Minimax y Poda Alfa-Beta para evaluar millones de posiciones y seleccionar los movimientos más favorables.

8. ¿Qué limitaciones tiene este enfoque frente a redes neuronales o aprendizaje por refuerzo?
Minimax requiere conocer todas las reglas y explorar árboles de búsqueda. En cambio, las redes neuronales y el aprendizaje por refuerzo pueden aprender estrategias a partir de datos y experiencia, adaptándose mejor a problemas complejos.

Conclusiones
Se implementaron correctamente los algoritmos Minimax y Poda Alfa-Beta. Los resultados demostraron que ambos producen la misma decisión final, mientras que Alfa-Beta mejora la eficiencia al reducir la cantidad de nodos explorados. Esto permite realizar búsquedas más rápidas en problemas de toma de decisiones y juegos adversariales.
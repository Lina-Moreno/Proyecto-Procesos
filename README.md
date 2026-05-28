# Proyecto de Rachas de Éxitos

Este proyecto contiene un notebook que analiza un modelo de rachas de éxitos usando cadenas de Markov.

## Descripción

El proyecto simula una serie de ensayos de Bernoulli con probabilidad de éxito `p` y probabilidad de fracaso `q = 1 - p`.
Cada estado representa la longitud actual de una racha de éxitos consecutivos.
A partir de ese modelo se construyen matrices de transición, se simulan trayectorias y se calculan propiedades importantes de la cadena de Markov.

## Objetivos del proyecto

- Construir y mostrar la matriz de transición original.
- Construir la matriz modificada con un estado absorbente.
- Simular la evolución de las rachas paso a paso.
- Analizar clases de comunicación, estados transitorios y recurrentes.
- Calcular periodos de los estados.
- Evaluar probabilidades de transición en varios pasos.
- Comparar la simulación con tiempos medios teóricos de recurrencia y absorción.

## Contenido del notebook

El notebook `Proyecto.ipynb` incluye las siguientes secciones:

1. **Introducción al modelo**
   - Define la sucesión de ensayos de Bernoulli y el espacio de estados `S = {0, 1, 2, ...}`.
   - Explica las probabilidades de transición del modelo.

2. **Matrices de transición**
   - Construye la matriz de transición original para el modelo infinito.
   - Construye la versión absorbente donde el estado `N` es fijo.
   - Imprime ambas matrices para comparar su estructura.

3. **Simulación**
   - Implementa una simulación interactiva con `tkinter` y `matplotlib`.
   - Permite ejecutar el modelo en modo `Infinito` o `Absorbente`.
   - Dibuja la evolución de la longitud de la racha en una gráfica.

4. **Simulación rápida absorbente**
   - Añade una alternativa sin interfaz gráfica para obtener resultados rápidos.
   - Registra la secuencia de símbolos `p` y `q` y la trayectoria de la racha.

5. **Clases de comunicación**
   - Analiza qué estados se comunican entre sí.
   - Determina si la cadena es irreducible o si existe una clase absorbente.

6. **Clasificación de estados**
   - Clasifica los estados como transitorios o recurrentes positivos.
   - Muestra qué estados permanecen y cuáles se abandonan.

7. **Periodos de los estados**
   - Calcula el periodo de cada estado usando posibles ciclos de retorno.
   - Identifica si cada estado es aperiódico o periódico.

8. **Cálculos de Markov**
   - Construye el vector de distribución inicial `π(0)`.
   - Calcula `P^n` en varios pasos y muestra probabilidades de transición.
   - Imprime probabilidades de recurrencia sobre la diagonal.

9. **Tiempos medios y análisis**
   - Obtiene la distribución estacionaria para el caso infinito.
   - Calcula tiempos medios de transición entre estados.
   - Genera una simulación larga y compara resultados empíricos con la teoría.

10. **Cálculos de absorción**
    - Construye la matriz `Q` de estados transitorios.
    - Calcula la matriz fundamental `(I - Q)^{-1}`.
    - Obtiene tiempos medios de absorción y su varianza.
    - Dibuja la trayectoria en el caso absorbente y muestra la cota de dispersión.

## Dependencias principales

Para ejecutar el notebook, este proyecto usa principalmente:

- Python 3
- `numpy`
- `matplotlib`
- `tkinter` (parte de la librería estándar de Python)

El archivo `requirements.txt` contiene dependencias del entorno, entre ellas:

- `asttokens==3.0.1`
- `colorama==0.4.6`
- `comm==0.2.3`
- `contourpy==1.3.3`
- `cycler==0.12.1`
- `debugpy==1.8.20`

## Instalación

1. Crear y activar un entorno virtual:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

2. Instalar las dependencias necesarias:

```powershell
pip install numpy matplotlib
```

3. Si deseas instalar las dependencias listadas en `requirements.txt`:

pip install -r requirements.txt

## Uso

1. Abrir `Proyecto.ipynb` en Jupyter Notebook o JupyterLab.
2. Ejecutar las celdas en orden.
3. En la sección de simulación, usa el botón `Iniciar` para comenzar y `Parar` para detener.
4. Cambia el modo entre `Infinito` y `Absorbente` para ver cómo cambia el comportamiento.

## Qué observar

- El primer bloque compara la matriz original con la matriz absorbente.
- En `Infinito`, la cadena puede volver a bajar después de alcanzar el estado máximo.
- En `Absorbente`, el estado `N` es terminal y la cadena se detiene ahí.
- Las tablas de `P^n` muestran cómo cambian las probabilidades con el tiempo.
- La comparación entre resultados simulados y valores teóricos muestra la consistencia del modelo.

## Estructura del repositorio

- `Proyecto.ipynb`: notebook con todo el análisis y las simulaciones.
- `requirements.txt`: lista de dependencias del entorno.

## Comentarios finales

Este proyecto está diseñado para estudiar un modelo clásico de rachas de éxitos usando herramientas de cadenas de Markov, simulación numérica y análisis de propiedades de estados. El notebook permite tanto la ejecución interactiva como el cálculo teórico de las cantidades más relevantes.
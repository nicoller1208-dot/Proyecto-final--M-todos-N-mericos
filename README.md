# Simulación Numérica de la Ecuación de Schrödinger en 2D y 3D mediante FEM y Crank–Nicolson

Repositorio correspondiente al proyecto final del curso de Métodos Numéricos de la Universidad EAFIT. El proyecto consiste en el desarrollo de un solucionador numérico para la ecuación de Schrödinger dependiente del tiempo utilizando el Método de Elementos Finitos (FEM) y el esquema temporal implícito de Crank–Nicolson en dominios bidimensionales y tridimensionales.

El trabajo combina conceptos de mecánica cuántica computacional, análisis numérico, álgebra lineal dispersa y simulación científica, integrando tanto el desarrollo matemático como la implementación computacional completa en Python.

---

# Descripción General

La ecuación de Schrödinger dependiente del tiempo constituye una de las formulaciones fundamentales de la mecánica cuántica, ya que describe la evolución temporal de sistemas microscópicos mediante funciones de onda complejas. Aunque algunos sistemas ideales poseen soluciones analíticas conocidas, la mayoría de problemas físicos reales requieren métodos numéricos debido a la complejidad geométrica, las condiciones de frontera y la presencia de potenciales espaciales variables.

En este proyecto se desarrolló una implementación completa basada en el Método de Elementos Finitos para resolver numéricamente la ecuación:

iℏ ∂ψ/∂t = -(ℏ² / 2m) ∇²ψ + Vψ

La discretización espacial fue realizada mediante:

- elementos cuadriláteros bilineales Q4 en 2D
- elementos hexaédricos H8 en 3D

Por otra parte, la integración temporal se implementó utilizando el esquema implícito de Crank–Nicolson:

(iℏ/Δt M + H/2) ψⁿ⁺¹ = (iℏ/Δt M - H/2) ψⁿ

donde:

- M representa la matriz de masa
- H corresponde al Hamiltoniano discretizado
- ψ describe el estado cuántico del sistema

La formulación implementada permite estudiar fenómenos asociados a propagación, confinamiento y dispersión de paquetes de onda bajo diferentes configuraciones de potencial.

---

# Objetivos del Proyecto

El propósito principal del proyecto fue desarrollar un solucionador numérico robusto y físicamente consistente para la ecuación de Schrödinger dependiente del tiempo. A partir de esto, se buscó analizar propiedades fundamentales de estabilidad numérica, conservación de probabilidad y convergencia espacial.

Adicionalmente, el proyecto permitió explorar la relación entre formulaciones numéricas utilizadas en ecuaciones de difusión y aquellas aplicadas en mecánica cuántica, particularmente mediante esquemas implícitos y operadores diferenciales discretizados.

---

# Características Principales

El proyecto incluye simulaciones completas tanto en dos como en tres dimensiones, implementadas desde cero en Python utilizando estructuras matriciales dispersas optimizadas.

Entre las principales capacidades del simulador se encuentran:

- ensamblaje FEM utilizando matrices sparse en formatos LIL, DOK y CSR
- integración temporal mediante Crank–Nicolson
- aplicación de condiciones de frontera tipo Dirichlet
- simulación de paquetes gaussianos
- análisis de estabilidad energética
- conservación de norma cuántica
- visualización dinámica de densidad de probabilidad
- análisis de convergencia espacial
- interfaces gráficas interactivas desarrolladas con Tkinter

El código permite trabajar con diferentes potenciales físicos, incluyendo sistemas libres, osciladores armónicos, barreras de potencial, doble pozo, potenciales coulombianos regularizados y cajas cuánticas tridimensionales.

---

# Implementación Computacional

La implementación fue desarrollada completamente en Python utilizando bibliotecas de computación científica ampliamente utilizadas dentro de simulación numérica.

Las principales herramientas utilizadas fueron:

- NumPy para operaciones matriciales y manejo de arreglos
- SciPy para matrices dispersas y solución de sistemas lineales
- Matplotlib para visualización y animaciones
- Tkinter para interfaces gráficas interactivas

Durante el ensamblaje FEM se emplearon formatos dispersos LIL y DOK debido a su eficiencia para inserción incremental de coeficientes. Posteriormente, las matrices fueron convertidas a formato CSR con el fin de optimizar la resolución de sistemas lineales asociados al esquema temporal.

La formulación bidimensional trabaja sobre dominios rectangulares uniformes, mientras que la extensión tridimensional introduce elementos hexaédricos H8 y visualización mediante cortes ortogonales del volumen espacial.

---

# Simulación Bidimensional

El archivo `metodos_proyecto_2d.py` contiene la implementación completa del solucionador bidimensional.

Dentro de esta simulación se desarrollaron funcionalidades para:

- generación de malla uniforme
- ensamblaje de matrices de masa y rigidez
- construcción del Hamiltoniano
- integración temporal
- cálculo de observables físicos
- animación temporal de la densidad de probabilidad

El simulador permite estudiar la evolución temporal de paquetes gaussianos bajo diferentes configuraciones de potencial, mostrando comportamientos físicamente consistentes como dispersión libre y confinamiento armónico.

La conservación de probabilidad se evaluó mediante la norma FEM:

||ψ||² = ψ†Mψ

mientras que la energía esperada fue calculada utilizando:

⟨H⟩ = (ψ†Hψ) / (ψ†Mψ)

Los resultados mostraron estabilidad temporal y ausencia de crecimiento artificial de energía durante las simulaciones.

---

# Simulación Tridimensional

El archivo `metodos_proyecto_3d.py` extiende el modelo hacia tres dimensiones utilizando elementos hexaédricos lineales H8.

La implementación tridimensional representa un aumento considerable en complejidad computacional debido al crecimiento del número de grados de libertad y del costo asociado al ensamblaje y resolución del sistema lineal.

Para facilitar el análisis visual, la densidad de probabilidad tridimensional se representa mediante cortes planos ortogonales en los planos XY, XZ y YZ. Esta estrategia permite observar estructuras internas del sistema y analizar estados confinados dentro de cajas cuánticas y potenciales armónicos tridimensionales.

Los resultados obtenidos mostraron:

- expansión isotrópica en simulaciones libres
- confinamiento espacial bajo potencial armónico
- conservación de probabilidad en 3D
- estabilidad energética del esquema implementado

---

# Resultados y Análisis

Las simulaciones realizadas reprodujeron correctamente comportamientos esperados dentro de mecánica cuántica computacional.

Para partículas libres se observó dispersión progresiva del paquete gaussiano, mientras que los potenciales armónicos produjeron confinamiento espacial alrededor de regiones de mínimo potencial.

Asimismo, el refinamiento progresivo de malla mostró convergencia espacial consistente, evidenciando estabilidad y coherencia matemática de la formulación FEM implementada.

La conservación aproximada de la norma cuántica durante toda la simulación constituye una validación importante del esquema de integración temporal utilizado.

---

# Estructura del Repositorio

```text
Proyecto-final--M-todos-N-mericos/
│
├── metodos_proyecto_2d.py
├── metodos_proyecto_3d.py
├── Informe_final.pdf
├── MN - Proyecto carrusel.mp4
├── MN -Reel.mp4
├──Proyecto carrusel - link
├── README.md

```

El repositorio incluye las diferentes entregas desarrolladas durante el proyecto, así como material visual complementario, implementaciones computacionales y el informe final completo.

---

# Ejecución

## Instalación de dependencias

Antes de ejecutar los simuladores es necesario instalar las bibliotecas utilizadas:

```bash
pip install numpy scipy matplotlib
```

Tkinter normalmente viene incluido con Python. En caso de no estar disponible:

### Ubuntu / Debian

```bash
sudo apt install python3-tk
```

### Windows

Tkinter suele instalarse automáticamente junto con Python.

---

# Ejecutar simulación 2D

```bash
python metodos_proyecto_2d.py
```

# Ejecutar simulación 3D

```bash
python metodos_proyecto_3d.py
```

---

# Autores

Ana Sofía Ceron Bonilla  
Nicolle Rodríguez Estupiñán

Universidad EAFIT  
Curso: Métodos Numéricos  
2026

---
- simulación científica

---

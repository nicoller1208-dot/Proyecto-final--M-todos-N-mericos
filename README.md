# Simulación Numérica de la Ecuación de Schrödinger en 2D y 3D mediante FEM y Crank–Nicolson

Proyecto final del curso de Métodos Numéricos enfocado en la simulación de la ecuación de Schrödinger dependiente del tiempo utilizando el Método de Elementos Finitos (FEM) y el esquema temporal de Crank–Nicolson en dos y tres dimensiones.

## Descripción del Proyecto

Este proyecto desarrolla un solucionador numérico para la ecuación de Schrödinger dependiente del tiempo, implementado en Python mediante matrices dispersas y técnicas de simulación científica.

La formulación empleada combina:

- Método de Elementos Finitos (FEM)
- Integración temporal implícita de Crank–Nicolson
- Matrices dispersas en formatos LIL, DOK y CSR
- Solución de sistemas lineales mediante SciPy

El proyecto permite estudiar distintos fenómenos físicos asociados a la mecánica cuántica, incluyendo:

- Propagación libre de paquetes gaussianos
- Confinamiento armónico
- Barreras de potencial
- Doble pozo
- Potenciales coulombianos
- Sistemas tridimensionales confinados

Además del desarrollo computacional, el proyecto incluye material audiovisual y divulgativo realizado como parte de las entregas académicas.

---

## Contexto Matemático y Físico

La ecuación de Schrödinger dependiente del tiempo describe la evolución temporal de sistemas cuánticos:

\[
i\hbar \frac{\partial \psi}{\partial t}
=
-\frac{\hbar^2}{2m}\nabla^2 \psi + V\psi
\]

La discretización espacial se realizó mediante FEM:

- Elementos cuadriláteros bilineales Q4 en 2D
- Elementos hexaédricos H8 en 3D

La evolución temporal se implementó usando el esquema de Crank–Nicolson:

\[
\left(
\frac{i\hbar}{\Delta t}M + \frac{1}{2}H
\right)\Psi^{n+1}
=
\left(
\frac{i\hbar}{\Delta t}M - \frac{1}{2}H
\right)\Psi^{n}
\]

---

## Características Principales

### Simulación FEM en 2D y 3D
- Implementación completa del método de elementos finitos.
- Ensamblaje de matrices globales dispersas.
- Condiciones de frontera tipo Dirichlet.

### Integración Temporal Estable
- Método implícito de Crank–Nicolson.
- Conservación aproximada de probabilidad.
- Estabilidad energética durante la simulación.

### Potenciales Implementados
- Libre
- Armónico
- Barrera
- Barrera doble
- Doble pozo
- Coulombiano regularizado
- Caja cuántica

### Visualización y Análisis
- Evolución temporal de densidad de probabilidad.
- Animaciones de simulaciones.
- Visualización de cortes planos en 3D.
- Análisis de:
  - norma cuántica
  - energía esperada
  - convergencia espacial
  - posición esperada

### Interfaz Gráfica
Los simuladores incluyen interfaz gráfica desarrollada con Tkinter para:

- Configuración de parámetros
- Selección de potenciales
- Ejecución de simulaciones
- Exportación de resultados y figuras

---

## Tecnologías Utilizadas

- Python
- NumPy
- SciPy
- Matplotlib
- Tkinter

---

## Estructura del Repositorio

```text
Proyecto-final--M-todos-N-mericos/
│
├── metodos_proyecto_2d.py
├── metodos_proyecto_3d.py
│
├── Informe_final.pdf
│
├── README.md
│
├── Entregas/
│   ├── carrusel_canva/
│   ├── reel_resumen/
│   └── avances/
│
└── recursos/

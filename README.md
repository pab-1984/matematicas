# Repositorio de Matemáticas 🧠

¡Bienvenido! Este repositorio está dedicado a la exploración de diversos temas matemáticos, desde conceptos intermedios hasta investigaciones avanzadas. El objetivo es proporcionar un recurso claro y práctico para el aprendizaje y la experimentación.

## Estructura del Repositorio

El contenido está organizado en las siguientes carpetas:

-   **/cursos**: Apuntes, ejercicios y material de apoyo para diferentes cursos de matemáticas.
-   **/investigaciones**: Artículos, notas y exploraciones sobre temas de investigación específicos.
-   **/codigo**: Implementaciones y ejemplos en código para ilustrar conceptos matemáticos.

## ¿Cómo Empezar?

1.  **Explora las carpetas**: Navega por los directorios para encontrar el tema de tu interés.
2.  **Revisa el código**: La carpeta `/codigo` contiene ejemplos prácticos. Cada subdirectorio explica qué problema resuelve y cómo ejecutarlo.
3.  **Contribuye**: Si tienes material que te gustaría agregar, ¡las contribuciones son bienvenidas! Consulta la guía para contribuir (`CONTRIBUTING.md`) para más detalles.

---

## Sugerencias de Contenido

A continuación se presenta una lista de temas sugeridos, divididos por nivel de dificultad, que pueden ser incluidos en este repositorio.

### Contenido Intermedio

-   **Álgebra Lineal Numérica**:
    -   Descomposición en valores singulares (SVD) y sus aplicaciones en compresión de imágenes.
    -   Métodos iterativos para resolver sistemas de ecuaciones lineales (Jacobi, Gauss-Seidel).
-   **Ecuaciones Diferenciales Parciales (EDP)**:
    -   Ecuación del calor y de ondas: deducción y soluciones fundamentales.
    -   Introducción al método de elementos finitos para resolver EDPs numéricamente.
-   **Análisis Complejo**:
    -   Teorema del residuo y su aplicación al cálculo de integrales reales.
    -   Mapeos conformes y sus aplicaciones en física e ingeniería.

### Contenido Avanzado

-   **Topología Algebraica**:
    -   Homotopía y grupo fundamental.
    -   Homología simplicial y su cálculo para superficies simples.
-   **Geometría Algebraica**:
    -   Variedades afines y proyectivas.
    -   Teorema de los ceros de Hilbert (Nullstellensatz).
-   **Teoría de Números Analítica**:
    -   La función Zeta de Riemann y su conexión con los números primos.
    -   El Teorema de los Números Primos.

---

## Ejemplos de Código para Visualización

Usar código es una excelente manera de visualizar y "sentir" los conceptos matemáticos.

### Visualización del Atractor de Lorenz (Caos y Sistemas Dinámicos)

-   **Concepto**: Mostrar cómo un sistema de ecuaciones diferenciales determinista puede generar un comportamiento caótico y un fractal conocido como el atractor de Lorenz.
-   **Implementación**: Un script en **Python** con `matplotlib` y `scipy` para resolver el sistema y graficar la trayectoria en 3D.

    ```python
    import numpy as np
    import matplotlib.pyplot as plt
    from scipy.integrate import solve_ivp

    # Parámetros de Lorenz
    sigma, rho, beta = 10, 28, 8/3

    # Sistema de Ecuaciones de Lorenz
    def lorenz(t, xyz):
        x, y, z = xyz
        dxdt = sigma * (y - x)
        dydt = x * (rho - z) - y
        dzdt = x * y - beta * z
        return [dxdt, dydt, dzdt]

    # Condiciones iniciales y tiempo de integración
    xyz0 = [0, 1, 1.05]
    t_span = [0, 100]
    t_eval = np.linspace(t_span[0], t_span[1], 10000)

    # Resolver el sistema
    sol = solve_ivp(lorenz, t_span, xyz0, t_eval=t_eval)

    # Graficar el resultado
    fig = plt.figure(figsize=(12, 9))
    ax = fig.add_subplot(111, projection='3d')
    ax.plot(sol.y[0], sol.y[1], sol.y[2], lw=0.5)
    ax.set_title("Atractor de Lorenz")
    plt.show()
    ```

### Fractal de Mandelbrot (Análisis Complejo)

-   **Concepto**: Visualizar el conjunto de Mandelbrot, un famoso fractal en el plano complejo.
-   **Implementación**: Un script en **Python** con `numpy` y `matplotlib` que itera la función $f_c(z) = z^2 + c$ para cada punto $c$ del plano complejo y colorea según la velocidad de divergencia.

### Paseo Aleatorio y Movimiento Browniano (Probabilidad)

-   **Concepto**: Simular un paseo aleatorio en 1D o 2D como una aproximación discreta al movimiento browniano.
-   **Implementación**: Un script en **Python** que simula los pasos y grafica la trayectoria resultante. Es una excelente introducción visual a los procesos estocásticos.

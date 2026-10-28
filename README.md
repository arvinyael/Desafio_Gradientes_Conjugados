# Simulador de Ajustes Presupuestarios y Estructura de Costos Corporativos

### Métodos Numéricos — Desafío Académico: Método de Gradientes Conjugados Precondicionado (GCP)

---

## Información Institucional y Personal

* **Universidad:** Universidad Mayor de San Andrés (UMSA)
* **Facultad:** Facultad de Ciencias Puras y Naturales (FCPN)
* **Carrera:** Licenciatura en Informática
* **Materia:** Métodos Numéricos
* **Mención Académica:** Desarrollo de Software e Innovación Tecnológica
* **Estudiante:** Arvin Yael Vargas Condori
* **Base Teórica:** Fundamentado en el artículo científico *"Método de Gradientes Conjugados Precondicionado"* de Porfirio Suñagua S. (Revista Boliviana de Matemática UMSA, 2020).

---

## 1. Descripción del Proyecto

Este proyecto consiste en un simulador web interactivo y reactivo diseñado para resolver problemas de optimización y ajuste presupuestario corporativo ($n \ge 4$). El sistema modela la interacción de costos entre departamentos mediante un sistema lineal de ecuaciones $Ax = b$, donde $A$ es una matriz cuadrada, simétrica y definida positiva.

La aplicación permite evaluar y diagnosticar la precisión, el número de condición ($\kappa$) y la velocidad de convergencia del **Método de Gradientes Conjugados Precondicionado (GCP)** frente al método de Gradientes Conjugados (GC) simple y a soluciones directas de referencia (Factorización de Cholesky) bajo tres escenarios financieros: **Ideal**, **Bajo Estrés Financiero** y **Mal Condicionado**.

---

## 2. Arquitectura de Software y Estructura del Repositorio

El proyecto se diseñó bajo una arquitectura cliente (Frontend SPA) liviana, modular y declarativa, orientada al rendimiento en tiempo real sin dependencias de servidores backend pesados.

### Estructura de Archivos

```text
├── index.html       # Estructura semántica HTML5 con los 10 módulos obligatorios.
├── style.css        # Estilos personalizados, animaciones y diseño responsivo.
├── script.js        # Motor matemático (GCP, GC, Cholesky, Kappa, validaciones QA) y renderizado UI.
└── README.md        # Documentación técnica del repositorio y guía de ejecución.
```

### Componentes y Bibliotecas Utilizadas
* **HTML5 / CSS3 (Tailwind CSS CDN):** Interfaz moderna, responsiva y adaptable a dispositivos móviles y de escritorio.
* **JavaScript ES6+ (Vanilla JS):** Implementación nativa y optimizada de los algoritmos de álgebra lineal numérica.
* **Chart.js:** Visualización interactiva mediante gráficos de velocidad de convergencia de residuos iterativos en escala logarítmica.

---

## 3. Fundamentación Matemática y Financiera

### Variables del Modelo ($n = 4$)
1. **$x_1$:** Presupuesto de Nómina y Talento Humano.
2. **$x_2$:** Costos de Infraestructura Cloud y Servidores.
3. **$x_3$:** Inversión en Investigación y Desarrollo (I+D).
4. **$x_4$:** Gastos de Logística y Operaciones Generales.

### Propiedades de la Matriz $A$
* **Simetría ($A = A^\top$):** Refleja la reciprocidad en las interacciones de costos indirectos entre áreas corporativas ($a_{ij} = a_{ji}$).
* **Definida Positiva ($x^\top A x > 0, \forall x \neq 0$):** Garantiza que el sistema posea una única solución óptima y asegura la convergencia teórica del algoritmo de Gradientes Conjugados.

---

## 4. Instrucciones de Instalación y Ejecución Local

No se requiere la instalación de gestores de paquetes como Node.js (npm) ni entornos de ejecución complejos, ya que la aplicación se ejecuta de manera nativa en cualquier navegador web moderno.

### Opción 1: Ejecución Directa en el Navegador

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/tu-usuario/desafio-gcp-finanzas.git
   cd desafio-gcp-finanzas
   ```

2. **Abrir la aplicación:**
   * Haz doble clic en el archivo `index.html` o ábrelo directamente desde tu navegador preferido (Chrome, Firefox, Edge, Safari).

---

### Opción 2: Servidor de Desarrollo Local (Recomendado)

Si utilizas Visual Studio Code:

1. Instala la extensión **Live Server**.
2. Haz clic derecho sobre `index.html`.
3. Selecciona **Open with Live Server**.
4. La aplicación se desplegará en `http://127.0.0.1:5500`.

---

## 5. Módulo de Pruebas de Software (QA)

La aplicación incluye un sistema de validación interna que captura excepciones matemáticas antes de procesar los algoritmos:

| Caso de Prueba | Entrada | Resultado Esperado | Conclusión |
| :--- | :--- | :--- | :---: |
| **Carga de Escenarios** | Clic en "Escenario Mal Condicionado" | Carga instantánea de matriz $A$ y vector $b$, recálculo de soluciones y gráfica | **Aprobado ✔** |
| **Matriz Asimétrica** | Introducción de $a_{12} \neq a_{21}$ | Notificación de error en la interfaz sin caída del software | **Aprobado ✔** |
| **Edición Dinámica** | Cambio manual de $a_{11}$ en la tabla | Actualización reactiva inmediata de errores y vectores solución | **Aprobado ✔** |
| **Comparativa GCP vs GC** | Ejecución con $\kappa(A) \gg 1$ | GCP converge en menos iteraciones que el método GC simple | **Aprobado ✔** |

---

## 6. Referencias Bibliográficas

1. **Suñagua S., P. (2020).** *Método de Gradientes Conjugados Precondicionado.* Revista Boliviana de Matemática, UMSA, 04, 2–7.
2. **Golub, G. H., & Van Loan, C. F. (2013).** *Matrix Computations* (4th ed.). Johns Hopkins University Press.
3. **Saad, Y. (2003).** *Iterative Methods for Sparse Linear Systems* (2nd ed.). SIAM.
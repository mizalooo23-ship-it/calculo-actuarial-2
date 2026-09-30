# CALCULO-ACTUARIAL-II
RESUMEN DE CONTENIDO
FLORES CARRETERO LINO MISAEL
---

# Resumen: Cálculo Actuarial II - Unidad I
**Preliminares probabilísticos y entorno computacional reproducible**

---

## 1. Propósito y Enfoque del Curso
* El cálculo actuarial modela obligaciones inciertas representando matemáticamente eventos, montos y tiempos de pago.
* La relación fundamental del curso expresa el valor actuarial como la esperanza del valor presente aleatorio ($\mathbb{E}[\text{valor presente aleatorio}]$).
* El flujo de trabajo garantiza la **reproducibilidad**, conectando modelos matemáticos, implementación en código, datos públicos y pruebas de contraste.

---

## 2. Entorno Computacional y Git
* **Herramientas base:** Se utiliza Python, Git, Visual Studio Code (VS Code) y GitHub para asegurar trazabilidad y control de versiones.
* **Estructura del repositorio:** Obligatoriamente se organizan directorios para datos (`data/raw`, `data/processed`), código (`src/`), notebooks (`notebooks/`), pruebas (`tests/`), figuras y reportes.
* **Ciclo diario de Git:** Los comandos fundamentales para el control de cambios son `git status`, `git add`, `git commit`, `git pull` y `git push`.
* **Buenas prácticas:** Nunca se deben subir contraseñas, tokens de API o archivos grandes de datos crudos al repositorio público; para ello se configura el archivo `.gitignore`.

---

## 3. Python Esencial para Modelar Riesgo
* Se emplean tipos numéricos con separadores de legibilidad (como `500_000`) y funciones para encapsular fórmulas de costos esperados.
* **Bibliotecas clave:** 
  * `NumPy` para cálculo vectorizado en carteras.
  * `Pandas` para la manipulación estructurada de tablas de datos.
  * `Matplotlib` para la generación de gráficas de diagnóstico.
  * `SciPy` para el manejo de distribuciones de probabilidad continuas y discretas.
* La reproducibilidad estricta se logra mediante el uso de semillas pseudoaleatorias (ej. `np.random.default_rng`).

---

## 4. Lenguaje de Probabilidad y Espacios Medibles
* Un espacio de probabilidad se define mediante la terna $(\Omega, \mathcal{F}, \mathbb{P})$, donde $\Omega$ es el espacio muestral, $\mathcal{F}$ es la $\sigma$-álgebra de eventos medibles y $\mathbb{P}$ es la medida de probabilidad.
* **Herramientas condicionales:** Se fundamenta el uso de probabilidad condicional, la ley de probabilidad total y el Teorema de Bayes para actualizar escenarios de riesgo ante nueva información.
* La independencia entre eventos simplifica el análisis de carteras, aunque los choques sistémicos o catastróficos invalidan este supuesto si hay dependencia común.

---

## 5. Variables Aleatorias y Momentos
* Una variable aleatoria es una función medible que mapea el espacio muestral hacia los números reales.
* **Medidas de resumen:** 
  * La **esperanza** ($\mathbb{E}[X]$) representa el promedio del modelo y cumple la propiedad de linealidad incluso sin independencia.
  * La **varianza** ($\text{Var}(X)$) y la **covarianza** miden la dispersión y la dependencia entre riesgos, componentes críticos para calcular carteras agregadas.
* Las transformaciones de pérdidas permiten modelar contratos de seguros reales mediante deducibles y límites operativos ($\mathbb{E}[(X-d)_+]$).

---

## 6. Distribuciones Fundamentales en Seguros
* **Discretas:** 
  * *Bernoulli:* Modela el éxito o fracaso de un riesgo individual (ej. ocurrencia de siniestro).
  * *Binomial:* Suma de riesgos Bernoulli idénticos e independientes.
  * *Poisson:* Modela conteos de reclamaciones raras; requiere diagnosticar la equidispersión ($\text{Var}(N) = \mathbb{E}[N]$).
* **Continuas:**
  * *Exponencial:* Caracterizada por una fuerza de mortalidad constante y la propiedad de falta de memoria.
  * *Gamma y Normal:* Empleadas para modelar severidades con sesgo positivo o aproximaciones mediante el Teorema Central del Límite.

---

## 7. Riesgo Agregado y Datos de México
* **Modelación colectiva:** El riesgo agregado se expresa como $S = \sum_{j=1}^{N} X_j$, combinando frecuencias y severidades mediante esperanza condicional.
* **Lectura crítica de estadísticas oficiales:** Al trabajar con fuentes del INEGI (como las Estadísticas de Defunciones Registradas - EDR), es obligatorio distinguir con precisión entre un **conteo absoluto**, una **tasa bruta poblacional** y una **probabilidad individual ($q_x$)**, evitando sesgos por entidades de ocurrencia o estructuras de edad.

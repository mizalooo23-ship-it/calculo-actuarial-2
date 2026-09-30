# CALCULO-ACTUARIAL-II
FLORES CARRETERO LINO MISAEL
RESUMEN DE CONTENIDO

---

# Resumen: Cálculo Actuarial II - Unidad I
**Preliminares probabilísticos y entorno computacional reproducible**

---

## 1. Propósito y Enfoque del Curso
* El cálculo actuarial modela obligaciones inciertas representando matemáticamente eventos, montos y tiempos de pago[span_0](start_span)[span_0](end_span).
* La relación fundamental del curso expresa el valor actuarial como la esperanza del valor presente aleatorio ($\text{E}[\text{valor presente aleatorio}]$)[span_1](start_span)[span_1](end_span).
* El flujo de trabajo garantiza la **reproducibilidad**, conectando modelos matemáticos, implementación en código, datos públicos y pruebas de contraste[span_2](start_span)[span_2](end_span)[span_3](start_span)[span_3](end_span).

---

## 2. Entorno Computacional y Git
* **Herramientas base:** Se utiliza Python, Git, Visual Studio Code (VS Code) y GitHub para asegurar trazabilidad y control de versiones[span_4](start_span)[span_4](end_span)[span_5](start_span)[span_5](end_span).
* **Estructura del repositorio:** Obligatoriamente se organizan directorios para datos (`data/raw`, `data/processed`), código (`src/`), notebooks (`notebooks/`), pruebas (`tests/`), figuras y reportes[span_6](start_span)[span_6](end_span).
* **Ciclo diario de Git:** Los comandos fundamentales para el control de cambios son `git status`, `git add`, `git commit`, `git pull` y `git push`[span_7](start_span)[span_7](end_span).
* **Buenas prácticas:** Nunca se deben subir contraseñas, tokens de API o archivos grandes de datos crudos al repositorio público; para ello se configura el archivo `.gitignore`[span_8](start_span)[span_8](end_span)[span_9](start_span)[span_9](end_span)[span_10](start_span)[span_10](end_span).

---

## 3. Python Esencial para Modelar Riesgo
* Se emplean tipos numéricos con separadores delegibilidad (como `500_000`) y funciones para encapsular fórmulas de costos esperados[span_11](start_span)[span_11](end_span)[span_12](start_span)[span_12](end_span).
* **Bibliotecas clave:** 
  * `NumPy` para cálculo vectorizado en carteras[span_13](start_span)[span_13](end_span).
  * `Pandas` para la manipulación estructurada de tablas de datos[span_14](start_span)[span_14](end_span).
  * `Matplotlib` para la generación de gráficas de diagnóstico[span_15](start_span)[span_15](end_span).
  * `SciPy` para el manejo de distribuciones de probabilidad continuas y discretas[span_16](start_span)[span_16](end_span)[span_17](start_span)[span_17](end_span).
* La reproducibilidad estricta se logra mediante el uso de semillas pseudoaleatorias (ej. `np.random.default_rng`)[span_18](start_span)[span_18](end_span).

---

## 4. Lenguaje de Probabilidad y Espacios Medibles
* Un espacio de probabilidad se define mediante la terna $(\Omega, \mathcal{F}, \mathbb{P})$, donde $\Omega$ es el espacio muestral, $\mathcal{F}$ es la $\sigma$-álgebra de eventos medibles y $\mathbb{P}$ es la medida de probabilidad[span_19](start_span)[span_19](end_span).
* **Herramientas condicionales:** Se fundamenta el uso de probabilidad condicional, la ley de probabilidad total y el Teorema de Bayes para actualizar escenarios de riesgo ante nueva información[span_20](start_span)[span_20](end_span)[span_21](start_span)[span_21](end_span).
* La independencia entre eventos simplifica el análisis de carteras, aunque los choques sistémicos o catastróficos invalidan este supuesto si hay dependencia común[span_22](start_span)[span_22](end_span).

---

## 5. Variables Aleatorias y Momentos
* Una variable aleatoria es una función medible que mapea el espacio muestral hacia los números reales[span_23](start_span)[span_23](end_span).
* **Medidas de resumen:** 
  * La **esperanza** ($\mathbb{E}[X]$) representa el promedio del modelo y cumple la propiedad de linealidad incluso sin independencia[span_24](start_span)[span_24](end_span).
  * La **varianza** ($\text{Var}(X)$) y la **covarianza** miden la dispersión y la dependencia entre riesgos, componentes críticos para calcular carteras agregadas[span_25](start_span)[span_25](end_span).
* Las transformaciones de pérdidas permiten modelar contratos de seguros reales mediante deducibles y límites operativos ($\text{E}[(X-d)_+]$)[span_26](start_span)[span_26](end_span)[span_27](start_span)[span_27](end_span).

---

## 6. Distribuciones Fundamentales en Seguros
* **Discretas:** 
  * *Bernoulli:* Modela el éxito o fracaso de un riesgo individual (ej. ocurrencia de siniestro)[span_28](start_span)[span_28](end_span).
  * *Binomial:* Suma de riesgos Bernoulli idénticos e independientes[span_29](start_span)[span_29](end_span).
  * *Poisson:* Modela conteos de reclamaciones raras; requiere diagnosticar la equidispersión ($\text{Var}(N) = \mathbb{E}[N]$)[span_30](start_span)[span_30](end_span).
* **Continuas:**
  * *Exponencial:* Caracterizada por una fuerza de mortalidad constante y la propiedad de falta de memoria[span_31](start_span)[span_31](end_span)[span_32](start_span)[span_32](end_span).
  * *Gamma y Normal:* Empleadas para modelar severidades con sesgo positivo o aproximaciones mediante el Teorema Central del Límite[span_33](start_span)[span_33](end_span).

---

## 7. Riesgo Agregado y Datos de México
* **Modelación colectiva:** El riesgo agregado se expresa como $S = \sum_{j=1}^{N} X_j$, combinando frecuencias y severidades mediante esperanza condicional[span_34](start_span)[span_34](end_span).
* **Lectura crítica de estadísticas oficiales:** Al trabajar con fuentes del INEGI (como las Estadísticas de Defunciones Registradas - EDR), es obligatorio distinguir con precisión entre un **conteo absoluto**, una **tasa bruta poblacional** y una **probabilidad individual ($q_x$)**, evitando sesgos por entidades de ocurrencia o estructuras de edad[span_35](start_span)[span_35](end_span)[span_36](start_span)[span_36](end_span)[span_37](start_span)[span_37](end_span).

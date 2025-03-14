# Simulación del PhizerGate en NetLogo

## 📌 Objetivo de la Simulación
Esta simulación modela el impacto en la confianza de los inversores debido a la propagación de un bulo sobre Pfizer, provocando una caída en la bolsa y su posterior recuperación.

---

## Conversación con NetLogo para crear la simulación
- https://chatgpt.com/share/67d41c31-4354-8005-b238-ae714837cfa5

## 🏦 Aspectos Clave de la Simulación

### **1️⃣ Tipos de Inversores**
- **Institucionales (3%)** → Reaccionan con menos pánico.
- **Especuladores (50%)** → Reaccionan de manera más agresiva.
- **Minoristas (resto)** → Son los más influenciados por el pánico.

Los porcentajes de cada tipo de inversor se configuran mediante **sliders** en la interfaz de NetLogo.

### **2️⃣ Factores de Decisión de los Inversores**
- **Nivel de pánico** (según tipo de inversor).
- **Exposición al bulo** (ajustable en redes sociales, periódicos, TV, WhatsApp).
- **Intervención gubernamental** (0-100% en un slider, donde 100% puede bloquear la bolsa).

### **3️⃣ Propagación del Bulo**
- Modelada como una red **“pequeño mundo”** o **aleatoria** (ajustable desde un selector en NetLogo).
- Se propaga cada cierto tiempo (ajustable con un slider, valor inicial **30 días**).
- La reacción del mercado es **instantánea**.

### **4️⃣ Caída y Recuperación de la Acción**
- Relación **no lineal** entre pánico y caída del precio:
  - Si el **10% de inversores** entra en pánico → la acción baja **5%**.
  - Si el **50% de inversores** entra en pánico → la acción baja **30%**.
- **Corrección del precio** tras el desmentido del bulo.

### **5️⃣ Parámetros Ajustables en NetLogo**
- **Probabilidad de venta si se cree en el bulo** (slider, valor inicial 60%).
- **Influencia social** entre inversores (pánico colectivo).
- **Estrategias de trading** (algunos compran barato en la caída).

---

## 🛠 Implementación en NetLogo

### **🔧 Correcciones realizadas en el código:**

1. **Ejecutar la simulación de forma continua**:
   - Se modificó la función `go` para ejecutarse en bucle hasta que la acción llegue a 0 o pase un año (365 ticks).
   - Se configuró el botón `Go` para ejecutarse en modo **Forever**.

2. **Controlar la cantidad de cada tipo de inversor con sliders:**
   - Se añadieron sliders en la interfaz para definir los porcentajes de cada tipo de actor antes de la simulación.
   - Se ajustó la creación de inversores en `create-investors` para que respete estos valores dinámicamente.

3. **Añadir una gráfica de evolución de actores:**
   - Se creó un **plot** llamado `Evolución de Inversores`.
   - Se añaden tres series (`Institucionales`, `Especuladores`, `Minoristas`) para visualizar la variación de sus cantidades a lo largo del tiempo.

4. **Modificación de la reacción del mercado:**
   - Se ajustó `market-reaction` para aplicar la caída no lineal de la acción.

5. **Corrección del bulo y recuperación del mercado:**
   - Se agregó una función `correct-bulo` que recupera la confianza y estabiliza el precio con base en `trust-in-desmentido`.

---

## 🚀 Pasos para Ejecutar la Simulación en NetLogo

### **1️⃣ Configurar NetLogo**
1. **Abrir NetLogo** y crear un nuevo proyecto.
2. **Copiar y pegar el código** en la pestaña **Code**.
3. **Configurar la interfaz**:
   - **Botón `Setup`** para inicializar la simulación.
   - **Botón `Go`** en modo `Forever` para que la simulación corra automáticamente.
   - **Sliders** para ajustar los parámetros de la simulación.
   - **Monitor del precio de la acción** (`stock-price`).
   - **Monitor del nivel de pánico** (`panic-level`).
   - **Gráfica `Evolución de Inversores`** para visualizar cambios en la cantidad de actores.

4. **Ejecutar la simulación** con `Setup` → `Go` y analizar los resultados.

---

## 📈 Posibles Mejoras Futuras
- **Añadir gráficos adicionales** para visualizar la evolución del precio de la acción.
- **Implementar estrategias de control gubernamental dinámicas**.
- **Incorporar nuevas variables macroeconómicas** (tasas de interés, confianza del consumidor).
- **Agregar un módulo de aprendizaje automático** para ajustar dinámicamente los parámetros de la simulación.

---

Con estos cambios, la simulación permite estudiar el impacto de la desinformación en el mercado financiero y explorar estrategias de mitigación. 🚀📊

### 👥 Autores
- Investigación: Jonás
- Implementación en NetLogo: [Tu Nombre]
- Asistencia en Modelado: ChatGPT 😃



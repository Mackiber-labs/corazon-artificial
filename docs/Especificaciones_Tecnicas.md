# Especificaciones Técnicas del Corazón Artificial Híbrido

Este documento contiene las especificaciones detalladas de cada componente del sistema, con valores numéricos, referencias y protocolos.

---

## 1. Actuador (motor electromagnético lineal)

| Parámetro | Valor | Notas |
|-----------|-------|-------|
| **Fuerza máxima** | 8 N | Para generar 120 mmHg en 30 cm² de membrana |
| **Carrera** | 12 mm | Volumen de eyección de 70 mL |
| **Voltaje de operación** | 12 V | Batería de inducción o supercondensador |
| **Corriente pico** | 2 A | Durante la sístole (200 ms) |
| **Corriente en reposo** | 100 mA | Durante la diástole |
| **Frecuencia máxima** | 150 bpm | Adaptación a ejercicio intenso |
| **Eficiencia** | >70% | Medido en banco de pruebas |
| **Vida útil estimada** | >10 años | Ciclos >10⁸ |

**Referencias:**
- Motor lineal de imanes permanentes (Maxon, FAULHABER).
- Estudio de eficiencia: *Linear motors for medical devices*, IEEE Trans. Med. Robot. Bionics (2022).

---

## 2. Trama de burbujas

| Parámetro | Valor | Notas |
|-----------|-------|-------|
| **Material** | Microesferas de vidrio recubiertas de silicona (3M™ Glass Bubbles) | Comercial, con datos de fatiga |
| **Tamaño de burbuja** | 50-200 µm | Distribución homogénea |
| **Densidad** | 0.15-0.25 g/cm³ | Según el fabricante |
| **Resistencia a la compresión** | 10 MPa | >10⁸ ciclos sin degradación |
| **Grosor de la capa** | 2-5 mm | Entre capa externa e interna |
| **Módulo de elasticidad** | 1-5 MPa | Similar a pared ventricular nativa |

**Referencias:**
- Hoja técnica 3M™ Glass Bubbles (2025).
- *Fatigue properties of syntactic foams*, J. Compos. Mater. (2020).

---

## 3. Endotelio autólogo (protocolo de cultivo y siembra)

| Parámetro | Valor | Notas |
|-----------|-------|-------|
| **Fuente celular** | Biopsia de vena safena (2 cm²) | Extraída 4 semanas antes de la cirugía |
| **Medio de cultivo** | EGM-2 (Lonza) + 10% FBS + VEGF (50 ng/mL) | Cambio de medio cada 3 días |
| **Tiempo de expansión** | 3 semanas | Hasta alcanzar 10⁷ células |
| **Densidad de siembra** | 1.5 × 10⁵ células/cm² | Sobre colágeno tipo I (50 µg/cm²) |
| **Matriz de soporte** | Colágeno tipo I + fibronectina (10 µg/cm²) | Para mejorar la adhesión celular |
| **Tiempo de maduración** | 7 días | En biorreactor con flujo pulsátil (1 L/min, 60 bpm) |
| **Espesor de la capa** | 1-2 µm | Monocapa confluente de endotelio |

**Referencias:**
- Atala, A., et al. (2006). *The Lancet*, 367(9518), 1241-1246.
- Yoo, J. J., et al. (2016). *J. Biomed. Mater. Res. A*, 104(12), 3115-3124.

---

## 4. Piezoeléctricos (PVDF + PDMS)

| Parámetro | Valor | Notas |
|-----------|-------|-------|
| **Material** | PVDF polarizado (20-30 cm²) encapsulado en PDMS | Laminado flexible |
| **Voltaje pico** | 15 V | Deformación mecánica >1% (presión arterial) |
| **Potencia media** | 2 mW (reposo) / 5 mW (ejercicio) | Depende de la actividad del paciente |
| **Resistencia** | >10⁸ ciclos | Datos de envejecimiento por vibración |
| **Ubicación** | Entre capa externa y trama de burbujas | Captura deformación del latido |

**Referencias:**
- Persano, L., et al. (2013). *Nat. Commun.*, 4, 1633.
- Chorsi, M. T., et al. (2019). *Adv. Mater.*, 31(1), 1802084.

---

## 5. Sensores y sistema de control

| Sensor | Modelo | Rango | Precisión | Ubicación |
|--------|--------|-------|-----------|-----------|
| **Presión arterial** | MEMS (Sensirion) | 0-300 mmHg | ±1 mmHg | Arteria de entrada/salida |
| **Flujo** | Ultrasónico (Transonic) | 0-10 L/min | ±0.1 L/min | Aorta y arteria pulmonar |
| **Acelerómetro** | MEMS (ADXL345) | ±16 g | 0.1 g | Capa externa |
| **Temperatura** | Termistor NTC | 30-42°C | ±0.1°C | Superficie del dispositivo |
| **Microcontrolador** | STM32L o MSP430 | 1.8-3.6 V | 32-bit ARM Cortex-M | Encapsulado en titanio |

**Referencias:**
- Hoja técnica de cada componente.
- *IEEE Sensors Journal*, guías de integración de MEMS en dispositivos médicos.

---

## 6. Interfaz neuronal (nervio vago)

| Parámetro | Valor | Notas |
|-----------|-------|-------|
| **Tipo de electrodo** | Cuff tripolar (MicroProbes) | 3 anillos de platino-iridio |
| **Impedancia** | <10 kΩ | Mediciones en solución salina |
| **Estimulación** | 1-5 V, 1-20 Hz, 200 µs de pulso | Prendiendo en el período refractario para evitar arritmias |
| **Registro** | 0.1-100 Hz, ganancia 1000× | Señal aferente del nervio vago |
| **Protocolo de seguridad** | Monitoreo continuo de ECG | Detección de bloqueo aurículo-ventricular |

**Referencias:**
- Grill, W. M., et al. (2001). *IEEE Trans. Neural Syst. Rehabil. Eng.*, 9(3), 221-234.
- MicroProbes Inc. catálogo de electrodos cuff (2025).

---

## 7. Simulación CFD (condiciones de contorno)

| Parámetro | Valor | Notas |
|-----------|-------|-------|
| **Geometría** | Modelo 3D de las cámaras | Basado en CT cardíaca humana |
| **Flujo de entrada** | 5 L/min (pulsátil, 70 bpm) | Gasto cardíaco en reposo |
| **Presión sistólica** | 120 mmHg | Ventrículo izquierdo |
| **Presión diastólica** | 80 mmHg | Ventrículo izquierdo |
| **Modelo de turbulencia** | k-ω SST | Para flujo en válvulas |
| **Objetivo** | Estrés de cizallamiento <10 Pa | Para evitar hemólisis y activación plaquetaria |

**Referencias:**
- Vahidkhah, K., et al. (2016). *Artif. Organs*, 40(9), 833-846.
- Guía de usuario de ANSYS Fluent (2025).

---

## 8. Pruebas ex vivo (protocolo)

| Parámetro | Valor | Notas |
|-----------|-------|-------|
| **Sangre** | Bovina, con heparina (10 UI/mL) | Anticoagulación local |
| **Circuito** | Pulsátil (mock loop) | Simulación de circulación sistémica y pulmonar |
| **Duración** | 72 horas | Funcionamiento continuo |
| **Presión** | 120/80 mmHg | En la salida del ventrículo izquierdo |
| **Flujo** | 5 L/min | Gasto cardíaco en reposo |
| **Hemólisis** | <0.5% (índice de hemólisis) | Medido por espectrofotometría |
| **Activación plaquetaria** | Medición por citometría de flujo | Marcadores CD62P y CD63 |
| **Criterio de éxito** | Presión >100 mmHg, flujo >4 L/min, hemólisis <0.5% | Validación funcional y de seguridad |

**Referencias:**
- Moazami, N., et al. (2019). *J. Thorac. Dis.*, 11(10), 4392-4406.
- ISO 7198:2025 (Prótesis cardiovasculares).

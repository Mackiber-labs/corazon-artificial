# Corazón Artificial Híbrido de Doble Capa

**Diseño conceptual de un corazón artificial implantable que elimina el cable externo, la anticoagulación obligatoria y permite adaptación en tiempo real al paciente.**

---

## 📌 Estado del proyecto

✅ Diseño conceptual completo  
✅ Especificaciones técnicas definidas  
🔲 Prototipo de laboratorio  
🔲 Simulación CFD  
🔲 Pruebas ex vivo  
🔲 Implantación en animales  
🔲 Ensayo clínico

---

## 🧠 Resumen ejecutivo

Este repositorio contiene el diseño de un **corazón artificial híbrido** que supera las limitaciones de los dispositivos actuales (neumáticos, cable externo, anticoagulación obligatoria).

La innovación principal es una **doble capa estructural** con una trama de burbujas de silicona que aloja un fluido circundante, eliminando la fricción y permitiendo un movimiento de cizallamiento suave. La capa interna está recubierta con **endotelio autólogo** para evitar trombosis y anticoagulación. La energía se obtiene mediante un sistema híbrido (piezoeléctricos + batería de inducción) y el control se realiza mediante una **IA en el borde conectada al nervio vago**, permitiendo una adaptación en tiempo real a la actividad del paciente.

**No hay baterías tóxicas ni cables externos.**

---

## 🏗️ Arquitectura general

| Capa | Material | Función |
|------|----------|---------|
| **Capa externa** | Silicona porosa + mesotelio autólogo | Integración con tejido circundante |
| **Trama de burbujas** | Microcápsulas de aire de silicona (50-200 μm) | Amortiguación hidráulica, distribución de presión |
| **Capa interna** | Endotelio autólogo + colágeno tipo I | Evita trombosis |
| **Soporte rígido** | Titanio o PEEK | Soporte para válvulas |

---

## ⚡ Componentes clave

| Subsistema | Tecnología | Especificaciones |
|------------|------------|------------------|
| **Actuación** | Motor electromagnético lineal | 8 N, 12 mm, 12 V, 2 A, >70% eficiencia |
| **Energía** | Piezoeléctricos PVDF+PDMS + inducción + supercondensador | 20-30 cm², 15 V pico, 2-5 mW continuos |
| **Control** | IA en el borde (TensorFlow Lite Micro) + interfaz con nervio vago | STM32L o MSP430, electrodos de cuff tripolares |
| **Válvulas** | Pericardio bovino (bicúspides y semilunares) | Anillo de sutura de silicona |

---

## 📂 Estructura del repositorio

- `/docs/` — Documentación completa del diseño.
- `/docs/Especificaciones_Tecnicas.md` — Tablas con parámetros detallados.
- `/cad/` — Archivos CAD (STL, STEP) del prototipo.
- `/simulacion/` — Archivos de simulación (CFD, COMSOL).
- `/firmware/` — Código de la IA y control de sensores.
- `/hardware/` — Esquemáticos eléctricos y lista de materiales (BOM).

---

## 🔗 Enlaces

- **Zenodo**: (DOI pendiente)
- **Documento completo**: `/docs/Diseno_Completo_v1.0.md`
- **Especificaciones técnicas**: `/docs/Especificaciones_Tecnicas.md`
- **Licencia**: CC BY-NC 4.0

---

## 👤 Autor

**Enrique Aguayo H.** — Mackiber Labs  
Contacto: eaguayo@migst.cl  
ORCID: 0009-0004-4615-6825  
GitHub: [@enriqueherbertag-lgtm](https://github.com/enriqueherbertag-lgtm)

---

## 🧾 Licencia

Este proyecto está bajo licencia **CC BY-NC 4.0**.  
Uso no comercial permitido con atribución.

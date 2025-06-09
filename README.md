# 🚀 Automatización de Facturas

## 📌 Descripción

Este proyecto tiene como objetivo automatizar el proceso de **recepción y carga de facturas** en SAP, eliminando la intervención manual que actualmente genera demoras y errores en la transcripción de datos. La solución se enfoca en agilizar la carga, validación y confirmación de facturas provenientes de diferentes fuentes (electrónicas, computarizadas y manuales).

---

## 🔗 Antecedentes / Dependencias

Actualmente el proceso se realiza de forma **manual**, lo cual ocasiona:

- Retrasos en la contabilización de facturas.
- Errores humanos por transcripción.
- Falta de visibilidad del estado de las facturas.

---

## 📈 Propuesta de Mejora (Fase 1)

### 1️⃣ Punto 0: Selección y Filtro de Datos

**Objetivo**: Desplegar una pantalla de selección con filtros relevantes para acotar las OC/OS listas para facturar.

**Campos de Filtro sugeridos**:

- Sociedad
- Organización de Compras
- Proveedor
- Fecha de pedido
- Segmento
- Ce.Coste

---

### 2️⃣ Punto 1: Carga de Archivos de Facturas

**Objetivo**: Cargar facturas en SAP de acuerdo con el tipo (electrónica, computarizada o manual) y validar sus datos.

**Tipos de carga soportados**:

- **Factura electrónica** → Archivo XML
- **Factura computarizada** → Archivo TXT (campos separados por `|`)
- **Factura manual** → Formulario manual en pantalla

**Validaciones clave**:

- Nombre del proveedor
- NIT
- Total de la factura
- Diferencias de importes (con tolerancia configurable desde `ZMMFI_CONFIG_FACTURA`)

**Columnas recomendadas** para este punto (ordenadas):

1. Línea sel.
2. Tipo de factura
3. Seleccionar archivo
4. XML
5. PDF
6. Cod.Proveedor
7. Nombre del proveedor
8. N°Factura
9. OS/OC
10. Fecha de Registro
11. Sociedad
12. Segmento
13. Ind.Impuesto
14. Gerencia
15. Importe en USD (Con IVA)
16. Importe en USD (Sin IVA)
17. Importe en BOB (Con IVA)
18. Importe en BOB (Sin IVA)
19. TotalFact.
20. Diferencia
21. Pos.
22. Cantidad de pedido
23. UMB
24. Texto breve
25. Fecha pedido
26. Moneda doc.
27. Info Log
28. Tipos de carga
29. Documento físico

---

### 3️⃣ Punto 2: Confirmación de Facturas (Similitud con MIRO)

**Objetivo**: Confirmar o rechazar facturas cargadas por proveedores y registrar resultados en SAP de forma masiva.

**Funcionalidades**:

- Revisión de facturas cargadas
- Confirmación masiva en SAP
- Rechazo con motivo/observación
- Log de errores/success para trazabilidad

**Columnas recomendadas**:

1. Línea sel.
2. Status
3. Estado de la factura
4. N°Factura
5. N°MIRO
6. N°FI
7. Sociedad
8. Gerencia
9. Cod.Proveedor
10. Nombre del proveedor
11. OS/OC
12. TotalFact.
13. Diferencia
14. Usuario que confirmó
15. Fecha base contab.
16. Fecha recepción
17. Fecha vencimiento factura
18. Log de errores
19. XML / PDF (visualización)
20. Moneda factura
21. Documento físico

---

### 4️⃣ Punto 3: Reporte de Estado de Facturas

**Objetivo**: Visualizar el estado completo de las facturas: listas para facturar, facturadas y por pagar.

**Filtros sugeridos**:

- Usuario que confirmó/rechazó
- Estado de la factura
- Fecha de registro
- Sociedad / Proveedor / Gerencia

**Columnas recomendadas**:

1. N°Factura
2. Estado de la factura
3. Fecha de Registro
4. Cod.Proveedor
5. Nombre del proveedor
6. Sociedad
7. Segmento
8. Gerencia
9. OS/OC
10. TotalFact.
11. Diferencia
12. Tipo de factura
13. Usuario confirmador
14. Fecha base contab.
15. Fecha vencimiento
16. Documento físico
17. Moneda factura

---

## 💡 Futuro del Proyecto

Esta solución busca asemejarse a **SAP ARIBA Network** en su funcionamiento, estableciendo un flujo estructurado de carga, validación, confirmación y visibilidad de facturas.

---

## 📂 Estructura del Repositorio (Propuesta)


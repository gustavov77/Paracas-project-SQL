# Paracas-project-SQL
Modelamiento de base de datos en una planta SWRO 
Caso Propuesto del Curso
Proyecto de Modelamiento de Datos
Tema: Gestión de Operaciones en una Planta de Ósmosis Inversa de Agua de Mar
1. Contexto General del Caso

La empresa ficticia AquaDesal Perú S.A. opera una planta desaladora de agua de mar mediante tecnología de ósmosis inversa ubicada en la costa peruana. La planta abastece agua potable a una ciudad costera y agua industrial a empresas mineras y energéticas.

En los últimos años, la organización ha tenido problemas relacionados con:

Falta de trazabilidad operativa.
Dificultad para controlar parámetros críticos de operación.
Poca integración entre mantenimiento, laboratorio y producción.
Ausencia de indicadores históricos confiables.
Problemas para analizar el rendimiento de membranas y consumo energético.
Reportes manuales y dispersos en Excel.

La gerencia decide implementar un Sistema de Gestión Operacional basado en Base de Datos que permita centralizar la información y mejorar la toma de decisiones.

Los estudiantes actuarán como analistas y modeladores de datos encargados de diseñar la solución de base de datos para la planta.

2. Objetivo del Proyecto

Diseñar un modelo de datos completo para gestionar la operación de una planta de tratamiento de agua de mar por ósmosis inversa.

El sistema deberá permitir:

Registrar producción de agua.
Monitorear variables operativas.
Gestionar equipos y mantenimiento.
Registrar limpiezas químicas (CIP).
Controlar calidad del agua.
Gestionar alarmas e incidencias.
Analizar desempeño energético y operacional.
3. Alcance del Sistema

El sistema abarcará las siguientes áreas:

Área	Descripción
Captación	Registro del agua de mar de ingreso
Pretratamiento	Filtración, coagulación, dosificación química
Ósmosis inversa	Operación de trenes y membranas
Postratamiento	Ajuste final del agua producto
Laboratorio	Calidad del agua
Mantenimiento	Gestión de activos y fallas
Energía	Consumo energético
Operaciones	Producción y KPIs
4. Procesos Principales del Negocio
A. Gestión de Producción

La planta opera 24/7 y produce agua desalinizada.

Se requiere registrar:

Fecha y hora.
Caudal de alimentación.
Caudal permeado.
Caudal rechazo.
Recuperación (%).
Conductividad.
Presiones.
Temperatura.
Producción diaria.
B. Gestión de Membranas

Cada tren de ósmosis posee membranas instaladas.

Se necesita registrar:

Código de membrana.
Marca y modelo.
Fecha de instalación.
Horas de operación.
Diferencial de presión.
Ensuciamiento.
Reemplazos.
C. Limpiezas CIP

Cuando las membranas pierden rendimiento se realizan limpiezas químicas.

Registrar:

Fecha de CIP.
Motivo.
Tipo de ensuciamiento.
Productos químicos usados.
Duración.
Resultado post-limpieza.
D. Gestión de Alarmas

El sistema debe registrar alarmas operativas:

Ejemplos:

Alta conductividad.
Baja presión.
Alta presión diferencial.
Baja producción.
Fallo de bomba.

Datos requeridos:

Fecha/hora.
Severidad.
Equipo asociado.
Estado.
Operador responsable.
E. Mantenimiento de Equipos

Equipos críticos:

Bombas de alta presión.
Bombas dosificadoras.
Filtros multimedia.
Cartuchos.
ERD.
Instrumentación.

Registrar:

Mantenimientos preventivos.
Correctivos.
Horas de parada.
Repuestos usados.
Técnicos responsables.
F. Laboratorio y Calidad

Registrar análisis de:

pH
Conductividad
SDI
Turbidez
Cloro libre
Boro
Sílice
TDS

Con trazabilidad por punto de muestreo.

5. Requerimientos Funcionales
El sistema debe permitir:
Operaciones
Registrar datos operativos cada hora.
Consultar históricos.
Generar KPIs.
Mantenimiento
Registrar órdenes de trabajo.
Programar mantenimientos.
Calidad
Registrar resultados de laboratorio.
Detectar incumplimientos.
Reportes
Producción diaria.
Consumo energético.
Disponibilidad de equipos.
Rendimiento de membranas.
6. Requerimientos No Funcionales
Base de datos relacional.
Multiusuario.
Integridad de datos.
Seguridad por roles.
Escalabilidad.
Auditoría de cambios.
7. Entidades Iniciales del Modelo
Posibles entidades del sistema
Entidad	Descripción
Planta	Información general
Área	Secciones operativas
Tren_RO	Trenes de ósmosis
Membrana	Membranas instaladas
Equipo	Activos físicos
Sensor	Instrumentación
Lectura_Operacional	Variables de operación
Alarma	Eventos críticos
CIP	Limpiezas químicas
Quimico	Productos químicos
Mantenimiento	Órdenes de trabajo
Operador	Personal operativo
Laboratorio	Resultados de análisis
Punto_Muestreo	Ubicación de muestras
8. Reglas de Negocio Iniciales
Un tren RO puede tener muchas membranas.
Una membrana pertenece a un solo tren.
Un equipo puede generar múltiples alarmas.
Un mantenimiento puede involucrar varios repuestos.
Cada lectura operacional pertenece a un sensor.
Un operador puede registrar múltiples eventos.
Un CIP puede aplicarse a uno o varios trenes.
Un análisis de laboratorio debe estar asociado a un punto de muestreo.
9. Objetivos Académicos del Curso

Los estudiantes deberán aprender a:

Levantar requerimientos.
Identificar entidades y atributos.
Construir modelos ER.
Aplicar normalización.
Diseñar claves primarias y foráneas.
Modelar relaciones complejas.
Implementar bases de datos SQL.
Generar consultas analíticas.
Diseñar dashboards operacionales.
10. Posibles Entregables del Proyecto
Fase 1
Análisis del negocio.
Requerimientos.
Fase 2
Modelo conceptual (ER).
Fase 3
Modelo lógico relacional.
Fase 4
Normalización.
Fase 5
Implementación SQL.
Fase 6
Consultas y KPIs.
Fase 7
Dashboard operacional.
11. KPIs que Podrían Analizarse
KPI	Fórmula
Recovery (%)	Permeado / Alimentación
Disponibilidad	Horas operativas / Horas totales
Rechazo de sales	% remoción
Consumo energético específico	kWh/m³
Fouling rate	ΔP / tiempo
Producción diaria	m³/día
12. Escenario Problemático para el Proyecto

Durante los últimos 6 meses:

El consumo energético aumentó 18%.
La frecuencia de CIP creció 25%.
La producción cayó 12%.
Existen alarmas repetitivas sin análisis histórico.
No se tiene trazabilidad adecuada de membranas.
Los reportes tardan horas en consolidarse.

La gerencia necesita una solución basada en datos para identificar causas y optimizar la operación.

13. Próximos Temas del Curso

Después del caso propuesto, podrían desarrollar:

Levantamiento de requerimientos.
Identificación de entidades.
Modelo entidad-relación.
Cardinalidades.
Normalización (1FN, 2FN, 3FN).
Modelo lógico.
SQL DDL.
SQL DML.
Consultas analíticas.
KPIs y dashboards.
Integración con Power BI.
Modelado dimensional para analítica.

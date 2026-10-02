# 🎯 Agent Skills Repository

Repositorio centralizado de **Agent Skills** modulares, especializadas y basadas en estándares de ingeniería de software, arquitectura de sistemas, modelado formal, diseño UX/UI, gestión de conocimiento y comunicación profesional.

Estas habilidades están diseñadas para ser consumidas y ejecutadas por agentes de Inteligencia Artificial (compatibles con **Google Antigravity**, **Claude Code**, **Cursor**, **Windsurf**, agentes basados en OpenAI y frameworks agénticos avanzados) conforme al estándar de carpetas `SKILL.md`.

> 📘 **Playbook de rutas**: Consultá la [**Guía de aplicación de skills para Sistemas de Información**](GUIA.md), que ayuda a seleccionar únicamente las skills y compuertas necesarias para cada producto. No es obligatorio ejecutar las 22.

> 🧾 **Registro de auditoría**: el [prompt, alcance y resultado de la auditoría ASI/DSI del 2026-09-04](audits/2026-09-04-auditoria-skills-asi-dsi.md) quedan versionados junto con las skills.

---

## 📌 Contenido

- [Guía de rutas y productos](GUIA.md)
- [Visión General y Propósito](#-visión-general-y-propósito)
- [Mapa del Ciclo de Vida de Software](#-mapa-del-ciclo-de-vida-de-software)
- [Catálogo de Skills](#-catálogo-de-skills)
  - [1. Requerimientos, Viabilidad y Procesos de Negocio](#1-requerimientos-viabilidad-y-procesos-de-negocio)
  - [2. Análisis Funcional y Especificación del Sistema](#2-análisis-funcional-y-especificación-del-sistema)
  - [3. Calidad y Arquitectura de Software](#3-calidad-y-arquitectura-de-software)
  - [4. Diseño Orientado a Objetos, Patrones y Persistencia](#4-diseño-orientado-a-objetos-patrones-y-persistencia)
  - [5. Modelado Visual y Diagramación Universal](#5-modelado-visual-y-diagramación-universal)
  - [6. Experiencia de Usuario, UI y Diseño Generativo](#6-experiencia-de-usuario-ui-y-diseño-generativo)
  - [7. Productividad y Gestión del Conocimiento](#7-productividad-y-gestión-del-conocimiento)
  - [8. Comunicación, Redacción y Oratoria Profesional](#8-comunicación-redacción-y-oratoria-profesional)
  - [9. Construcción de Backend y Pruebas](#9-construcción-de-backend-y-pruebas)
  - [10. Gestión y Mejora de Procesos (GMP / Ciclo PDCA)](#10-gestión-y-mejora-de-procesos-gmp--ciclo-pdca)
  - [11. Ingeniería de Carrera y Optimización Curricular](#11-ingeniería-de-carrera-y-optimización-curricular)
  - [12. Inteligencia Artificial Estructurada (TypeSafe)](#12-inteligencia-artificial-estructurada-typesafe)
- [Anatomía de una Skill](#-anatomía-de-una-skill)
- [Compatibilidad de nombres y agentes](#-compatibilidad-de-nombres-y-agentes)
- [Guía de Integración y Uso](#-guía-de-integración-y-uso)
- [Estándares y Fundamentos Académicos](#-estándares-y-fundamentos-académicos)
- [Buenas Prácticas de Contribución](#-buenas-prácticas-de-contribución)

---

## 🚀 Visión General y Propósito

A diferencia de prompts aislados, las **Agent Skills** de este repositorio definen un producto, sus entradas, límites, decisiones y criterios de cierre. Cada paquete incluye solo los recursos que necesita:

1. un `SKILL.md` conciso para alcance, flujo y contrato de salida;
2. `references/` para detalle condicional que cambia decisiones;
3. `templates/` cuando una estructura reutilizable mejora consistencia;
4. `scripts/` cuando una transformación o validación realmente puede automatizarse;
5. `examples/` breves cuando enseñan un comportamiento que las reglas no dejan claro.

El catálogo cubre productos de **Análisis de Sistemas de Información (ASI)**, **Diseño de Sistemas de Información (DSI)** y construcción downstream. Los marcos PUD/RUP, DDD, GRASP/GoF, ISO/IEC 25010 e IEEE 29148 se aplican únicamente donde aportan al artefacto solicitado.

---

## 🗺️ Mapa del Ciclo de Vida de Software

El siguiente diagrama muestra relaciones posibles entre productos. Las rutas se seleccionan según el encargo y los artefactos disponibles; las flechas no convierten el catálogo en un pipeline obligatorio.

```mermaid
flowchart TD
    subgraph Orquestacion_Academica["Modo académico transversal"]
        EPC[epc-flow-gen<br/><i>Orquestación de EPC académico</i>]
    end

    subgraph Relevamiento_y_Estrategia["Relevamiento & Viabilidad"]
        SC[system-classifier<br/><i>Encuadre por modo y evidencia</i>]
        RE[requirements-extractor<br/><i>Evidencia a requisitos</i>]
        BPMN[bpmn-extractor<br/><i>BPMN & Fichas</i>]
    end

    subgraph Analisis_del_Sistema["Análisis del Sistema (ASI)"]
        UCE[use-case-extractor<br/><i>Modelo y descripciones de CU</i>]
        DMG[domain-model-gen<br/><i>Modelo conceptual trazable</i>]
        CV[crud-validator<br/><i>Matriz CRUD diagnóstica</i>]
    end

    subgraph Arquitectura_y_Diseno["Arquitectura & Diseño (DSI)"]
        QSS[quality-scenario-specifier<br/><i>Escenarios según perfil</i>]
        MD[microservice-decomposer<br/><i>Decisión de límites & C4</i>]
        GSR[grasp-sequence-realizer<br/><i>RCU / DSD trazable</i>]
        DD[domain-design<br/><i>DCD trazable</i>]
        GOF[gof-adviser<br/><i>Decisión GoF opcional</i>]
        ROM[relational-object-map<br/><i>Mapeo relacional; DDL opcional</i>]
        UMLC[uml-consistency<br/><i>Auditoría cruzada UML</i>]
    end

    subgraph Construccion_Backend["Construcción de Backend & Pruebas"]
        ORM[orm-master<br/><i>Mapeo y consultas con evidencia</i>]
        API[api-design<br/><i>Contrato HTTP/OpenAPI</i>]
        TEST[backend-testing<br/><i>Pruebas según riesgo</i>]
    end

    subgraph Frontend_y_Visualizacion["Frontend & Visualización"]
        UXUI[design-ux-ui<br/><i>Artefacto UX/UI proporcional</i>]
        DS[diagramStudio<br/><i>Diagramación Universal Mermaid & Draw.io</i>]
    end

    subgraph Gestion_y_Mejora_Procesos["Gestión & Mejora de Procesos (GMP)"]
        PW[processWorkbench<br/><i>Orquestador Metodológico E1-E3</i>]
        OA[organizationAnalysis<br/><i>E1: Definición Org & Cadena Virtual</i>]
        PM[processMap<br/><i>E1: Mapa 3 Niveles & Selección Crítica</i>]
        OM[organizationalMotivations<br/><i>E1: Mapa SDLI & Motivaciones</i>]
        SIP[sipocBuilder<br/><i>E2: Matriz SIPOC</i>]
        PA[processAuditor<br/><i>E2: Auditoría 4 Ejes GUI_U2</i>]
        STM[stakeholderMatrix<br/><i>E2: Matriz Stakeholders</i>]
        FOD[fodaProcess<br/><i>E2: Matriz FODA</i>]
        CAM[cameStrategizer<br/><i>E3: Cruces CAME</i>]
        VAB[valueActionsBuilder<br/><i>E3: Acciones EERR & Filtro</i>]
        KPI[kpiDesigner<br/><i>Universal Metrics & SMART</i>]
        PIP[processImprovementPlanner<br/><i>Orquestador PDCA E1-E4 & Gantt</i>]
    end

    subgraph Soporte_Cognitivo["Gestión, Comunicación & Carrera"]
        NLM[notebooklm / notebooklmSourceNaming<br/><i>MCP, Citas & Nomenclatura</i>]
        PNL[oratoriaPnl<br/><i>Oratoria con PNL & 5Q</i>]
        HUM[humanizer<br/><i>Desintoxicación IA & Burstiness</i>]
        CVO[cvOptimizer<br/><i>CV ATS en LaTeX & Google X-Y-Z</i>]
    end

    subgraph IA_Estructurada["Inteligencia Artificial Estructurada"]
        TSA[typesafe-ai<br/><i>Primitivas IA tipadas: Choice, Score & Noul</i>]
    end

    SC --> RE
    RE --> BPMN
    RE --> UCE
    BPMN --> UCE
    BPMN <--> PA
    PA --> PW
    PW --> PIP
    PIP --> KPI
    PIP --> DS
    UCE --> DMG
    UCE --> CV
    DMG --> CV
    DMG --> GSR
    QSS --> MD
    MD --> GSR
    MD -.-> DS
    GSR --> GOF
    DMG --> ROM
    GSR --> UMLC
    DMG --> UMLC
    GSR --> DD
    DD -. design-rcu opcional .-> GSR
    GOF --> DD
    ROM --> ORM
    DD --> ORM
    DD --> API
    DD --> TEST
    ORM --> TEST
    API --> TEST
    EPC -. selecciona solo lo pedido .-> RE
    EPC -.-> UCE
    EPC -.-> QSS
    EPC -.-> GSR
    EPC -.-> DS
    GSR -.-> DS
    DMG -.-> DS
    DD -.-> DS
    HUM -. pautas anti-IA & verbos .-> CVO
    HUM -. cadencia & oratoria .-> PNL
```

`epc-flow-gen` es un orquestador para un **Ejercicio Práctico Complementario** de ASI/DSI. Lee la consigna y deriva solo los ítems solicitados a las skills especialistas; no representa una etapa de interfaz ni obliga a recorrer las ramas ilustradas.

---

## 📚 Catálogo de Skills

El repositorio cuenta actualmente con **31 skills especializadas**, distribuidas en las siguientes áreas de competencia:

Las skills migradas muestran en la etiqueta su `name` invocable en hyphen-case.
Algunos paquetes y enlaces conservan nombres o carpetas históricas en camelCase para
no romper compatibilidad; ante cualquier diferencia, prevalece el frontmatter.

### 1. Requerimientos, Viabilidad y Procesos de Negocio

| Skill | Descripción | Estándares y Técnicas Clave | Artefactos |
| :--- | :--- | :--- | :--- |
| [**system-classifier**](systemClassifier/SKILL.md) | Responde una pregunta concreta de diagnóstico, clasificación de SI, prefactibilidad o contexto PUD. | TGS, taxonomía TPS/MIS/DSS/ESS/KMS/AI, evidencia y análisis por modo. | Dictamen breve o informe formal; plantilla/referencia solo en el modo correspondiente. |
| [**requirements-extractor**](requirementsExtractor/SKILL.md) | Extrae y normaliza requisitos trazables sin diseñar la solución. | RF, RNF, reglas, restricciones, historias opcionales, fuentes y preguntas abiertas. | Registro Markdown por defecto; ERS, historias o JSON solo si se solicitan. |
| [**bpmn-extractor**](bpmnExtractor/SKILL.md) | Modela o audita procesos de negocio desde evidencia narrativa. | Perfil BPMN de ASI, ficha institucional y semántica de flujo. | Ficha y especificación del BPD; BPD gráfico solo con herramienta BPMN, o IR/Mermaid/XML no ejecutable en el perfil compatible. |

---

### 2. Análisis Funcional y Especificación del Sistema

| Skill | Descripción | Estándares y Técnicas Clave | Artefactos |
| :--- | :--- | :--- | :--- |
| [**use-case-extractor**](useCaseExtractor/SKILL.md) | Descubre el modelo o describe CU trazables; deriva las realizaciones a su skill especialista. | Objetivos de actor, relaciones CU, flujos y evidencia; Gherkin solo cuando se pide. | Inventario/diagrama o descripción institucional según el modo seleccionado. |
| [**crud-validator**](crudValidator/SKILL.md) | Contrasta entidades con CU o requisitos sin exigir CRUD completo para cada clase. | Evidencia de C/R/U/D, excepciones justificadas y nivel de cobertura. | Matriz diagnóstica y propuestas; no genera requisitos o CU automáticamente. |
| [**domain-model-gen**](domainModelGen/SKILL.md) | Genera un modelo conceptual trazable sin introducir tablas, servicios ni arquitectura. | Clases, atributos, responsabilidades y relaciones derivadas del dominio; patrones ASI solo cuando aplican. | Diagrama conceptual y registro breve de evidencia. |
| [**epc-flow-gen**](epcFlowGen/SKILL.md) | Resolución trazable de Ejercicios Prácticos Complementarios de ASI/DSI mediante selección de artefactos y skills según la consigna. | Matriz ítem → artefacto → evidencia → skill → estado, control de cobertura y no invención. | Resolución ensamblada en el formato pedido, con pendientes justificados. |

---

### 3. Calidad y Arquitectura de Software

| Skill | Descripción | Estándares y Técnicas Clave | Artefactos |
| :--- | :--- | :--- | :--- |
| [**quality-scenario-specifier**](qualityScenarioSpecifier/SKILL.md) | Convierte RNF en escenarios verificables sin inventar umbrales. | Perfil de cátedra atributo–estímulo–respuesta; seis partes y tácticas como modos condicionales. | Escenario del perfil pedido, pendientes y criterios de verificación. |
| [**microservice-decomposer**](microserviceDecomposer/SKILL.md) | Evalúa monolito modular frente a microservicios y define límites solo si se justifican. | Drivers de negocio/calidad, bounded contexts, dependencias y capacidad operativa. | Decisión arquitectónica y vistas solicitadas; “no descomponer” es válido. |

---

### 4. Diseño Orientado a Objetos, Patrones y Persistencia

| Skill | Descripción | Estándares y Técnicas Clave | Artefactos |
| :--- | :--- | :--- | :--- |
| [**grasp-sequence-realizer**](graspSequenceRealizer/SKILL.md) | Única propietaria de la realización de análisis o diseño para un escenario concreto. | BCE/GRASP aplicables, mensajes y responsabilidades trazables; GoF no es obligatorio. | RCU/DSD en una notación elegida y decisiones justificadas. |
| [**domain-design**](domainDesign/SKILL.md) | Transforma modelos de análisis y realizaciones en un DCD trazable. | Clases, responsabilidades, interfaces y relaciones de diseño justificadas; arquitectura/código son modos explícitos. | DCD por defecto; detalle técnico adicional solo si se solicita. |
| [**gof-adviser**](gofAdviser/SKILL.md) | Evalúa si una fuerza de diseño justifica un patrón y compara alternativas. | Problema, contexto, consecuencias y evidencia; “ningún patrón” es una salida válida. | Decisión o refactor solicitado con verificación. |
| [**uml-consistency**](umlConsistency/SKILL.md) | Audita dos o más artefactos existentes con evidencia y confianza. | DCD/DSD/DTE/código, normalización y fuente autoritativa. | Informe de inconsistencias; no inventa modelos ni corrige sin permiso. |
| [**relational-object-map**](relationalObjectMap/SKILL.md) | Traduce un DCD a decisiones de mapeo relacional trazables. | Identidad, atributos, asociaciones, herencia y restricciones del motor cuando exista. | Modelo lógico por defecto; esquema/DDL solo si se solicita, sin capa DAO. |

---

### 5. Modelado Visual y Diagramación Universal

| Skill | Descripción | Estándares y Técnicas Clave | Artefactos |
| :--- | :--- | :--- | :--- |
| [**diagramStudio**](diagramStudio/SKILL.md) | Motor unificado de diagramación visual y estructural (Mermaid y Draw.io nativo). Se activa **automáticamente** ante cualquier pedido textual de diagramas o inferencia del agente. | Modos `mermaid`, `drawio` y `dual`; 31 guías Mermaid, 20 manuales Draw.io y presets para Mapa de Procesos Institucional (3 niveles) y SIPOC visual. | Bloques Mermaid in-line, archivos `.drawio` XML editables y vistas sincronizadas. |

---

### 6. Experiencia de Usuario, UI y Diseño Generativo

| Skill | Descripción | Estándares y Técnicas Clave | Artefactos |
| :--- | :--- | :--- | :--- |
| [**design-ux-ui**](designUxUi/SKILL.md) | Diseño, auditoría o implementación de UX/UI con un artefacto proporcional al pedido y al sistema existente. | Flujos y estados, reutilización de componentes/tokens, accesibilidad WCAG 2.2 AA y verificación condicional. | Especificación, prototipo, código o informe según el modo; `references/` y `scripts/` se cargan solo cuando aplican. |

---

### 7. Productividad y Gestión del Conocimiento

| Skill | Descripción | Estándares y Técnicas Clave | Artefactos |
| :--- | :--- | :--- | :--- |
| [**notebooklm**](notebooklm/SKILL.md) | Integración con el servidor MCP de NotebookLM para registro de libretas compartidas, consultas fundamentadas con citas y carga de fuentes. | Protocolo MCP, grounded Q&A con citas automáticas, gestión de notebooks colaborativas. | `manual_notebooklm_mcp.md` |
| [**notebooklmSourceNaming**](notebooklmSourceNaming/SKILL.md) | Taxonomía y convención estandarizada de prefijos para ordenar, catalogar y normalizar fuentes antes de su ingesta en NotebookLM. | Prefijos estructurados (`PLN_`, `LIB_`, `NOR_`, `SLI_`, `APU_`, `GUI_`, `VID_`) para trazabilidad rigurosa en paneles de citas. | `SKILL.md` |

---

### 8. Comunicación, Redacción y Oratoria Profesional

| Skill | Descripción | Estándares y Técnicas Clave | Artefactos |
| :--- | :--- | :--- | :--- |
| [**oratoriaPnl**](pnlOratoria/SKILL.md) | Estructuración y preparación de presentaciones orales de alto impacto basadas en Programación Neurolingüística y retórica persuasiva. | Análisis de audiencia 5Q, sistemas representacionales VAK (Visual, Auditivo, Kinestésico), metaprogramas, encuadres, calibración y feedback. | `references/` (01 a 05: el presentador PNL, diseño 5Q, audiencia, voz/cuerpo, feedback) |
| [**humanizer**](humanizer/SKILL.md) | Desintoxicación y humanización de textos generados por IA; restauración de cadencia rítmica (*burstiness*), perplejidad y erradicación de clichés sintéticos. | 24 patrones de IA, matriz de intensidad (`light`, `medium`, `aggressive`), modos general/técnico/académico y detector automatizado. | Texto pulido con reporte diagnóstico, `scripts/` (detector, analizador, regresión) y catálogo de patrones. |

---

### 9. Construcción de Backend y Pruebas

| Skill | Descripción | Estándares y Técnicas Clave | Artefactos |
| :--- | :--- | :--- | :--- |
| [**orm-master**](ormMaster/SKILL.md) | Auditoría, diseño u optimización de un mapeo ORM concreto sin redefinir dominio ni esquema. | Estrategias de carga basadas en evidencia, límites transaccionales y concurrencia según el ORM/base existentes. | Diagnóstico o cambio en el stack solicitado. |
| [**api-design**](apiDesign/SKILL.md) | Diseño o auditoría de contratos HTTP/REST a partir de operaciones y requisitos aprobados. | Semántica HTTP, OpenAPI 3.x, compatibilidad y, cuando aplican, Problem Details e idempotencia. | Contrato y decisiones; implementación solo si se solicita. |
| [**backend-testing**](backendTesting/SKILL.md) | Estrategia, auditoría o implementación de pruebas downstream guiada por comportamiento y riesgo. | Niveles unitario/integración/contrato/E2E, AAA/GWT y dobles de Meszaros según el caso. | Matriz de cobertura y/o pruebas en el stack existente. |

---

### 10. Gestión y Mejora de Procesos (GMP / Ciclo PDCA)

| Skill | Descripción | Estándares y Técnicas Clave | Artefactos |
| :--- | :--- | :--- | :--- |
| [**processWorkbench**](processWorkbench/SKILL.md) | Mesa analítica y estratégica para Etapas 1 a 3 de GMP. Encuadre, selección del proceso crítico, diagnóstico y CAME. | Ponderación de 5 criterios de cátedra, Lógica Dominante del Servicio (SDL), Cadena de Valor Virtual (Rayport & Sviokla), FODA, cruces CAME, acciones EERR y filtro de restricciones operativas. | Matrices estructuradas Markdown de Etapas 1, 2 y 3 con cálculo ponderado y filtro de viabilidad. |
| [**organizationAnalysis**](organizationAnalysis/SKILL.md) | Skill atómica para la definición institucional y modelado, diagnóstico y validación de la Cadena de Valor Virtual en Etapa 1 de GMP. | Encuadre organizacional (Misión, Visión, SMART, Clientes, Propuesta de Valor), transformación de información en 5 procesos (Recopilar, Organizar, Seleccionar, Sintetizar, Distribuir), cruce bidimensional físico-virtual (La Matriz del Valor), 3 fases de madurez digital y Lógica Dominante del Servicio (SDL). | Entregable canónico persistido deterministamente en 'cadena_valor_virtual.md' y validado por CLI. |
| [**processMap**](processMap/SKILL.md) | Skill atómica para el diseño y validación del Mapa de Procesos institucional de 3 niveles y la selección multicriterio ponderada del proceso crítico en Etapa 1 de GMP. | Arquitectura de procesos en 3 niveles canónicos (Estratégicos, Clave/Operativos, Soporte), delimitación de entrada/salida de clientes, diagramación Mermaid con proceso crítico resaltado, matriz multicriterio formal de los 5 factores de cátedra ($\sum w_i = 1.00$) y justificación técnica del porqué. | Entregable canónico persistido deterministamente en 'mapa_procesos.md' y validado por CLI (con soporte de exportación a 'seleccion_proceso.md'). |
| [**organizationalMotivations**](organizationalMotivations/SKILL.md) | Skill atómica para el relevamiento de motivaciones de la organización, cruzando el negocio con los 10 macro-sectores del Mapa SDLI y 3 dimensiones bajo SDL en Etapa 1. | Mapa de Tendencias SDLI (10 macro-sectores, 3 dimensiones: Sociedad, Tecnología, Economía), Lógica Dominante del Servicio (SDL - Vargo & Lusch), co-creación de valor, necesidades del cliente e impulsores causales de rediseño. | Matriz canónica persistida deterministamente en 'motivaciones.md' y validada por CLI. |
| [**sipocBuilder**](sipocBuilder/SKILL.md) | Skill atómica para la delimitación, alcance y normalización de la matriz SIPOC con especificaciones técnicas y exportación a diagramStudio. | Matriz SIPOC de 5 dimensiones, regla canónica de 4 a 7 macroetapas ($4 \le P \le 7$), requisitos técnicos obligatorios en entradas/salidas, delimitación de fronteras y sincronización con BPMN 2.0. | Matriz canónica persistida deterministamente en 'sipoc.md' y exportable a Mermaid/Draw.io. |
| [**processAuditor**](processAuditor/SKILL.md) | Auditoría forense del proceso AS-IS en Etapa 2 sobre los 4 ejes de la guía oficial GUI_U2. | Control interno (marco COSO), segregación de funciones (SoD), ruta documental y formularios, ergonomía/factores humanos y silos informáticos/TI. | Matriz de Riesgos y Controles (RCM), matriz SoD, checklists temáticos y evidencias para FODA. |
| [**stakeholderMatrix**](stakeholderMatrix/SKILL.md) | Skill atómica para el relevamiento, clasificación y diagnóstico de partes interesadas en Etapa 2 de GMP. | Matriz canónica de triple columna (Resultados esperados, Expectativas cualitativas, Obstáculos percibidos), taxonomía interna/externa de 6 roles, matriz de Mendelow y mapa de tensiones. | Matriz canónica persistida deterministamente en 'stakeholders.md'. |
| [**fodaProcess**](fodaProcess/SKILL.md) | Skill atómica para la estructuración y validación de la Matriz FODA del proceso operativo en Etapa 2 de GMP. | Delimitación estricta de frontera interna/externa (controlabilidad), cardinalidad de 4-6 factores por cuadrante, articulación bajo los 3 Ejes de Cátedra (Estrategia, Stakeholders, Resultados) y trazabilidad forense de debilidades. | Matriz canónica persistida deterministamente en 'foda.md'. |
| [**cameStrategizer**](cameStrategizer/SKILL.md) | Skill atómica para la construcción, auditoría y validación de la Matriz CAME en Etapa 3 de GMP. | Cruces estratégicos explícitos en sus 4 cuadrantes (FO Ofensiva, FA Defensiva, DO Reorientación, DA Supervivencia), citación obligatoria de IDs de factores FODA ($F_i \times O_j$), doble formulación (enunciado táctico + acción operativa tangible) y validación determinista. | Matriz canónica persistida deterministamente en 'came.md' y validada por CLI. |
| [**valueActionsBuilder**](valueActionsBuilder/SKILL.md) | Skill atómica para la formulación del inventario de Acciones de Valor EERR y evaluación sistemática mediante el Filtro de Restricciones Operativas en Etapa 3 de GMP. | Esquema de 4 palancas EERR (Eliminar, Reducir, Incrementar, Crear), trazabilidad a cruces CAME (DO/FO/FA/DA), filtro cuádruple de viabilidad (Plazos, Costos, TI, Resistencia al Cambio) y mitigaciones. | Inventario de acciones y matriz de viabilidad determinista 'acciones_valor.md'. |
| [**bpmnExtractor**](bpmnExtractor/SKILL.md) | Extracción y modelado BPMN 2.0, validación SIPOC ↔ BPD y análisis diferencial cuantitativo. | BPMN-IR acíclico, modo `sipoc-sync` para coherencia de fronteras y modo `diff-as-is-to-be` para balance cuantitativo de mejora. | Ficha institucional, especificación BPD, matriz SIPOC-sync y reporte comparativo diff. |
| [**kpiDesigner**](kpiDesigner/SKILL.md) | Diseño y auditoría universal de sistemas de medición, métricas y tableros en 4 dominios. | Sintaxis SMART obligatoria, consistencia dimensional matemática, data provenance y validación automatizada por script. | Fichas técnicas de KPIs (O1 vs O2, DORA, SRE, HEART, Balanced Scorecard) y catálogo validado. |
| [**processImprovementPlanner**](processImprovementPlanner/SKILL.md) | Orquestador metodológico del ciclo PDCA de 4 etapas y generador de entregables finales sin Excel. | Compilación de informes maestros en Markdown, cronogramas Gantt visuales en Mermaid y matriz de trazabilidad E1->E4. | Informe Técnico Maestro (.md), diagrama de Gantt Mermaid y matriz integral de consistencia. |

---

### 11. Ingeniería de Carrera y Optimización Curricular

| Skill | Descripción | Estándares y Técnicas Clave | Artefactos |
| :--- | :--- | :--- | :--- |
| [**cvOptimizer**](cvOptimizer/SKILL.md) | Elaboración, modernización y adaptación de CVs ATS de alto impacto en LaTeX con base de datos incremental y entrega multicanal. | Fórmula Google X-Y-Z canónica, memoria viva `profile_data.json`, topología lineal ATS (1-2 páginas holgadas), modularidad LaTeX (Awesome-CV, Jake's Resume, ModernCV) y render PNG con PyMuPDF. | PDF compilado (`<Apellido Nombre>CV_<Puesto>.pdf`), `preview.png`, `profile_data.json` enriquecido y cuadros de postulación copiables (RRHH, LinkedIn, pitch). |

---

### 12. Inteligencia Artificial Estructurada (TypeSafe)

> **Instalada via:** `npx skills add typesafe-ai/skills --skill typesafe-ai` · [skills.sh/typesafe-ai/skills](https://skills.sh/typesafe-ai/skills) · [Docs](https://docs.typesafe.ai/introduction)

| Skill | Descripción | Primitivas y Modelo | Artefactos |
| :--- | :--- | :--- | :--- |
| [**typesafe-ai**](typesafeAi/SKILL.md) | Integra el modelo **Jev** de TypeSafe — el primer *System One model* — para construir software con unidades de inteligencia AI tipadas y componibles. En lugar de generar texto libre, Jev evalúa un *estado* (texto, JSON, arrays) contra preguntas tipadas y retorna respuestas estructuradas con probabilidades y confianza que el código puede consumir directamente (branch, sort, route). Usar cuando una feature necesita sentido común programable, cuando un paso LLM prompt-and-parse podría convertirse en una decisión estructurada, o para explorar qué puede hacer la IA en una aplicación. | **Primitivas:** `Choice` (selecciona una opción de una lista → `choice + probabilities + confidence`), `Score` (puntúa el estado contra una rúbrica → `score + probabilities + confidence`), `Noul` (¿es verdadera esta afirmación? → `noul` 0–1). **Modelo:** `jev-latest` (SDK default). **Casos:** routing, ranking, extracción, verificación, experiencias interactivas. | Código de integración via Python SDK, JavaScript SDK o `POST /v1/systemone`. Lee documentación viva en [docs.typesafe.ai/llms.txt](https://docs.typesafe.ai/llms.txt). |

---

### 13. Visión por Computadora y Organización Multimedia

| Skill | Descripción | Estándares y Técnicas Clave | Artefactos |
| :--- | :--- | :--- | :--- |
| [**photoOrganizer**](photoOrganizer/SKILL.md) | Orquestación integral del servidor PhotOrganizer MCP para clasificación, clustering y deduplicación masiva de colecciones fotográficas y de video. | Biometría facial InsightFace (ArcFace 512-d), detección corporal YOLOv8 + piel YCrCb, clustering DBSCAN, Pareto ABC, verificación O(1) de manifiestos y los 7 invariantes canónicos de ruteo grupal con embeddings ilimitados. | Carpetas estructuradas por persona y `_Grupales/`, `manifest.json` con cabecera `total_files`, `embeddings.npy` y reportes JSON. |

---

## 🧩 Anatomía de una Skill


Cada skill dentro del repositorio implementa una estructura estandarizada de **Documentación Dual Obligatoria**:

```
nombre-de-la-skill/
├── SKILL.md                 # Contrato operacional consumido por el LLM (YAML Frontmatter + Progressive Disclosure)
├── README.md                # Documentación técnica orientada a desarrolladores/usuarios humanos
├── references/              # [Opcional] Documentación técnica de soporte, gramáticas y marcos conceptuales
├── templates/               # [Opcional] Plantillas institucionales (Markdown, JSON Schema, XML, DDL)
├── scripts/                 # [Opcional] Scripts auxiliares ejecutables (Python, CLI de validación)
└── examples/                # [Opcional] Ejemplos reales y casos de estudio de referencia
```

### 1. Contrato Operativo del Agente (`SKILL.md`)
Define los metadatos YAML superiores para identificación y ruteo dinámico por parte del motor de agentes:

```yaml
---
name: nombre-de-la-skill
description: >-
  Producto que genera, cuándo debe activarse y el límite que evita confundirla con
  skills cercanas.
---
```

### 2. Documentación Humana (`README.md`)
Explica al desarrollador la arquitectura del paquete, prerequisitos de runtime, ejemplos de invocación por línea de comandos y el contrato exacto de entradas y salidas.

---

## 🔄 Compatibilidad de nombres y agentes

El `name` del frontmatter es el identificador canónico. Las carpetas camelCase se
conservan para instalaciones históricas y
[`skill-aliases.json`](skill-aliases.json) mantiene el mapeo completo de nombres
anteriores, incluido `design-md` → `design-ux-ui`.

Un cargador u orquestador portable debe resolver una petición así:

1. buscar coincidencia exacta con un `name` canónico;
2. si no existe, buscar el texto exacto en `skill-aliases.json` y usar su
   `canonical_name` y `skill_file`;
3. cargar un único `SKILL.md`; nunca ejecutar a la vez alias y destino;
4. si no puede leer el registro, informar el nombre no resuelto en vez de elegir por
   parecido.

Esta regla no presupone Codex, Gemini, Claude ni una API de invocación concreta. Si el
host no puede despachar skills por nombre, debe localizar el paquete disponible, leer
su `SKILL.md` y aplicar el mismo contrato. Si el paquete no está instalado, debe dejar
un handoff explícito y no improvisar instrucciones ausentes.

---

## 🛠️ Guía de Integración y Uso

### 1. Uso en Google Antigravity
Si estás utilizando Antigravity, este repositorio puede vincularse directamente como workspace de skills o copiarse en la ruta de configuración del agente:
- **Global:** `~/.gemini/antigravity/skills/`
- **Por proyecto:** Copiar o clonar las carpetas de las skills dentro de `.agent/skills/` o `.gemini/skills/` en la raíz de tu proyecto.

### 2. Uso en Claude Code, Cursor y Windsurf
- **Claude Code:** Coloca las skills deseadas dentro del directorio `.claude/skills/` o referencia el archivo `SKILL.md` dentro de tu archivo `CLAUDE.md`.
- **Cursor / Windsurf:** Añade la regla en `.cursorrules` o en los agentes de proyecto indicando la ubicación del directorio de skills y solicitando la lectura del `SKILL.md` correspondiente al abordar tareas afines.

### 3. Ejecución Directa de Scripts
Algunas skills incluyen utilidades de soporte. Leer primero el modo correspondiente y ejecutar cada script solo si coincide con el producto y el entorno:

Primero resolver un intérprete Python 3 disponible: `python3`, `python`, `py -3` o el
runtime provisto por el host. En los ejemplos, `<python-3>` representa el comando
resuelto completo. Si no existe, registrar la validación como no ejecutada; no simular
un resultado satisfactorio.

- **Validación y render de BPMN-IR:**
  ```text
  <python-3> bpmnExtractor/scripts/bpmn_ir_transformer.py bpmnExtractor/templates/bpmn_process_ir_example.json --format mermaid
  ```
- **Integridad semántica de un registro de requisitos JSON:**
  ```text
  <python-3> requirementsExtractor/scripts/validate_requirements_semantics.py path/to/registro.json
  ```
- **Auditoría y Validación de Tokens UX/UI:**
  ```powershell
  pwsh -NoProfile -File designUxUi/scripts/validate_design.ps1 -Path .\mi-proyecto\DESIGN.md
  ```
- **Servidor de Previsualización Local:**
  ```text
  <python-3> designUxUi/scripts/serve_preview.py --root path/to/frontend --port 0
  ```
- **Detección de patrones de IA y métricas de burstiness (`humanizer`):**
  ```text
  <python-3> humanizer/scripts/ai_detector.py path/to/documento.txt --json
  <python-3> humanizer/scripts/text_analyzer.py original.txt revisado.txt --compare
  ```
- **Compilación modular de CV en LaTeX y render PNG (`cvOptimizer`):**
  ```text
  <python-3> cvOptimizer/scripts/build_cv.py --project-dir cv_Analista_IT/ --candidate-name "Nombre Candidato" --target-role "Analista IT"
  <python-3> cvOptimizer/scripts/update_profile.py --input-profile profile_data.json
  ```

Sustituí las rutas de ejemplo por artefactos existentes. El validador de diseño puede
requerir que `npx` obtenga `@google/design.md`; el servidor exige un directorio que
contenga `index.html` y elige un puerto libre con `--port 0`.

---

## 🏛️ Estándares y Fundamentos Académicos

Las directrices metodológicas implementadas en este repositorio se basan en literatura y normas de referencia internacional en la Ingeniería de Software:

- **Ingeniería de Requerimientos:** ISO/IEC/IEEE 29148:2018, IEEE Std 830, Guía INCOSE para la Elicitación de Requisitos.
- **Modelado y Especificación:** Alistair Cockburn (*Writing Effective Use Cases*), Ivar Jacobson (*Object-Oriented Software Engineering - BCE*).
- **Modelado de Procesos:** BPMN 2.0 (Object Management Group - OMG).
- **Diseño Orientado a Objetos:** Craig Larman (*Applying UML and Patterns - GRASP*), Erich Gamma et al. (*Design Patterns - GoF*).
- **Arquitectura de Software y Backend:** Bass, Clements & Kazman (*Software Architecture in Practice*), Mark Richards & Neal Ford (*Fundamentals of Software Architecture*), Eric Evans (*Domain-Driven Design*), Simon Brown (*The C4 Model for Visualising Software Architecture*), Robert C. Martin (*Clean Architecture*), Alistair Cockburn (*Hexagonal Architecture / Ports & Adapters*).
- **Persistencia y ORM:** Martin Fowler (*Patterns of Enterprise Application Architecture - Unit of Work, Identity Map*), Vlad Mihalcea (*High-Performance Java Persistence*).
- **Diseño de APIs Web:** Leonard Richardson (*REST Maturity Model*), RFC 7807 / RFC 9457 (*Problem Details for HTTP APIs*), OpenAPI Specification 3.x.
- **Artesanía de Testing Automatizado:** Gerard Meszaros (*xUnit Test Patterns - Test Doubles Taxonomy*), Kent Beck (*Test-Driven Development by Example*).
- **Calidad de Software:** ISO/IEC 25010 / 25000 (SQuaRE - System and Software Quality Requirements and Evaluation).
- **Diseño de Interfaz y Accesibilidad:** Jakob Nielsen (10 Heurísticas de Usabilidad), W3C WCAG 2.2 Nivel AA y sistemas de tokens cuando el producto los requiere.
- **Comunicación Persuasiva:** Programación Neurolingüística (PNL) aplicada a oratoria técnica.
- **Desintoxicación y Refinamiento de Salidas de IA:** Estilometría y lingüística computacional aplicada a modelos de lenguaje (cadencia rítmica, perplejidad, variación métrica / *burstiness*, riqueza léxica TTR), directivas de claridad técnica y manuales de estilo.
- **Ingeniería Curricular y Evaluación de Talento:** Metodología Google X-Y-Z de impacto cuantificado (*Laszlo Bock - Work Rules!*), estándares de legibilidad y topologías de parseo para sistemas de seguimiento de candidatos (ATS Parsing Algorithms - Workday, Greenhouse, Taleo, Lever).

---

## 🤝 Buenas Prácticas de Contribución

1. **Idempotencia y Determinismo:** Al proponer cambios o nuevas skills, prioriza artefactos reproducibles (plantillas, esquemas y checklists verificables).
2. **Documentación Complementaria en `references/`:** No sobrecargues `SKILL.md` con tablas extensas si pueden residir en archivos dedicados dentro de `references/`.
3. **Validación Sintáctica:** Verifica que los bloques Mermaid, scripts Python y JSON Schemas sean formalmente válidos antes de hacer commit.
4. **Respeto a los Estándares:** Conserva la nomenclatura y las reglas de trazabilidad definidas para los artefactos de análisis y diseño.

---

<div align="center">
  <sub>Desarrollado para potenciar el flujo de trabajo de agentes inteligentes y desarrolladores de software.</sub>
</div>

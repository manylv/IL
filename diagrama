graph TD
    %% Estilos de Nodos
    classDef problem fill:#f96,stroke:#333,stroke-width:2px;
    classDef jtp fill:#bef,stroke:#333,stroke-width:1px,rx:10,ry:10;
    classDef arco fill:#fed,stroke:#333,stroke-width:1px,rx:10,ry:10;
    classDef decision fill:#ff9,stroke:#333,stroke-width:2px;
    classDef success fill:#ccf,stroke:#333,stroke-width:1px,stroke-dasharray: 5 5;
    classDef technical fill:#eee,stroke:#333,stroke-width:1px;

    Start((Inicio)) --> Analisis
    
    subgraph Analisis[FASE 1: Análisis del Problema]
        direction TB
        E[Estado Actual: Incompatibilidad] --> P1
        E --> P2
        
        P1(JT Plastic: <br>Usa Condiciones FVA1)
        P1 -->|Ventaja| V1{Vínculo Directo<br>OC-Costo}:::success
        
        P2(Arco: <br>Usa OCs NBTM Separadas)
        P2 -->|Ventaja| V2{Mantiene 20+<br>Autorizaciones}:::success
        
        P1 -.->|Requiere| Unif:::problem
        P2 -.->|Requiere| Unif:::problem
        
        Unif{Sin Vínculo<br>Sistémico}
    end

    Analisis --> Solucion

    subgraph Solucion[FASE 2: Solución Propuesta]
        direction TB
        Unif -->|Decisión| Standard(Adoptar Estándar FVA1):::decision
        Standard --> Finanzas[Finanzas Arco: Abierto al Cambio]:::jtp
        
        Standard --> Workaround(Evaluar Workaround para Arco):::arco
        Workaround --> Link(Vincular OCs NBTM<br>vía Campo Referencia):::technical
        Link --> Manual(Ingreso Manual: <br>HES de OC Producto):::arco
    end

    Solucion --> Pruebas

    subgraph Pruebas[FASE 3: Próximos Pasos & Validación]
        direction TB
        Task_A1(Alonso: Documentar<br>Proceso JT Plastic):::jtp
        Task_C1(Cristian: Validar API<br>con OCs NB & NBTM):::technical
        Link -->|Prueba Piloto| Test_Alonso_Cristian(Alonso & Cristian: <br>Test de Trazabilidad):::decision
        
        Task_C1 --> Test_Alonso_Cristian
        
        Test_Alonso_Cristian -->|Éxito| PropuestaZahel(Proponer Solución<br>Validada a Zahel):::jtp
        
        Task_A1 --> Sync(Compartir Documentación<br>con Miriam)
        Sync --> PropuestaZahel
    end

    %% Definición de clases específicas para estilos visuales
    class P1,V1 jtp;
    class P2,V2 arco;
    class Unif problem;
    class Standard decision;
    class Link,Task_C1 technical;
    class Workaround,Manual arco;
    class Test_Alonso_Cristian decision;
    class PropuestaZahel success;

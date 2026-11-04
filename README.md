# Gestión de la Comunidad Institucional TEC

Este proyecto consiste en el diseño e implementación de un ecosistema digital automatizado en **Java** para la administración centralizada de los miembros del Tecnológico de Costa Rica (Estudiantes, Funcionarios Propietarios y Funcionarios Interinos). La aplicación resuelve flujos operacionales complejos bajo el paradigma de Programación Orientada a Objetos (POO), integrando capas de persistencia física en disco, control preventivo de errores mediante excepciones y una interfaz gráfica de usuario (GUI) responsiva.

---

## Arquitectura del Sistema y Patrones de Diseño

El sistema se estructura bajo un enfoque modular guiado por una jerarquía de herencia de tres niveles y abstracciones estrictas:
*   **Modelo de Herencia Cohesivo:** Basado en la clase abstracta raíz `Persona` y la clase abstracta intermedia `Funcionario`, especializándose en los tipos concretos `Estudiante`, `Interino` y `Propietario`.
*   **Polimorfismo:** Implementación personalizada del método conceptual `vacacionesPagadas()` según el marco normativo de cada rol.
*   **Interfaces Contractuales (Decisiones de Diseño):**
    *   `ITransaccional`: Regula las operaciones de manipulación lógica (`registrar`, `editar`, `localizar`).
    *   `IAlmacenable`: Define los métodos de serialización física (`guardar`, `cargar`).

---

## Reglas de Negocio Incorporadas

1.  **Restricción de Contratos (Interinos):** Validación lógica para asegurar que la duración de los contratos no exceda los 6 meses.
2.  **Límites de Jornada (Propietarios):** Control riguroso de la carga porcentual laboral, acotada estrictamente entre el 25% (10 horas) y el 150% (60 horas) semanales.
3.  **Persistencia Transparente:** Carga automática del repositorio de objetos al iniciar la aplicación y guardado preventivo al cerrar la GUI para evitar la pérdida de datos.

---

## Componentes del Entorno Gráfico (Java Swing)

La interfaz gráfica opera directamente sobre la clase controladora `ComunidadTEC` y cuenta con las siguientes capacidades integradas:
*   **Formularios Dinámicos:** Activación y ocultamiento adaptativo de campos en función del tipo de miembro seleccionado (Manejo de fechas con bibliotecas `.jar` externas para contratos).
*   **Operaciones CRUD:** Vinculación directa de botones de registro con refrescamiento inmediato en componentes `JTable`.
*   **Laboratorio de Reportes Avanzados:**
    *   *Filtro Salarial:* Selección por rangos mediante el uso interactivo de componentes `JSlider`.
    *   *Desglose de Comunidad:* Contabilidad y auditoría exacta de los miembros registrados por categoría.
    *   *Cálculo de Nómina de Vacaciones:* Procesamiento algorítmico automatizado del beneficio para el periodo legal 2026 y exportación a archivos planos legibles (`ReporteVacaciones.txt`) con control interno de excepciones E/S.

---

## Tecnologías y Entorno
*   **Lenguaje:** Java 8 o superior.
*   **IDE:** NetBeans / VS Code.
*   **Framework GUI:** Java Swing (Componentes renombrados bajo convención técnica, ej: `tbComunidad`, `txtSalario`).

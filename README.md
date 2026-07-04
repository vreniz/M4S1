# Diseño Conceptual y Lógico de Base de Datos

## Hospital Vida Sana — Historia de Usuario M4S1

### Descripción
Diseño de una base de datos relacional para el Hospital "Vida Sana", que permite gestionar **pacientes, médicos, citas y diagnósticos** de forma consistente y sin duplicidades. El diseño abarca el modelo conceptual (DER) y su conversión al modelo relacional, normalizado hasta la **tercera forma normal (3FN)**.

Este entregable corresponde únicamente al diseño. **No incluye** scripts SQL de creación, carga de datos ni interfaz gráfica.

### Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `DER.pdf` | Diagrama Entidad–Relación (modelo conceptual) |
| `ModeloRelacional.pdf` | Modelo relacional con tipos de datos (modelo lógico) |

### Entidades del modelo
- **ESPECIALIDAD** — catálogo de especialidades médicas
- **MEDICO** — datos de los médicos (FK a especialidad)
- **PACIENTE** — datos de los pacientes
- **CITA** — agendamiento entre paciente y médico (FK a ambos)
- **DIAGNOSTICO** — resultado de una cita (relación 1:1 con CITA)

### Convenciones del diagrama
- 🔵 **Azul:** claves primarias (PK)
- 🟡 **Amarillo:** claves foráneas (FK)
- **Rombos:** relaciones entre entidades
- **U:** atributo UNIQUE

### Normalización aplicada (3FN)
- **1FN:** todos los atributos son atómicos, sin grupos repetitivos.
- **2FN:** todos los atributos dependen completamente de la clave primaria.
- **3FN:** se eliminaron dependencias transitivas (ej.: `nombre_esp` se extrajo a la tabla ESPECIALIDAD en lugar de repetirse en cada médico).

### Correspondencia DER ↔ Modelo Relacional
Ambos modelos reflejan exactamente las mismas estructuras y relaciones (correspondencia 1:1), garantizando la coherencia entre el diseño conceptual y el lógico.

---
*Elaborado como parte del entrenamiento en modelado de bases de datos — M4S1.*

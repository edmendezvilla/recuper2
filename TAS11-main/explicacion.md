1.-Crear script DDL

Rutine: Almacena información sobre las rutinas, incluyendo descripción, advertencias y sexo objetivo.

exercise: Contiene detalles sobre los ejercicios y un URL a un video demostrativo.
Routine_exercise: Conecta las rutinas con los ejercicios, especificando series y repeticiones. 

Incluye claves foráneas para routine_id y exercise_id para relacionar las tablas Rutine y exercise.

Students: Información de estudiantes
Courses: Información de cursos
Enrollments: Inscripciones de estudiantes en cursos

2.-Poblar con datos

Rutine: Se agregan dos rutinas, una para principiantes y otra avanzada.

exercise: Se agregan dos ejercicios, "Push-ups" y "Squats", con enlaces a videos.

Routine_exercise: Asocia ejercicios con rutinas, especificando series y repeticiones.

Cada tabla recibe valores específicos para sus campos definidos.

3.-Crear una vista con las 3 tabla

La vista RoutineDetails combina datos de las tablas Rutine, Routine_exercise y exercise. Muestra detalles de las rutinas, ejercicios asociados, series, y repeticiones
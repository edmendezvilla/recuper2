
### 1. Crear script DDL
- Sentencia:
```
CREATE TABLE Rutine (
    id INT PRIMARY KEY,
    description TEXT,
    disclaimer TEXT,
    sex VARCHAR(10)
);

CREATE TABLE exercise (
    id INT PRIMARY KEY,
    detail TEXT,
    video_url TEXT
);

CREATE TABLE Routine_exercise (
    id INT PRIMARY KEY,
    series INT,
    repetitions INT,
    routine_id INT,
    exercise_id INT,
    FOREIGN KEY (routine_id) REFERENCES Rutine(id),
    FOREIGN KEY (exercise_id) REFERENCES exercise(id)
);
```

- Captura

<img src="![alt text](image.png)" width="500"/>

### 2. Poblar con datos
---
- Sentencia:
```

INSERT INTO Rutine (id, description, disclaimer, sex)
VALUES
(1, 'Beginner Routine', 'Consult a physician before starting.', 'unisex'),
(2, 'Advanced Routine', 'Do not attempt if injured.', 'unisex');


INSERT INTO exercise (id, detail, video_url)
VALUES
(1, 'Push-ups', 'http://example.com/pushups'),
(2, 'Squats', 'http://example.com/squats');


INSERT INTO Routine_exercise (id, series, repetitions, routine_id, exercise_id)
VALUES
(1, 3, 15, 1, 1),
(2, 4, 20, 2, 2);

```

- Captura

<img src="![alt text](image-1.png)" alt="drawing0" width="500"/>

### 3. Crear una vista con las 3 tablas
---
- Sentencia:
```
CREATE VIEW RoutineDetails AS
SELECT 
    r.id AS RoutineID,
    r.description,
    r.disclaimer,
    r.sex,
    e.id AS ExerciseID,
    e.detail,
    e.video_url,
    re.series,
    re.repetitions
FROM
    Rutine r
JOIN
    Routine_exercise re ON r.id = re.routine_id
JOIN
    exercise e ON re.exercise_id = e.id;

```

- Captura

<img src="![alt text](image.png)" alt="drawing0" width="500"/>

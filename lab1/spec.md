
# Сутності та атрибути

- StrategAI: id (PK), name, faction_color
- Squad: id (PK), name
- Mob: id (PK), squad_id (FK), health, damage, position
- Target: id (PK), is_destroyed, position
- Task: id (PK), path, status

# Зв'язки

StrategAI може створювати 0...* Squad, Squad має лише 1 StrategAI.
StrategAI може створювати 0...* Target, Target має лише 1 StrategAI.
Mob належить лише 1 StrategAI, StrategAI може мати 0...* Mob.
Squad може мати 0...* Mob, Mob належить лише 1 Squad. Squad може мати 0...* Target, Target може належати 0...* Squad. Squad має 0...* Task, Task належить лише 1 Squad. Task може бути призначено 0...* Mob, Mob може виконувати лише 1 Task.
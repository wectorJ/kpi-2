
# Сутності та атрибути

- Operator: id (PK), is_player, fraction_color
- Squad: id (PK), operator_id (FK), name
- Mob: id (PK), squad_id (FK), operator_id (FK), health, damage, pos_x, pos_y
- Target: id (PK), is_destroyed, pos_x, pos_y
- Task: id (PK), path, status

# Зв'язки

Operator може мати 0...* Squad, кожен Squad належить рівно 1 Operator.
Operator може бути пов'язаний із 0...* Target, кожен Target може бути пов'язаний із 0...* Operator.
Operator може мати 0...* Mob, кожен Mob належить рівно 1 Operator.
Squad може мати 0...* Mob, кожен Mob може належати 0...1 Squad.
Squad може бути пов'язаний із 0...* Target, кожен Target може бути пов'язаний із 0...* Squad.
Squad має 0...* Task, кожен Task належить рівно 1 Squad.
Task може бути призначено 0...* Mob, кожен Mob може виконувати 0...1 Task.

# Сутності та атрибути

- Operator: int id (PK), bool is_player, string fraction_color
- Squad: int id (PK), int operator_id (FK), string name
- Mob: int id (PK), int squad_id (FK), int operator_id (FK), int health, int damage, float pos_x, float pos_y
- Target: int id (PK), bool is_destroyed, float pos_x, float pos_y
- Task: int id (PK), string path, status (JSON)

# Зв'язки

Operator може мати 0...* Squad, кожен Squad належить рівно 1 Operator.
Operator може бути пов'язаний із 0...* Target, кожен Target може бути пов'язаний із 0...* Operator.
Operator може мати 0...* Mob, кожен Mob належить рівно 1 Operator.
Squad може мати 0...* Mob, кожен Mob може належати 0...1 Squad.
Squad може бути пов'язаний із 0...* Target, кожен Target може бути пов'язаний із 0...* Squad.
Squad має 0...* Task, кожен Task належить рівно 1 Squad.
Task може бути призначено 0...* Mob, кожен Mob може виконувати 0...1 Task.
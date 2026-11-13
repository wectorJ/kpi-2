# language: en

Feature: UC-04 Розформувати Squad

  @SC-10 @UC-04
  Scenario: Розформування Squad з Mob
    Given Player P1 володіє Squad S1, до якого входять Mob M1 і M2
    And кожен із цих Mob має особистий Task
    When P1 надсилає команду розформувати Squad S1
    Then S1 видалено зі списку Squad гравця P1
    And M1 і M2 залишаються у власності P1
    And M1 і M2 більше не належать до жодного Squad і не мають особистих Task

  @SC-11 @UC-04
  Scenario: Видалення порожнього Squad
    Given Player P1 володіє порожнім Squad S1
    When P1 надсилає команду розформувати Squad S1
    Then S1 видалено зі списку Squad гравця P1

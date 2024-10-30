### OB_06_upravlenie_proektami_Bitva_Geroev
### [Перейти к файлу игры](battle_of_heroes.py)
# Инструкция по использованию игры "Битва героев"

Добро пожаловать в "Битву героев"! В этой игре вы сможете сразиться с компьютером, управляя своим собственным героем. Ниже приведены инструкции о том, как запустить игру и наслаждаться игровым процессом.

## Системные требования

- Python 3.x (установите с [официального сайта Python](https://www.python.org/downloads/))

## Как запустить игру

1. **Скопируйте код**: Скопируйте приведённый ниже код в текстовый редактор или IDE (например, PyCharm или VSCode).

    ```python
    class Hero:
        def __init__(self, name, health=100, attack_power=20):
            self.name = name
            self.health = health
            self.attack_power = attack_power

        def attack(self, other):
            other.health -= self.attack_power
            print(f"{self.name} атакует {other.name} на {self.attack_power} урона!")

        def is_alive(self):
            return self.health > 0


    class Game:
        def __init__(self, player_name):
            self.player = Hero(player_name)
            self.computer = Hero("Компьютер")

        def start(self):
            print("Игра началась!")
            while self.player.is_alive() and self.computer.is_alive():
                # Ход игрока
                self.player.attack(self.computer)
                if self.computer.is_alive():
                    # Ход компьютера
                    self.computer.attack(self.player)

                print(f"{self.player.name} здоровье: {self.player.health}")
                print(f"{self.computer.name} здоровье: {self.computer.health}")
                print("-" * 30)

            if self.player.is_alive():
                print(f"{self.player.name} победил!")
            else:
                print(f"{self.computer.name} победил!")


    def main():
        player_name = input("Введите имя вашего героя: ")
        game = Game(player_name)
        game.start()


    if __name__ == "__main__":
        main()
    ```

2. **Сохраните файл**: Сохраните файл с расширением `.py`, например, `battle_of_heroes.py`.

3. **Откройте терминал или командную строку**: 
    - На Windows: нажмите `Win + R`, введите `cmd` и нажмите Enter.
    - На macOS: откройте "Терминал" из папки "Программы".

4. **Перейдите в каталог, где сохранен файл**: Используйте команду `cd`, чтобы перейти в нужн

ый каталог. Например:
   ```bash
   cd путь/к/каталогу
   ```

5. **Запустите игру**: Введите следующую команду и нажмите Enter:
   ```bash
   python battle_of_heroes.py
   ```

## Игровой процесс

1. **Введите имя вашего героя**: После запуска игры вам будет предложено ввести имя вашего героя. Введите имя и нажмите Enter.

2. **Сражение**: Игра начнётся, и ваш герой будет сражаться с компьютером. Каждый ход ваш герой будет атаковать компьютера, а затем компьютер будет атаковать вас.

3. **Следите за здоровьем**: Здоровье вашего героя и компьютера будет отображаться после каждого хода. Игра закончится, когда один из героев потеряет все здоровье.

4. **Определение победителя**: В конце игры вы увидите сообщение о том, кто победил — вы или компьютер!

## Примечания

- Убедитесь, что у вас установлен Python 3.x.
- Если у вас возникнут проблемы с запуском игры, проверьте, правильно ли установлен Python и добавлен ли он в переменные окружения.

Спасибо за игру! Удачи вам в сражениях!

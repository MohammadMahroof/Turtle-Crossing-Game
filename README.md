# 🐢 Turtle Crossing Game

A simple **road-crossing arcade game** built using **Python Turtle** and **Object-Oriented Programming (OOP)**.

The player controls a turtle and tries to cross the road without getting hit by moving cars. Each successful crossing increases the level and makes the cars faster.

> 📚 **This project was built as part of my Python learning journey to practice Object-Oriented Programming, game logic, and working with the Turtle graphics library.**

---

## 📌 Project Overview

**Turtle Crossing** is a small interactive game inspired by the classic road-crossing concept.

The player starts at the bottom of the screen and moves the turtle upward using the **Up Arrow** key. Cars continuously appear and move from right to left.

The goal is to reach the finish line without colliding with a car.

When the player successfully crosses the road:

```text
Reach Finish Line
       ↓
Return to Start
       ↓
Increase Level
       ↓
Increase Car Speed
       ↓
Continue Playing
```

If the player hits a car:

```text
Car Collision
      ↓
GAME OVER
```

---

## 🎮 Game Features

* 🐢 Player-controlled turtle
* ⌨️ Keyboard controls
* 🚗 Randomly generated cars
* 🎨 Random car colors
* ↔️ Cars moving across the screen
* 💥 Collision detection
* 🏁 Finish-line detection
* 📈 Level progression
* ⚡ Increasing car speed
* 📊 Level scoreboard
* 💀 Game Over message
* 🧩 Object-Oriented design

---

## 🕹️ Controls

| Key         | Action                 |
| ----------- | ---------------------- |
| ⬆️ Up Arrow | Move the turtle upward |

The player must carefully move upward and avoid the cars.

---

## 🛠️ Technologies Used

* **Python**
* **Turtle Graphics**
* **Object-Oriented Programming (OOP)**
* **Random Module**
* **VS Code / PyCharm**
* **Git & GitHub**

---

## 📂 Project Structure

```text
Turtle-Crossing/
│
├── main.py
├── player.py
├── car_manager.py
├── scoreboard.py
└── README.md
```

### `main.py`

The main controller of the game.

It is responsible for:

* Creating the game screen
* Creating the game objects
* Setting keyboard controls
* Running the game loop
* Creating and moving cars
* Checking collisions
* Checking the finish line
* Increasing the level
* Ending the game

**In simple terms:** `main.py` connects everything together.

---

### `player.py`

Contains the `Player` class.

It is responsible for everything related to the player turtle:

* Creating the player
* Setting the starting position
* Moving upward
* Returning to the starting position
* Checking the finish line

Important methods:

```text
go_up()
    → Moves the player upward

go_to_start()
    → Returns the player to the starting position

is_at_finish_line()
    → Checks whether the player reached the finish line
```

---

### `car_manager.py`

Contains the `CarManager` class.

It manages all the cars in the game.

It is responsible for:

* Creating cars
* Assigning random colors
* Assigning random positions
* Storing cars in a list
* Moving cars
* Managing car speed
* Increasing speed after each level

Important attributes:

```text
all_cars
    → Stores all car objects

car_speed
    → Stores the current car speed
```

Important methods:

```text
create_car()
    → Creates a new car

move_cars()
    → Moves all cars to the left

level_up()
    → Increases the car speed
```

---

### `scoreboard.py`

Contains the `Scoreboard` class.

It manages the information displayed to the player.

It is responsible for:

* Displaying the current level
* Increasing the level
* Updating the scoreboard
* Displaying `GAME OVER`

Important methods:

```text
update_scoreboard()
    → Updates the level display

increase_level()
    → Increases the level by 1

game_over()
    → Displays GAME OVER
```

---

# 🧠 How the Game Works

## 1. The Player

When the game starts, a turtle is placed near the bottom of the screen.

The player uses the **Up Arrow** key to move forward.

```text
Press Up Arrow
      ↓
Player moves upward
```

The movement distance is controlled using a constant:

```python
MOVE_DISTANCE = 10
```

---

## 2. Cars

Cars are created randomly during the game.

Each car receives:

* A random color
* A random starting position
* A horizontal shape

All cars are stored in a list:

```python
self.all_cars = []
```

This allows `CarManager` to keep track of and control multiple cars.

---

## 3. Car Movement

Cars move from **right to left** across the screen.

```text
🚗  ←  ←  ←  ←
```

The current speed is stored in:

```python
self.car_speed
```

This allows the game to increase the difficulty as the player progresses.

---

## 4. Collision Detection

The game checks the distance between the player and every car.

```text
Player
   ↓
Check distance
   ↓
Distance < 20?
   ↓
Collision
   ↓
GAME OVER
```

If the player gets too close to a car, the game ends.

---

## 5. Finish Line

The player has to reach the finish line at the top of the screen.

The method:

```text
is_at_finish_line()
```

checks whether the player has reached it.

If the player reaches the finish line:

```text
Finish Line
     ↓
Player returns to start
     ↓
Level increases
     ↓
Car speed increases
     ↓
Game continues
```

---

## 6. Level Progression

Every successful crossing increases the level.

The starting car speed is:

```python
STARTING_MOVE_DISTANCE = 5
```

The speed increases by:

```python
MOVE_INCREMENT = 10
```

Example:

```text
Level 1 → Speed 5
Level 2 → Speed 15
Level 3 → Speed 25
Level 4 → Speed 35
...
```

This makes the game progressively more challenging.

---

# 🔄 Main Game Loop

The game continuously runs while:

```python
while game_is_on:
```

The basic flow is:

```text
Start Game
    ↓
Create Cars
    ↓
Move Cars
    ↓
Player Moves
    ↓
Check Collision
    ↓
Check Finish Line
    ↓
Level Up
    ↓
Increase Car Speed
    ↓
Repeat
```

The game stops when the player collides with a car.

---

# 🧩 Object-Oriented Design

The project is divided into three main classes:

```text
Player
   ↓
Controls the player

CarManager
   ↓
Creates and manages cars

Scoreboard
   ↓
Manages level and GAME OVER
```

`main.py` connects these classes and controls the overall game.

This separation makes the code easier to:

* Understand
* Maintain
* Debug
* Modify
* Extend

---

# 🏗️ Class Relationship

```text
                    Turtle Crossing
                          │
             ┌────────────┼────────────┐
             │            │            │
           Player      CarManager   Scoreboard
             │            │            │
          Movement      Cars         Level
          Controls      Creation    Game Over
          Finish        Movement
                        Speed
```

Each class has a specific responsibility instead of putting all the game logic into one file.

---

# 🐍 Python Concepts Practiced

This project helped me practice:

* Variables
* Lists
* Functions
* Classes and Objects
* Constructors (`__init__`)
* Instance attributes
* Instance methods
* Inheritance
* `for` loops
* `while` loops
* Conditional statements
* Random numbers
* Turtle graphics
* Keyboard event handling
* Collision detection
* Object interaction
* Game loops
* Modular programming
* Object-Oriented Programming

---

# ▶️ How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/MohammadMahroof/Turtle-Crossing-Game.git
```

### 2. Open the Project

Open the project folder in **VS Code**, **PyCharm**, or another Python IDE.

### 3. Run the Game

```bash
python main.py
```

The Turtle Crossing game window will open.

---

# 📋 Requirements

The project uses Python's built-in modules:

* `turtle`
* `random`
* `time`

No external Python packages are required.

Check your Python installation:

```bash
python --version
```

---

# 🚀 Future Improvements

Possible improvements for future versions:

* 🏆 Add a high-score system
* 💾 Save the highest level locally
* 🔄 Add a Restart Game option
* ⏸️ Add Pause and Resume functionality
* 🔊 Add sound effects
* 🎵 Add background music
* ❤️ Add multiple lives
* 🚗 Improve car spawning and traffic patterns
* 🎨 Add different player and car designs
* 🎚️ Add different difficulty levels
* 🖥️ Improve the game interface
* 🎯 Add a Start Game screen
* 📊 Add additional game statistics
* 🧹 Remove cars that leave the screen to improve performance

---

# 🎯 Learning Goal

The main goal of this project was to strengthen my **Python programming and Object-Oriented Programming skills** by building a complete interactive game.

Through this project, I practiced how to take individual programming concepts and combine them into a working application:

```text
Python Basics
      ↓
OOP
      ↓
Classes & Objects
      ↓
Turtle Graphics
      ↓
Keyboard Events
      ↓
Game Loop
      ↓
Collision Detection
      ↓
Game State
      ↓
Level Progression
```

This project is part of my **Python learning journey**, where I am building practical projects to improve my programming, problem-solving, and software development skills.

---

# 📌 Project Status

**Completed** ✅

### Currently Implemented

* Player movement
* Random car generation
* Random car colors
* Car movement
* Collision detection
* Finish-line detection
* Level progression
* Increasing car speed
* Level scoreboard
* Game Over message

---

# 👨‍💻 Author

**Mohammad Mahroof**

Python Developer | Software Developer

---

# 📝 Quick Repository Reminder

When I come back to this project later, I can quickly remember:

```text
main.py
    → Controls the overall game

player.py
    → Controls the turtle

car_manager.py
    → Creates, manages, moves, and speeds up cars

scoreboard.py
    → Displays the level and GAME OVER
```

### Core Game Logic

```text
MOVE
  ↓
AVOID CARS
  ↓
REACH FINISH LINE
  ↓
LEVEL UP
  ↓
CARS GET FASTER
  ↓
REPEAT
```

### In One Sentence

> **Cross the road without getting hit → level up → cars get faster → repeat.**

---

## 📚 Part of My Python Learning Journey

This project represents one step in my journey of learning Python through **hands-on projects** rather than only studying theory.

The focus was not just on making the game work, but also on understanding **how to structure a program, use OOP, separate responsibilities, and turn individual concepts into a complete application**.

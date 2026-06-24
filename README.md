# IT-140
Intro to Scripting: SNHU 2024

IT 140 introduces Python scripting through a series of progressively complex programs. The course begins with variables, input/output, and conditionals, advances through loops and pseudocode design, and culminates in a complete text-based adventure game built with Python dictionaries, functions, and control flow logic.

Project Summaries

Module 2 — Name and Birth Year Calculator (mod2.3.py)

The first Python program written in the course. Prompts the user for their name and age, then calculates and prints the year they were born.

name = input('Enter your name: ')
age = int(input('Enter your age: '))
print('Hello', name, "you were born in", 2024 - age)

Concepts practiced: input(), type conversion with int(), string formatting, arithmetic expressions
Reflection: This module marked the first hands-on experience with PyCharm. Key observations included PyCharm's autocomplete feature for reducing spelling errors, automatic bracket and quotation closing, and the built-in debugger for catching issues before submission.

Module 3 — Payroll Overtime Calculator (Pseudocode)

Designed pseudocode for a payroll program that calculates weekly pay based on hours worked.

Logic:
Employees working 40 hours or fewer earn $20/hour (standard rate)
Employees working more than 40 hours earn $20/hour for the first 40, plus $30/hour for every hour over 40 (overtime rate)
Output is either a standard "Weekly Paycheck" or an "Overtime Paycheck" message
Concepts practiced: Conditional logic (IF/ELSE), variable declaration, arithmetic expressions, pseudocode structure

Module 4 — High/Low Number Guessing Game (Pseudocode, mod_4-3.docx)

Designed pseudocode for an interactive number guessing game.

Features:
Prompts the player for their name and welcomes them by name
Accepts a lower and upper bound from the player; validates that the lower bound is less than the upper bound, re-prompting if invalid
Generates a random number within the range using random.randint()
Loops until the player guesses correctly, providing "too high" or "too low" feedback after each wrong guess
Concepts practiced: while loops, input validation, random module, nested conditionals, user-facing output formatting

Module 6 Milestone — Room Navigation (ModuleSixMilestone.py)

An early milestone toward the final text-based game. Demonstrates the core room-linking pattern using a Python dictionary where each room key maps to a dictionary of available directions and their destination rooms.

rooms = {
    'Great Hall': {'South': 'Bedroom'},
    'Bedroom': {'North': 'Great Hall', 'East': 'Cellar'},
    'Cellar': {'West': 'Bedroom'}
}

The milestone explores the while True game loop pattern, directional input handling, and win/exit conditions.
Concepts practiced: Nested dictionaries, while loops, if/elif/else branching, user input

Final Project — Dancing with Anna (TextBasedGame.py)

A complete text-based adventure game set in a hotel. The player must collect six items spread across the hotel's rooms and reach the Ballroom to confront and capture the villain — Anna Delvey — before the police arrive.

Game Map

                    [Theater] — [Ballroom]*
                        |
[Pool] — [Library] — [Dining Room]
              |
           [Foyer] — [Bedroom]

* = Villain room (win condition)

How to Play:

Type m then a direction (North, South, East, West) to move between rooms
Type pick up to collect the item in the current room
Type battle in the Ballroom to begin the final dance battle against Anna
Type E to escape from a fight back to the Theater
Type HELP to re-read the rules
Type STOP to end the game
Win / Lose Conditions

Win: Collect all 6 items, reach the Ballroom, and defeat Anna in the dance battle (Anna's health reaches 0 while yours is still above 0). Prize: $500,000 bounty.
Lose: Your health drops to 0 during the fight, or Anna escapes.
Key Design Elements

game_rooms dictionary — links each room to its navigable directions and available item
item_pow dictionary — assigns a damage value to each collectible item for use in the final battle
print_master(event) function — centralizes all game text in a single dictionary of messages, keeping display logic separate from game logic
dance_bag list — tracks collected inventory throughout the game
fight_villain() function — manages the turn-based battle loop against Anna
Concepts practiced: Nested dictionaries, functions, lists, while loops, if/elif/else control flow, random.randint(), string formatting, separation of game logic and display logic.

Reflection:

The progression from mod2.3.py — a three-line script — to the full text-based adventure game captures how quickly Python fundamentals compound. By Module 2, the challenge was simply getting input() and int() to work together correctly. By the final project, the challenge was coordinating multiple functions, a persistent inventory list, nested dictionaries for game state, and a turn-based combat loop — all while keeping the code organized enough to debug. The most transferable skill the course built was thinking in data structures before writing code. The entire text-based game works because of one design decision: representing rooms as a nested dictionary where each key is a room name and each value is a dictionary of directions and items. Once that structure was in place, movement logic, item collection, and win-condition checking all became straightforward lookups and comparisons. That instinct — model the data first, then write the logic around it — is foundational to all programming beyond introductory scripting.

# Object-oriented programming (OOP) in JavaScript.

## Javascript Constructor Function
[watch video](https://www.youtube.com/watch?v=MBLCbJvyaA0)

## JavaScript Prototype Chain
[watch video](https://www.youtube.com/watch?v=1HEG5bvjJIA)

## JavaScript Classes
[watch video](https://www.youtube.com/watch?v=R4lPsqG2ic8)

## Challenge:

You are tasked with creating a class hierarchy for a simple game. The game will have different types of characters, each with their own abilities and attributes. Your task is to create the classes for the game characters using Object-oriented programming principles in JavaScript.

### Requirements
There should be a Character class that serves as the parent class for all game characters. It should have the following properties:

    - name: the name of the character
    - health: the health of the character
    - strength: the strength of the character

There should be three child classes that inherit from the Character class:

    - Warrior: a character that specializes in physical combat. It should have the following additional properties:
        - weapon: the type of weapon the warrior uses
        - power: a numeric value representing the warrior's special ability
    - Wizard: a character that specializes in magical combat. It should have the following additional properties:
        - spell: the type of spell the wizard uses
        - mana: the amount of mana the wizard has
    - Archer: a character that specializes in ranged combat. It should have the following additional properties:
        - bow: the type of bow the archer uses
        - accuracy: a numeric value representing the archer's accuracy
Each child class should have a method called attack that takes in a target character and deals damage based on the character's attributes and abilities.

Each child class should have a method called specialAbility that performs a special action based on the character's abilities.

### Example
Here's an example of how the classes should work together:

```
const warrior = new Warrior('Conan', 100, 10, 'Sword', 20);
const wizard = new Wizard('Gandalf', 80, 5, 'Fireball', 50);
const archer = new Archer('Legolas', 90, 7, 'Longbow', 75);


warrior.attack(wizard); // wizard's health is reduced
wizard.specialAbility(); // wizard uses special ability
archer.attack(warrior); // warrior's health is reduced
```

### Constraints
- You can assume that all input values are valid.
- You can assume that the attack method will always be called with a valid target character.
- You can assume that the specialAbility method will always be called with valid inputs.
- Your code should use proper Object-oriented programming principles in JavaScript.
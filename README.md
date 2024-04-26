# Zesheng Chen - Development Portfolio

## Game Title: Chord Clash
Link to team website and download our game: https://sites.google.com/view/chordclash/builds/beta

## Game Info
**Genre**: Rhythm, Local Multiplayer, Combat

**Platform**: Windows

**Game Overview**: Rhythm game! Select your characters, skills, and songs you would like them to play during the battle! Hitting notes to defeat your opponent. 
Don't forget to use power-ups to gain advantage!

**Notes**: Our games fully support keyboard navigation, so no mouse is needed!

## Development Info
**Team Size**: 7

**Personal Role**: Game Design Programmer, especially with User Interface (UI) design and keyboards navigation logic

**Tools Used**: Unreal 5, GitHub

**Duration**: March 13th 2024 - May 1st 2024

## Personal Contribution
- Implemented navigation system that allows both players to navigate all the menus, and make selections with keyboards only


- Implemented UI designs from tech team's mock-up, to improve the appearance of the UI system


- Implemented logic to correctly update the respective color for both players, without interfering each other's, including navigation and selection


- Implemented sound effects for navigation and selection of the UI system

*The gifs below are captured before the full implementation of art assets

![Main Menu & How to Play Menu.gif](Gifs%2FMain%20Menu%20%26%20How%20to%20Play%20Menu.gif)

![Navigating Through Menus.gif](Gifs%2FNavigating%20Through%20Menus.gif)

## Challenges
- This is my first time using Unreal Engine for the game development. It is my biggest challenges because I need to watch many tutorials and asking for help to familiarize the functionality of Unreal Engine 5. Since our game is developed sole using Blueprints instead of C++, I was struggled with the basics of blueprints as well at the beginning of our game production. With the help of tutorial videos and online resources, I was able to understand the use of Blueprints and implement them in our game.


- How to make navigation and selection work using keyboards only for both players is undoubtedly a great challenge for me. I followed through a video made by Youtuber Cibe, teaching how to implement navigation system for keyboards using Blueprints. His video is very helpful, demonstrating how to override OnKeyDown function to manage the different keyboards' inputs. The logic is to create integer variables that store index for each button, and store them into an array for each player. When using keyboards, use for loops to loop through the indexes in order to set and get the correct index when hovering on the button. Although his video only demonstrates one menu for only one player, I managed to achieve the goal of making it work for both players by copying the same logic for one player to another player.

  - I also fixed an issue when implementing this approach, which occurred in our Alpha build that the navigation did not work for player 2, The solution is to override OnKeyUp instead of OnKeyDown for keyboards navigation, to ensure the implementation of keyboards is functional.


- Another challenge I faced is to make selections that will go to next menu (only when both players made selections), and disable the navigation after the selection. I overcame this by creating two booleans and several branches (if statements), to check if only two players made selections, and jump over the logic of setting indexes if the selection is made. Then, I use Switch On Int node to decide each button's target, so that it will change the menu display into the next menu. 


- In order to display the setting and getting of indexes visually to players, I also need to implement the logic of correctly updating the color of both players during navigation and selection, without ruin each other's color update. The nodes for this implementation are not many, but the logics for it are complicated. Basically, I create a function for player 1, and copy it to player 2 so both have the same logic. Within this function, I need to make several branches to make sure the color update is correct.
  
  - Also, in our UI design, apart from the selection which updates the background color of a button, we actually update the border color of a button when the player is navigating. This is achieved by using Break/Make ButtonStyle, and Make SlateBrushOutlineSettings to set the border style of a button, to achieve the color effect on every button.

![Storing Index.png](Pictures%2FStoring%20Index.png)

![Button to Array.png](Pictures%2FButton%20to%20Array.png)

![Keyboards Navigation Logic Overview.png](Pictures%2FKeyboards%20Navigation%20Logic%20Overview.png)

![Set style for the button.png](Pictures%2FSet%20style%20for%20the%20button.png)

![Update Color Logic Example.png](Pictures%2FUpdate%20Color%20Logic%20Example.png)

## Code Architecture

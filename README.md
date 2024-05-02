# Zesheng Chen - Development Portfolio

## Game Title: Chord Clash
Link to team website and download our game:

https://sites.google.com/view/chordclash/builds/beta

## Game Info
**Genre**: Rhythm, Local Multiplayer, Combat

**Platform**: Windows

**Game Overview**: Rhythm game! Select your characters, skills, and songs you would like them to play during the battle! Hitting notes to defeat your opponent. 
Don't forget to use power-ups to gain advantage!

**Notes**: Our game fully supports keyboard navigation, so no mouse is needed!

## Development Info
**Team Size**: 7

**Personal Role**: Game Design Programmer, especially with User Interface (UI) design and keyboards navigation logic

**Tools Used**: Unreal 5, GitHub

**Duration**: March 13th 2024 - May 1st 2024

## Personal Contribution
- Implemented a navigation system that allows both players to navigate all the menus and make selections with keyboards only


- Implemented the Splash Screen, and UI designs from the tech team's mock-up to improve the appearance of the UI system


- Implemented logic to correctly update the respective color for both players without interfering with each other's, including navigation and selection


- Implemented sound effects for navigation and selection of the UI system

![Splash Screen.gif](Gifs%2FSplash%20Screen.gif)

![Main Menu Stuff.gif](Gifs%2FMain%20Menu%20Stuff.gif)

![Navigating Through Menus.gif](Gifs%2FNavigating%20Through%20Menus.gif)

## Challenges
- This is my first time using Unreal Engine for game development. It is my most significant challenge because I need to watch many tutorials and ask for help to familiarize the functionality of Unreal Engine 5. Since our game was developed solely using Blueprints instead of C++, I struggled with the basics of Blueprints at the beginning of our game production. With the help of tutorial videos and online resources, I was able to understand the use of Blueprints and implement them in our game.


- Making navigation and selection work using keyboards only for both players is undoubtedly challenging. I followed through a video by Youtuber Cibe, teaching how to implement a navigation system for keyboards using Blueprints. His video is beneficial, demonstrating how to override the OnKeyDown function to manage the different keyboards' inputs. The logic is to create integer variables that store an index for each button and store them into an array for each player. When using keyboards, use For Loops to loop through the indexes to set and get the correct index when hovering on the button. Although his video only demonstrates one menu for only one player, I achieved the goal of making it work for both players by copying the same logic from one player to another player.

  - I also fixed an issue when implementing this approach, which occurred in our Alpha build, where the navigation did not work for player 2; the solution is to override OnKeyUp instead of OnKeyDown for keyboard navigation to ensure the implementation of keyboards is functional.


- Another challenge I faced was to make selections that would go to the following menu (only when both players made selections) and turn off the navigation after the selection. I overcame this by creating two booleans and several branches (if statements) to check if only two players made selections and jump over the logic of setting indexes if the selection is made. Then, I used the Switch On Int node to decide each button's target so that it would change the menu display to the next menu.



- To display the setting and getting indexes visually to players, I also need to implement the logic of correctly updating the color of both players during navigation and selection without ruining each other's color update. The nodes for this implementation are few, but the logic is complicated. I create a function for player one and copy it to player two, so both have the same logic. I need to make several branches within this function to ensure the color update is correct.
  
  - Also, in our UI design, apart from the selection that updates the background color of a button, we actually update the border color of a button when the player is navigating. This is achieved by using Break/Make ButtonStyle and Make SlateBrushOutlineSettings to set the border style of a button to achieve the color effect on every button.

![Storing Index.png](Pictures%2FStoring%20Index.png)

![Button to Array.png](Pictures%2FButton%20to%20Array.png)

![Keyboards Navigation Logic Overview.png](Pictures%2FKeyboards%20Navigation%20Logic%20Overview.png)

![Set style for the button.png](Pictures%2FSet%20style%20for%20the%20button.png)

![Update Color Logic Example.png](Pictures%2FUpdate%20Color%20Logic%20Example.png)

## Code Architecture

Our game's code architecture is straightforward. In a nutshell, the Level Blueprint handles the game logic. The Main Menu will be displayed at the beginning of the game using the MainMenu Blueprint.

When both players select the buttons, the game stores the information for them in their respective PlayerPawn Blueprint, which is triggered later in the rhythm gameplay.

The gameplay will play songs, and players must use keyboards to hit notes. The NoteSpawner and Level Blueprint will handle most of the logic in the gameplay, and the InGameHUD Blueprint will display players' status, such as a health bar and texts as signifiers to let players know their status.

The Level Sequence will handle the camera animation and transition throughout the game.

I mainly contributed to the MainMenu Blueprint and individual blueprints for some menus. Below are simple UML diagrams I made to illustrate the structure. The first one is just part of a rough architecture of our game, and the second one is a more detailed architecture of my implementation in the MainMenu Blueprint.

![Rough Architecture of Our Game.png](UML%20Diagrams%2FRough%20Architecture%20of%20Our%20Game.png)

![More Detailed Architecture of My Implementation.png](UML%20Diagrams%2FMore%20Detailed%20Architecture%20of%20My%20Implementation.png)

## Version Control
For our game development, we used GitHub as our version control software.

Fortunately, all our tech team members were familiar with how GitHub works. One of our art team members used GitHub before, so we quickly learned how to coordinate using GitHub for Unreal Engine projects.

Our repository has a rule for pushing commits to the Main: each member must work in their own branch, using descriptive branch names, and must make a pull request for merging to the Main. The rule also states that the pull request can only be resolved when there are at least two approvals from team members. This will prevent someone from neglecting some of the details in the pull request and minimize the possibility of merge conflicts.

## Lessons Learned
- Don't be afraid to ask others for help. There are no stupid questions!


- Online resources, Unreal forums and videos, and all great tools to help you solve problems.


- Knowing how version control works in Unreal Engine is important to the team. This will improve team cooperation and minimize the risks of merge issues.


- Playtesting is important for gathering feedback. We were glad that all of the groups, including us, held in-person playtesting sessions for this class. I believe every group received good feedback.


- Keep communication for the team! The team needs to update each member's status every week so that other team members know about the progress made.
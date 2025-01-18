[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/MjLLqDcN)
# HW1
## W1L2 In-Class Activity
1. How would you describe this game world in Objects?
- UI:
  - Seeds planted number
  - Seeds reminded number
- Player:
  - Movement: WASD to move
- Seed:
  - Space to plant seeds
2. What attributes and actions do these objects have?
- Player:
  - Attributes:
    - Bunny sprites
  - Action:
  - Push WASD to move
  - Push the space to plant the seeds. The number of seeds planted increases, and the seeds remaining decrease. (show up in the UI)
- Plant:
  - Attributes:
    - Plant sprites
- Seed planted UI:
  - Attributes: text
  - Actions: The count goes up when the player plants a seed
- Seed remaining UI
  - Attributes: text 
  - Actions: The count goes down when the player plants a seed
3. How do these objects act on or affect each other?
- Players can grow plants, which appear when the player presses the space.

## Devlog
Before doing the homework, I reviewed the code I learned in GDIM31. In the beginning, I run the game first and see the player, background, and the UI of counts. Then, I stopped running the game and created the plant prefab. After that, I can see the plant on the game page. The next step for me is to open the script named Player and add this script to the Player inspector. I can see many member variables, but no code about move and plant exists. I first consider which setting in the Inspector corresponds to the member variable in the script, and then I write the code for movement. I first write code about moving up, and then I test this code to make sure there are no bugs. After that, I write the movement code so the player can move by pushing the keycode WASD. 

The next step is to make the player plant, so I use the Object. Instantiate in method PlantSeeds() to generate the plant in the player's position when pushing the keycode space. The next thing is to limit the count of plants remaining, so I first assign values 5 and 0 to variables _numSeedsLeft and _numSeedsPlanted. After that, I use if to make the code Instantiate execute in the condition that variable _numSeedsLeft is more than 0 in, and it can also execute the code that the count of seeds remaining goes down one and seeds plants goes up 1 when the player plant 1 time. 

The last step is to ensure the UI on the game page can change when the player plants, so I open another script named PlantCountUI. In this script, I can see two variable fields, named _plantedText and _remainingText, of types TMP_text and a public method UpdateSeeds, which takes two integer parameters. In this method, I update the text value of _plantedText and _remainingText by using code $“{value}.” After that, I create a new empty object in Unity, add the PlantCountUI in the UI’s inspector, and then drag the score text into the setting. After that, I drag UI into the “Plant Count UI” setting in the player object. In the player script, I reference the method UpdateSeeds in the method Start() and PlantSeeds() to ensure the UI synchronizes with the game's state. 

## Open-Source Assets
If you added any other outside assets, list them here!
- [Sprout Lands sprite asset pack](https://cupnooble.itch.io/sprout-lands-asset-pack) - character and item sprites

## Prof comments
You did a good job connecting your high-level plans into the code that you wrote. I would make sure for your next Devlog to also make it extremely clear how your break-down activity relates to the code that you wrote.

Please consider formatting your break-down activities with the hyphen '-' symbol as suggested above, and remove the prompts. This will make it a lot easier for me to read. See the [README formatting guide here](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

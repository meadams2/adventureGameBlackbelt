# adventureGameBlackbelt
CS120 Adventure Game Blackbelt 
Define main():
  Run getGame()
  currentNode gets "start"
  keepGoing gets True
  while keepGoing is True:
    Run playNode(game, currentNode)
    if currentNode is "quit:
      keepGoing gets false
    else:
      currentNode = playNode(game, currentNode)
Define getGame():
	Takes no parameters
	game = {
      "start": ["You bought a new Victorian era house.", "Explore the inside", "inside", "Explore the property", "property"], 
      "inside": ["You walk into the main foyer. To your left, there's a hallway. To the right there's another hallway. In the center there's a winding staircase.", "Explore the hallway to the left", "leftHallway", "Explore the hallway to the right", "rightHallway"], 
      "property": ["You see a barn, a root cellar, and a dilapidated well.", "Go into the barn.", "barn", "Go into the root cellar.", "cellar"], 
      "car": ["You are now in the car. You are a coward.", "Start over", "start", "Quit", "quit"], 
      "leftHallway": ["You see a locked vault and a door to the right of the locked vault.", "Try to open the vault", "vault", "Try to open the door to the right", "rightDoor"], 
      "rightHallway": ["You see a narrow servant's staircase at the end of the hallway. Along the right side, there are 2 doors. ", "Go up the servant's staircase", "stairCase2", "Open door 1.", "door1"], 
      "stairCase": ["You get to a landing. There's a hallway to the left and a hallway to the right.", "Go to the left", "left ", "Go to the right", "right"], 
      "vault": ["The vault is now open. ", "Go inside", "insideVault", "No thank you, I'm creeped out. ", "leftHallway"], 
      "rightDoor": ["The door swings open. ", "Go inside", "insideRightDoor", "Close door behind you. ", "closeRightDoor"], 
      "stairCase2": ["There's a landing at the at the second floor.", "Check out the second floor", "secondFloor", "Keep going up.", "goUp"], 
      "door1": ["A ghost turns around and shrieks at you to get out.", "Get out", "getOut", "Talk to the ghost", "talkGhost"], 
      "door2": ["You find a comfy looking bed.", "Take a nap", "nap", "Check out the room further", "investigate"], 
      "left ": ["You find a children's playroom. ", "Go inside", "insidePlayroom", "Go further down hallway", "furtherLeft"], 
      "right": ["You find a library with a bunch of dusty books.", "Go inside", "insideLibrary", "Go further down hallway", "furtherRight"], 
      "insideVault": ["There is a recently dead body in the vault.", "Get out of the vault", "leftHallway", "Poke body.", "poke"], 
      "closeVault": ["Why would you do that? You are now trapped with a body and run out of oxygen", "Start over", "start", "Quit", "quit"], 
      "insideRightDoor": ["A ghost comes up and offers you tea", "Take the tea", "takeTea", "Refuse tea", "refuseTea"], 
      "closeRightDoor": ["You are trapped inside with a ghost.", "Have a tea party with the ghost.", "ghostTea", "Introduce the ghost to TikTok", "ghostTikTok"], 
      "secondFloor": ["You find a closet", "Open closet", "openCloset", "Keep exploring floor", "keepExploring"], 
      "goUp": ["You find the attic. There is a ghost crying.", "Ask why the ghost is crying", "askGhost", "Leave", "rightHallway"], 
      "getOut": ["You fall and hit your head while in a rush to get out.", "Start over", "start", "Quit", "quit"], 
      "talkGhost": ["The ghost was lonely and needed someone to talk to. ", "Talk about computer science.", "computerScience", "Talk about literallly anything else", "anythingElse"], 
      "insultGhost": ["The ghost takes offense and kills you.", "Start over", "start", "Quit", "quit"], 
      "nap": ["A ghost comes in and kills you while you sleep", "Start over", "start", "Quit", "quit"], 
      "investigate": ["You find a strange trapdoor", "Go inside trapdoor", "trapDoor", "Nah man. ", "rightHallway"], 
      "insidePlayroom": ["A ghost child is rocking on a rocking horse", "Play with him", "playGhost", "Nope. Not happening.", "left "], 
      "furtherLeft": ["You find another door. The door is unlocked.", "Open door", "openDoor", "Keep going.", "furtherLeft2"], 
      "poke": ["Why would you do that? The ghost of the body kills you.", "Start over", "start", "Quit", "quit"], 
      "investigateVault": ["The door slams behind you. You die", "Start over", "start", "Quit", "quit"], 
      "takeTea": ["The ghost is pleased and offers to live with you peacefully", "Accept offer", "acceptOffer", "Call the ghost stinky and ugly", "insultGhost"], 
      "refuseTea": ["The ghost takes offense and kills you.", "Start over", "start", "Quit", "quit"], 
      "ghostTea": ["The ghost is pleased and you become great friends", "Start over", "start ", "Quit", "quit"], 
      "ghostTikTok": ["The ghost is confused, but ultimately is amused.", "Show the ghost instagram", "instagram", "Show the ghost reddit", "reddit"], 
      "askGhost": ["The ghost is happy to have someone to talk to. You live peacefully as roommates", "Start over", "start", "Quit", "quit"], 
      "computerScience": ["The ghost is intrigued and asks to learn more.", "Introduce them to Andy", "andy", "Refer them to chatGPT", "chatGPT"], 
      "anythingElse": ["The ghost is bored and kills you.", "Start over", "start", "Quit", "quit"], 
      "ghostDied": ["The ghost takes offense and kills you.", "Start over", "start ", "Quit", "quit"], 
      "openDoor": ["There is a very comfortable looking bed.", "Take a nap.", "nap", "Remake the bed.", "makeBed"], 
      "knockDoor": ["The ghost is very appreciative of your manners. You respect each other's personal space.", "Start over", "start", "Quit", "quit"], 
      "furtherLeft2": ["A painting falls on you. You die.", "Start over", "start", "Quit", "quit"], 
      "acceptOffer": ["You live a long peaceful life!", "Start over", "start", "Quit", "quit"], 
      "instagram": ["The ghost loves Keeping Up with the Kardashians", "Start over", "start", "Quit", "quit"], 
      "reddit": ["The ghost is confused by subreddits and kills you.", "Start over", "start", "Quit", "quit"], 
      "andy": ["The ghost learns a lot about computer science. ", "Introduce them to chatGPT", "chatGPT", "Let them come to class with you", "class"], 
      "chatGPT": ["The ghost hates it.", "Start over", "start", "Quit", "quit"], 
      "makeBed": ["The ghost asks if you could wash the sheets", "Say no", "noSheets", "Say yes", "washSheets"], 
      "washSheets": ["The ghost likes the clean sheets and you live peacefully.", "Start over", "start", "Quit", "quit"], 
      "class": ["The ghost gets a good grade in computer science.", "Start over", "start", "Quit", "quit"], 
      "barn": ["A rattlesnake bites you and you die.", "Start over", "start", "Quit", "quit"], 
      "cellar": ["The cellar door slams shut behind you. You die.", "Start over", "start", "Quit", "quit"], 
      "well": ["You fall into the well and die.", "Start over", "start", "Quit", "quit"], 
 }
	Return game.

Define playNode():
	playNode takes game and nodeKey
	currentNode gets game[nodeKey]
	Extract description, menu1, node1, menu2, node2, menu3, and node3
	Print description, menu1, menu2, and menu3
	Ask for user choice. Put in userChoice.
	Force userChoice to integer.
	If userChoice is 1:
		currentNode gets node1
	elif userChoice is 2:
		currentNode gets node2
	else userChoice is 3:
		currentNode gets node3
	Return current node
	

	

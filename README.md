# adventureGameBlackbelt
CS120 Adventure Game Blackbelt 
Define main():
  Run getGame()
  currentNode gets "start"
  keepGoing gets True
  whiel keepGoing is True:
    Run playNode(game, currentNode)
    if currentNode is "quit:
      keepGoing gets false
    else:
      currentNode = playNode(game, currentNode)
    

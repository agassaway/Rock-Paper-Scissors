import random
import sys
  
def rock_paper_scissors():
  player_choice = input("Rock, Paper, or Scissors?:")
  rpc = ["rock", "paper", "scissors"]
  computer_choice = random.choice(rpc)
  
  if player_choice.lower() not in rpc:
    print("Not a valid entry")
  else:
    print("Enemy chooses: %s" %computer_choice)
    
  while player_choice == "Rock".lower():
    if computer_choice == "scissors":
      print("You win!")
    elif computer_choice == "rock":
      print("You tied!")
    else:
      print("You lose :(")
    break
  
  while player_choice == "Paper".lower():
    if computer_choice == "rock":
      print("You win!")
    elif computer_choice == "paper":
      print("You tied!")
    else:
      print("You lose :(")
    break
    
  while player_choice == "scissors".lower():
    if computer_choice == "paper":
      print("You win!")
    elif computer_choice == "scissors":
      print("You tied!")
    else:
      print("You lose :(")
    break
  
def want_to_play_again(next_round):  
  play_again = (input("Do you want to play again? Y/N:"))
  play_again_choices = ["yes", "no", "y", "n"]
  
  if play_again.lower() not in play_again_choices:
    print("Not a valid entry")
    want_to_play_again(next_round)
  while play_again.lower() == "yes" or play_again.lower() == "y":
    next_round()
    want_to_play_again(next_round)
    break
  else:
    sys.exit("That was a fun game!")

  
rock_paper_scissors()
want_to_play_again(rock_paper_scissors)

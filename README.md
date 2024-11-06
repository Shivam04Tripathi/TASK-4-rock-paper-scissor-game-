# TASK-4-rock-paper-scissor-game-
import random

def get_computer_choice():
    return random.choice(["rock", "paper", "scissors"])

def determine_winner(user_choice, computer_choice):
    if user_choice == computer_choice:
        return "tie"
    elif (user_choice == "rock" and computer_choice == "scissors") or \
         (user_choice == "scissors" and computer_choice == "paper") or \
         (user_choice == "paper" and computer_choice == "rock"):
        return "user"
    else:
        return "computer"

def play_round():
    user_choice = input("Choose rock, paper, or scissors: ").lower()
    
    if user_choice not in ["rock", "paper", "scissors"]:
        print("Invalid choice. Please try again.")
        return None, None
    
    computer_choice = get_computer_choice()
    print(f"Computer chose: {computer_choice}")
    
    winner = determine_winner(user_choice, computer_choice)
    
    if winner == "tie":
        print("It's a tie!")
    elif winner == "user":
        print("You win!")
    else:
        print("Computer wins!")
    
    return winner

def main():
    print("Welcome to Rock, Paper, Scissors!")
    user_score = 0
    computer_score = 0
    
    while True:
        winner = play_round()
        
        if winner == "user":
            user_score += 1
        elif winner == "computer":
            computer_score += 1
        
        # Display current scores
        print(f"\nScores: You - {user_score}, Computer - {computer_score}\n")
        
        # Ask if the user wants to play again
        play_again = input("Do you want to play another round? (yes/no): ").lower()
        if play_again != "yes":
            print("Thanks for playing!")
            break

# Run the game
main()






OUTPUT 


Welcome to Rock, Paper, Scissors!
Choose rock, paper, or scissors: rock
Computer chose: scissors
You win!

Scores: You - 1, Computer - 0

Do you want to play another round? (yes/no): yes
Choose rock, paper, or scissors: paper
Computer chose: rock
You win!


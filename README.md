# Rock-Paper-Scissors-Game.py
import random

choices = ["rock", "paper", "scissors"]

WIN = 0
LOST = 0
TIES = 0
current_round = 0

rounds = int(input("How many rounds do you want to play? "))

while current_round < rounds:
    computer_choice = random.choice(choices)
    user_choice = input(f"Round {current_round + 1} - Enter rock, paper, or scissors (or 'quit' to exit): ").lower()

    if user_choice == "quit":
        print("\nExiting the game. Goodbye!")
        print(f"Final Score -> Wins: {WIN}, Losses: {LOST}, Ties: {TIES}")
        break
    elif user_choice not in choices:
        print("Invalid choice. Try again!\n")
        continue    
    elif user_choice == computer_choice:
        print(f"Both chose {user_choice}. It's a tie!")
        TIES += 1
    elif (user_choice == "rock" and computer_choice == "scissors") or \
         (user_choice == "paper" and computer_choice == "rock") or \
         (user_choice == "scissors" and computer_choice == "paper"):
        print(f"You win! {user_choice} beats {computer_choice}.")
        WIN += 1
    else:
        print(f"You lose! {computer_choice} beats {user_choice}.")
        LOST += 1

    current_round += 1
    print(f"Score -> Wins: {WIN}, Losses: {LOST}, Ties: {TIES}\n")

# Final Result
print("🏁 Final Result 🏁")
print(f"You: {WIN} | Computer: {LOST} | Ties: {TIES}")

if WIN > LOST:
    print("🎉 Congratulations, you win the match!")
elif LOST > WIN:
    print("😢 You lost the match. Better luck next time!")
else:
    print("🤝 It's a tie overall!")

import random

def get_user_choice():
    print("\n🎮 Rock, Paper, Scissors Game!")
    print("Type: rock, paper, or scissors")
    return input("Your choice: ").lower()

def get_computer_choice():
    return random.choice(['rock', 'paper', 'scissors'])

def decide_winner(player, computer):
    print(f"🧑 You chose: {player}")
    print(f"💻 Computer chose: {computer}")

    if player == computer:
        return "🤝 It's a tie!"
    elif (player == 'rock' and computer == 'scissors') or \
         (player == 'paper' and computer == 'rock') or \
         (player == 'scissors' and computer == 'paper'):
        return "🏆 You win!"
    else:
        return "😢 You lose."

def play():
    while True:
        user = get_user_choice()
        if user not in ['rock', 'paper', 'scissors']:
            print("❌ Invalid input. Try again.")
            continue
        computer = get_computer_choice()
        result = decide_winner(user, computer)
        print(result)

        again = input("\nPlay again? (yes/no): ").lower()
        if again != 'yes':
            print("👋 Thanks for playing!")
            break

play()

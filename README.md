# python-code
# a project of need 
import random

def get_computer_choice():
    """Randomly selects the computer's choice: Snake, Water, or Gun."""
    choices = ['snake', 'water', 'gun']
    return random.choice(choices)

def get_user_choice():
    """Prompts the user for their choice and validates the input."""
    while True:
        user_input = input("Enter your choice (snake, water, or gun): ").lower().strip()
        if user_input in ['snake', 'water', 'gun']:
            return user_input
        else:
            print("Invalid choice. Please enter 'snake', 'water', or 'gun'.")

def determine_winner(user_choice, computer_choice):
    """Determines the winner based on the game rules."""
    # Tie condition
    if user_choice == computer_choice:
        return "It's a tie!"

    # Winning conditions for the user
     Snake drinks Water (Snake wins)
    elif (user_choice == 'snake' and computer_choice == 'water'):
        return "You win! Snake drinks Water."
    # Water rusts Gun (Water wins)
    elif (user_choice == 'water' and computer_choice == 'gun'):
        return "You win! Water rusts Gun."
    # Gun kills Snake (Gun wins)
    elif (user_choice == 'gun' and computer_choice == 'snake'):
        return "You win! Gun kills Snake."

    # All other conditions are losses for the user (wins for the computer)
    else:
        # Provide a more specific loss reason for clarity
        if computer_choice == 'snake' and user_choice == 'water':
            return "Computer wins! Snake drinks Water."
        elif computer_choice == 'water' and user_choice == 'gun':
            return "Computer wins! Water rusts Gun."
        elif computer_choice == 'gun' and user_choice == 'snake':
            return "Computer wins! Gun kills Snake."
        else:
            # Fallback for unexpected cases, though the 'if/elif' above covers all
            return "Computer wins!"


def play_game():
    """Main function to run the Snake, Water, Gun game."""
    print("Welcome to Snake 🐍, Water 🌊, Gun 🔫 Game!")
    print("Rules: Snake vs Water -> Snake wins | Water vs Gun -> Water wins | Gun vs Snake -> Gun wins.")

    # Get choices
    user_choice = get_user_choice()
    computer_choice = get_computer_choice()

    print(f"\nYour choice: {user_choice.capitalize()}")
    print(f"Computer's choice: {computer_choice.capitalize()}")

    # Determine and print the result
    result = determine_winner(user_choice, computer_choice)
    print(f"\n--- {result} ---")

# Execute the game
if __name__ == "__main__":
    play_game()

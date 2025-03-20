import random

def coin_toss():
    return random.choice(["Heads", "Tails"])

def multiple_tosses(num_flips):
    heads_count = 0
    tails_count = 0
    
    for _ in range(num_flips):
        result = coin_toss()
        print(result)
        if result == "Heads":
            heads_count += 1
        else:
            tails_count += 1
    
    total = heads_count + tails_count
    print("\nResults:")
    print(f"Heads: {heads_count} ({(heads_count/total) * 100:.2f}%)")
    print(f"Tails: {tails_count} ({(tails_count/total) * 100:.2f}%)")

def main():
    while True:
        try:
            num_flips = int(input("Enter the number of times you want to flip the coin: "))
            if num_flips <= 0:
                print("Please enter a positive number.")
                continue
            
            multiple_tosses(num_flips)
            
            repeat = input("Do you want to toss again? (yes/no): ").strip().lower()
            if repeat != "yes":
                print("Thank you for using the virtual coin toss simulator!")
                break
        except ValueError:
            print("Invalid input. Please enter a valid number.")

if __name__ == "__main__":
    main()

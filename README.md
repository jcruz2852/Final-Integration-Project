# Final-Integration-Project

# John Cruz
# This program will calculate the price of granite/quartz/marble/quartzite countertops for clients.
# "to explain code that isnt obvious"
# "citations"
import random


print('''   Greetings, my name is John Cruz, i'm a Business Computer Systems major. I currently work 
for my dad who owns "Majestic Countertops" in Punta Gorda, Florida. I chose this major because 
one day I hope to step in his shoes and run his business when he decides to retire.''')

print('\n')  # spacing my codes so that i can read them easier in shell.
#  The material types that we stock and supply.
print("Available Stones:", sep='')

print("-granite", sep=''), print("-quartz", sep=''), print("-marble", sep=''), print("-quartzite", sep='')

print(sep='')  # a line break in shell for clear reading and remember that the top code belongs with the bottom code.

# LEVEL ONE Stone Prices per Sq.Ft:
# granite = 45
# quartz = 50
# marble = 60
# quartzite = 60
square_feet = int()
material_type = ("granite", "quartz", "marble", "quartzite")


# Collecting Customer Project Square Feet
def num_input(square_feet):
    """
    def function for acquiring customer square footage. """
    good_input = False
    while not good_input:
        try:
            square_feet = int(input("How many square feet does your project have? "))
            good_input = True
            print("Project square footage: ", square_feet, sep='')
        except ValueError:
            print("Error. Must be a whole number.")
    return square_feet


square_feet = num_input("square_feet")

print(sep='')


def material_choice(material_type):
    """
   def function to acquire the customers selected stone. """
    while True:
        try:
            material_type = input("What type of material are you interested in? ")
            material_type = material_type.lower()
            if material_type == "granite" or material_type == "quartz" or material_type == "marble" or \
                    material_type == "quartzite":
                print("Great, lets get you started with a free quote!")
                break
        except:
            pass
        print("Oops, please choose a material from the list.")
    return material_type


material_type = material_choice("material_type")

# calculating subtotal

if material_type == "granite":
    material_price = 45
    print("Your subtotal is: $", format(material_price * square_feet, '0.2f'), sep='')
elif material_type == "quartz":
    material_price = 50
    print("Your subtotal is: $", format(material_price * square_feet, '0.2f'), sep='')
elif material_type == "marble":
    material_price = 60
    print("Your subtotal is: $", format(material_price * square_feet, '0.2f'), sep='')
elif material_type == "quartzite":
    material_price = 60
    print("Your subtotal is: $", format(material_price * square_feet, '0.2f'), sep='')

sink = 200
sink_cut = 150
discount = 200
total_extras = 200 + 150 - 200
print("Your total is: $", format(material_price * square_feet + total_extras), sep='')

# calculating square footage when customer only provides a layout.
# Vanity size is 70in x 22.5in
vanity = int(70 * 22.5)
print("your vanity square footage is: ", vanity / 144)

# calcualting square footage, but leaving out decimals or the remainder.
vanity = int(70 * 22.5)
print("your vanity square footage is: ", vanity // 144)

# calculating backsplash sq/ft
print("your backsplash square footage is: ", (100 * 4) / 144)


#   collecting original sale price using def function.


def get_float_input(original_price):
    """
    using def function to acquire the original sale price."""
    good_input = False
    while not good_input:
        try:
            original_price = float(input("Enter original sale price of goods: "))
            good_input = True
            print("Original price: $", format(original_price, '.2f'), sep='')
        except ValueError:
            print("Error. Must be a float number.")
    return original_price


original_price = int(get_float_input("original_price"))


#   collecting discounted sale price using def function.


def get_float_input(sale_price):
    """
   def function in order to acquire the retail listed sale price"""
    good_input = False
    while not (good_input):
        try:
            sale_price = float(input("Enter discounted sale price of goods: "))
            good_input = True
            print("Sale price: $", format(sale_price, '.2f'), sep='')
        except ValueError:
            print("Error. Must be a float number.")
    return sale_price


sale_price = int(get_float_input("sale_price"))


#   collecting percent discount using def function.

def sales_discount(percentage):
    """
    using def function to acquire the discount percentage."""
    good_input = False
    while not (good_input):
        try:
            percentage = (original_price - sale_price / original_price * 100)
            good_input = True
            print("Percent off: ", format(percentage, ".2f"), "%", sep='')
        except ValueError:
            print("Error. Must be a float number.")
        return percentage


sales_discount("percentage")

# this is how you use "**"
print(12 ** 2)

# this is how you us "%"
print(12 % 5)

# this is how you use a concatenate
a = "countertops"
b = "are"
c = "cool"
d = "bro"
print(a + b + c + d)

a = "countertops"
print(a * 50)

# Granite sale, depending on project size.

square_feet = int(num_input("square_feet"))
granite_price = 0
if square_feet >= 50:
    granite_price += 40
    print("Congratulations, you qualify for our sale. Your granite price is: $", format(granite_price, '0.2f'), sep='')
else:
    granite_price += 45
    print("You don't qualify for our sale. Your granite price is: $", format(granite_price, '0.2f'), sep='')

# free sink if your material is granite and you have more than 50 sq/ft
material_type = material_choice("material_type")
square_feet = int(num_input("square_feet"))
# sink = 200
sub_total = 0
if (material_type == "granite") and (square_feet < 50):
    sink = 0
    print("Congrats you qualify for our month sale. You get a free sink!")
if (material_type != "granite") or (square_feet > 50):
    sink = 200
    print("Your sink price is: $", format(sink, '0.2f'), sep='')


# getting material price using def and if-elif-else. menu.

def material_type1(granite):
    """
    def function in regards to the material type."""
    pass


def material_type2(quartz):
    """
    def function in regards to the material type."""
    pass


def material_type3(marble):
    """
    def function in regards to the material type."""
    pass


def material_type4(quartzite):
    """
    def function in regards to the material type."""
    pass


while True:
    print("Select a number for the material you are interested in?")
    print("1.Granite")
    print("2.Quartz")
    print("3.Marble")
    print("4.Quartzite")
    print("5.Done sellecting.")
    material_type = input("Selection: ")

    if material_type == "1":
        print("The granite selected starts at $45.00 a square foot.")

    elif material_type == "2":
        print("The quartz selected starts at $50.00 a square foot.")

    elif material_type == "3":
        print("The marble selected starts at $60.00 a square foot.")

    elif material_type == "4":
        print("The quartzite selected starts at $60.00 a square foot.")

    elif material_type == "5":
        break

    else:
        print("Please select a valid number.")

# random number, vanity give away.


def random_num_game(number_selected):
    """
    def function in order to collect random numbers from users."""
    for i in range(1, 1001):
        try:
            number_selected = int(input("Please select a number between 0 and 1000: "))
            random_number = random.randint(1, 1001)
            if number_selected != random_number and random_number == (0 < random_number < 1000):
                print("Random number:", random_number)
                print("Sorry you are not the winner. Come by our location to receive 5% off of any material.")
            if number_selected == random_number:
                print("Random number:", random_number)
                print("Congratulations you are the winner. Come by our location to receive you FREE vanity.")
            if random_number != (0 < random_number < 1000):
                print("You selected an invalid number. You are not the winner.")
                break
        except ValueError:
            print("Error. Must be a whole number between 1-1000.")
    return number_selected


random_num_game("number_selected")


def random_max():
    """
    def function in order to acquire a random max number"""
    num1 = random.randint(0, 1000)
    num2 = random.randint(0, 1000)
    if num1 > num2:
        print("The random max number is:", num1)
    else:
        print("The random max number is:", num2)


random_max()


# using not
def material_choice_list(material_type):
    """
    def function in order to acquire customer material selection from a list"""
    good_input = False
    while not (good_input):
        material_list = ["granite", "quartz", "marble", "quartzite"]
        material_type = input("What type of material are you interested in? ")
        good_input = True
        if material_type in material_list:
            print("Great, lets get you started with a free quote!")
        if material_type not in material_list:
            print("Oops, that wasnt a valid material. Please give us a call.")
        return material_type


material_choice_list("material_type")

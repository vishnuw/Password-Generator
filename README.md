# Password-Generator
A simple password generator which generates password based on the input of your name and age
import random
import array as arr

# maximum length of password needed
# this can be changed to suit your password length
list_A= [8,9,10,11,12]
max_len = random.choice(list_A)

print("Enter Your Name: ") 

name= input()
nameU= name.upper()
nameL= name.lower()

print("Enter Your Age: ")
age= input()

charac_U= list(nameU)
charac_L= list(nameL)
charac_NO= list(age)

digits = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']
symbols = ['^', ';', '%', '<', '#', '$', '?', ':', '@', '.', '/', '!', '~', '>',
        '*', '(', ')', '=']

# combining all the characters from above arrays into one array
combined_list = digits + charac_U + charac_L + symbols + charac_NO

# randomly selecting a character from each set of characters
rand_digit = random.choice(digits)
rand_charac_U = random.choice(charac_U)
rand_charac_L = random.choice(charac_L)
rand_charac_NO = random.choice(charac_NO)
rand_symbol = random.choice(symbols)

# combining randomly selected characters
temp_pass = rand_digit + rand_charac_U + rand_charac_L + rand_symbol + rand_charac_NO

for x in range(max_len - 5):
    temp_pass = temp_pass + random.choice(combined_list)

    temp_pass_list = arr.array('u', temp_pass)
    random.shuffle(temp_pass_list)

password = ""
for x in temp_pass_list:
        password = password + x
        
print("Your newly generated password is: " , password)

# Caeser-s-Cipher-Encryption
In cryptography, a Caesar cipher, also known as shift cipher, is one of the simplest and most widely known encryption techniques.

# **Description**
It is a type of substitution cipher in which each letter is the plaintext is replaced by a letter of some fixed number of postitons down the alphabet.

For exmaple, with a left shift of 3, D would be replaced by A,E will become B, and so on.

# **Question**
Plain: ABCDEFGHIJKLMOPQRSTUVWXYZ

Cipher: XYZABCDEFGHIJKLMNOPQRSTUVW

Plaintext: THE QUICK BROWN FOX JUMPS OVER THE LAZY DOG

Ciphertext: QEB NRFZH YOLTK CLU GRJMP LSBO QEB IXWV ALD

Diciphering is done in reverse, with a right shift of 3.

# The Code
```
# create function to cipher and decipher the text
def encrypt(text, number, encrypt_input):
    new_string = '' # create a new string variable to hold the encrpted text
    for char in text: # loop through the input text
        if char in alphabets_list:
            index = alphabets_list.index(char) # get the index of each letter
            if encrypt_input == 'cipher': # if decipher is chosen
                new_index = index - number
                output_text = 'Ciphertext'
                input_text = 'Plain_text'
            else:                           #if decipher is chosen
                new_index = index + number
                new_index %= 26
                input_text = 'Ciphertext'
                output_text = 'Plaintext'
            new_char = alphabets_list[new_index] # create a new character using the shift number
            new_string = new_string + new_char
        else:
            new_string += char # add the character to new_string
    print(f'\n{input_text}: {text} \n{output_text}: {new_string}')



# create a list of all alphabets
alphabets = string.ascii_uppercase
alphabets_list = list(alphabets)
not_ended = True

while not_ended:
    # input the plain text
    text = input('Enter text to be encrypted. ').upper()
    # get the shift number
    shift_number = int(input('Enter shift number. ')) % 26
    # choose whether to cipher or decipher the text
    encryption = input("Input 'cipher' or 'decipher' to encrypt. ").lower()
    encrypt(text, shift_number, encryption)
    continue_ = input('Would you like to continue? "Y" or "N". ').lower()
    if continue_ == 'n':   # stop the program if  user decided to end it 
        not_ended = False

```

# The Result
![The Cipher](./images/Cipher.png)

# AUTHOR
Alberta Cofie

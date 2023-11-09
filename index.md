# This is a test header
### This is a second, smaller test header

![Image of Flame Princess smoking in the style of FLCL](https://external-preview.redd.it/yJY793FwBkO6lcHF4dEhc5fsmblp3lExtqObyit-xwA.jpg?width=1024&auto=webp&s=00f19fa95197fd085c3e7e715ecc3e7552a68784)

``` {Python}
import random



encrypt = 0          ##set to 1 if you want to encrypt the message
encrypt_random = 0   ##set to 1 if you want to generate a randomized key.  If not, you must enter a key below.
decrypt = 1          ##set to 1 if you want to decrypt a coded message.  If encrypt is enabled it will not decrypt the coded message you input.  It will simply restate the plaintext message





message = "Hey, this is my new and improved encryption function.  I think it's pretty cool."

key = "d(H1@.M[bcs{vLWe7I*\_t+)]N9R6~'?O!&P4kjA2 #^}m|EBh3VDp0QK=nYGF%uqiT<afry-/S;CZo5zwX>$8UxJ`l,g:"

coded_message = "['3D:m!&}:&}:j3:A'B:9A~:&j ^2E'~:'A6^3 m&2A:?|A6m&2Ap::b:m!&A4:&mY}: ^'mm3:622kp"




characters = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz,./\|@;':[]{}()<>-_!?$%^&*=+`~#0123456789 "

characters_list = []                      ##turns the characters into a list for easier iteration
for x in characters:
    characters_list.append(x)
characters_temp = characters_list.copy()

if encrypt == 1:
    if encrypt_random == 1:            ##Generates a random key if selected above by pulling characters from characters_temp at random and putting them in a new list                                               
        key_list = []
        for x in range(len(characters_list)):
            removal_point = random.randint(0, len(characters_temp)-1)
            key_list.append(characters_temp.pop(removal_point))
            
        key = ''.join(key_list)
    
    cipher_dict = {}                   ##creates a cipher dictionary connecting each character to another based on the key
    for x in characters:
        cipher_dict[x] = key[characters.find(x)]

    encrypted_message = []
    for x in message:                  ##creates a list replacing each character in the message with it corresponding character based on the cipher dictionary
        if x in cipher_dict:
            encrypted_message.append(cipher_dict[x])
        else:
            encrypted_message.append(x)
            
    coded_message = ''.join(encrypted_message.copy())
    print(characters)
    print(key)
    print()
    print(message)
    print()
    print (''.join(encrypted_message))
    print()

if decrypt == 1:
    cipher_dict = {}
    for x in key:
        cipher_dict[x] = characters[key.index(x)]

    decrypted_message = []
    for x in coded_message:
        if x in cipher_dict:
            decrypted_message.append(cipher_dict[x])
        else:
            decrypted_message.append(x)    

    print (''.join(decrypted_message))
```

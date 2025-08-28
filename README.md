## EX. NO: 1 : IMPLEMENTATION OF CAESAR CIPHER
## NAME: NAVEEN . S
## REG.NO: 212223240106
## AIM:

To implement the simple substitution technique named Caesar cipher using C language.

## DESCRIPTION:

To encrypt a message with a Caesar cipher, each letter in the message is changed using a simple rule: shift by three. Each letter is replaced by the letter three letters ahead in the alphabet. A becomes D, B becomes E, and so on. For the last letters, we can think of the
alphabet as a circle and "wrap around". W becomes Z, X becomes A, Y bec mes B, and Z
becomes C. To change a message back, each letter is replaced by the one three before it.

## EXAMPLE:

![image](https://github.com/Hemamanigandan/CNS/assets/149653568/eb9c6c43-8c80-4cdd-b9d4-91705a311c79)

## ALGORITHM:

### STEP-1: Read the plain text from the user.
### STEP-2: Read the key value from the user.
### STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.
### STEP-4: Else subtract the key from the plain text.
### STEP-5: Display the cipher text obtained above.


PROGRAM :-
~~~
#include <stdio.h>
#include <string.h>
void caesarCipher(char *text, int shift) 
{
    for (int i = 0; text[i]; i++) 
    {
        if (text[i] >= 'A' && text[i] <= 'Z')
        text[i] = ((text[i]- 'A' + shift) % 26) + 'A';
        
    }
 }
int main() 
{
    char text[] = "NAVEEN";
    printf("Plaintext: %s\n",text);
    caesarCipher(text, 3);
    printf("Encrypted Message: %s\n", text);
    caesarCipher(text,-3);
    printf("Decrypted Message: %s\n", text);
    return 0;
    
}
~~~
OUTPUT :-
<img width="1917" height="968" alt="image" src="https://github.com/user-attachments/assets/0222d05b-4fcb-4995-b3e5-4a3423f9a827" />


The program was exceutted sucessfully.

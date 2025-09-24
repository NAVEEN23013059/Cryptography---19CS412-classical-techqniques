# Rail Fence Cipher
Rail Fence Cipher using with different key values

## REGISTER NUMBER:212223240106
## name : naveen.s

# AIM:

To develop a simple C program to implement Rail Fence Cipher.

## DESIGN STEPS:

### Step 1:

Design of Rail Fence Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 
ALGORITHM DESCRIPTION:
In the rail fence cipher, the plaintext is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

## PROGRAM:

```

#include <stdio.h>
#include <string.h>
#include <stdbool.h>

void encryptRailFence(char text[], int key, char result[]) {
    int len = strlen(text);
    char rail[key][len];
    bool dir_down = false;
    int row = 0, col = 0;

  
    for (int i = 0; i < key; i++)
        for (int j = 0; j < len; j++)
            rail[i][j] = '\n';

    
    for (int i = 0; i < len; i++) {
        if (row == 0 || row == key - 1)
            dir_down = !dir_down;
        rail[row][col++] = text[i];
        row += dir_down ? 1 : -1;
    }


    int idx = 0;
    for (int i = 0; i < key; i++)
        for (int j = 0; j < len; j++)
            if (rail[i][j] != '\n')
                result[idx++] = rail[i][j];
    result[idx] = '\0';
}

void decryptRailFence(char cipher[], int key, char result[]) {
    int len = strlen(cipher);
    char rail[key][len];
    bool dir_down;
    int row, col;

    for (int i = 0; i < key; i++)
        for (int j = 0; j < len; j++)
            rail[i][j] = '\n';

    dir_down = false;
    row = 0; col = 0;
    for (int i = 0; i < len; i++) {
        if (row == 0) dir_down = true;
        if (row == key - 1) dir_down = false;
        rail[row][col++] = '*';
        row += dir_down ? 1 : -1;
    }


    int index = 0;
    for (int i = 0; i < key; i++)
        for (int j = 0; j < len; j++)
            if (rail[i][j] == '*' && index < len)
                rail[i][j] = cipher[index++];

    result[len] = '\0';
    row = 0; col = 0;
    dir_down = false;
    for (int i = 0; i < len; i++) {
        if (row == 0) dir_down = true;
        if (row == key - 1) dir_down = false;
        result[i] = rail[row][col++];
        row += dir_down ? 1 : -1;
    }
}

int main() {
    char text[100], cipher[100], decrypted[100];
    int key;

    printf("Enter plaintext: ");
    scanf("%[^\n]", text);

    printf("Enter key (number of rails): ");
    scanf("%d", &key);

    encryptRailFence(text, key, cipher);
    printf("Ciphertext: %s\n", cipher);

    decryptRailFence(cipher, key, decrypted);
    printf("Decrypted text: %s\n", decrypted);

    return 0;
}

```
## OUTPUT:


Simulating Rail Fence Cipher

<img width="1834" height="908" alt="image" src="https://github.com/user-attachments/assets/f47b6ea7-a4d8-4738-aaaf-2375ccf822fe" />



## RESULT:
The program is executed successfully

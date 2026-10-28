# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER
## DHANUSH(212224100011)

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:
```
#include <stdio.h>
#include <string.h>
int main()
{
    char text[100], cipher[100];
    int key, i;
    printf("Enter the plain text: ");
    fgets(text, sizeof(text), stdin);
    text[strcspn(text, "\n")] = '\0';
    printf("Enter the key: ");
    scanf("%d", &key);
    int k = ((key % 26) + 26) % 26;
    // Encryption
    for (i = 0; text[i] != '\0'; i++)
    {
        if (text[i] >= 'A' && text[i] <= 'Z')
            cipher[i] = (text[i] - 'A' + k) % 26 + 'A';
        else if (text[i] >= 'a' && text[i] <= 'z')
            cipher[i] = (text[i] - 'a' + k) % 26 + 'a';
        else
            cipher[i] = text[i];
    }
    cipher[i] = '\0';
    printf("Cipher text: %s\n", cipher);
    // Decryption
    getchar();
    printf("Enter your cipher text: ");
    fgets(cipher, sizeof(cipher), stdin);
    cipher[strcspn(cipher, "\n")] = '\0';
    printf("Enter the key for decryption: ");
    scanf("%d", &key);
    k = ((key % 26) + 26) % 26;
    for (i = 0; cipher[i] != '\0'; i++)
    {
        if (cipher[i] >= 'A' && cipher[i] <= 'Z')
            cipher[i] = (cipher[i] - 'A' - k + 26) % 26 + 'A';
        else if (cipher[i] >= 'a' && cipher[i] <= 'z')
            cipher[i] = (cipher[i] - 'a' - k + 26) % 26 + 'a';
    }
    printf("Plain text: %s\n", cipher);
    return 0;
}

```

## OUTPUT:
<img width="940" height="388" alt="image" src="https://github.com/user-attachments/assets/bb06149b-78dd-4257-9744-61b4ad24680c" />


## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.

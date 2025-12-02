# Without-built-in-function-7


#include <stdio.h>


int str_length(char str[15]) {
    int i = 0;
    while (str[i] != '\0')
        i++;
    return i;
}


int str_compare(char s1[15], char s2[15]) {
    int i = 0;
    while (s1[i] != '\0' || s2[i] != '\0') {
        if (s1[i] != s2[i])
            return s1[i] - s2[i];
        i++;
    }
    return 0;
}


void str_copy(char dest[], char src[]) {
    int i = 0;
    while (src[i] != '\0') {
        dest[i] = src[i];
        i++;
    }
    dest[i] = '\0';
}


void str_concat(char s1[15], char s2[15]) {
    int i = 0, j = 0;

    while (s1[i] != '\0')
        i++;

    while (s2[j] != '\0') {
        s1[i] = s2[j];
        i++;
        j++;
    }
    s1[i] = '\0';
}

int main() {
    char str1[100], str2[100], result[100];
    int choice;

    while (1) {
        printf("\n-------- MENU --------\n");
        printf("1. Find Length of String\n");
        printf("2. Compare Two Strings\n");
        printf("3. Copy String\n");
        printf("4. Concatenate Strings\n");
        printf("5. Exit\n");
        printf("-----------------------\n");

        printf("Enter your choice: ");
        scanf("%d", &choice);
        getchar(); 
        switch (choice) {
            case 1:
                printf("Enter a string: ");
                scanf("%s", str1);
                printf("Length = %d\n", str_length(str1));
                break;

            case 2:
                printf("Enter first string: ");
                scanf(" %s", str1);
                printf("Enter second string: ");
                scanf(" %s", str2);

                if (str_compare(str1, str2) == 0)
                    printf("Strings are Equal\n");
                else
                    printf("Strings are NOT Equal\n");
                break;

            case 3:
                printf("Enter a string to copy: ");
                scanf(" %s", str1);

                str_copy(result, str1);
                printf("Copied String: %s\n", result);
                break;

            case 4:
                printf("Enter first string: ");
                scanf(" %s", str1);
                printf("Enter second string: ");
                scanf(" %s", str2);

                str_concat(str1, str2);
                printf("Concatenated String: %s\n", str1);
                break;

            case 5:
                printf("--------------- Thank You!-------------------\n");
                return 0;

            default:
                printf("Invalid Choice! Try Again.\n");
        }
    }

    return 0;
}


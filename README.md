# Atividade2_Aula-0108
A função deve retornar o endereço da posição do caractere lido, caso ocaracterece não exista na string a função deve retornar NULL. Na função main() solicite uma string e um caractere ao usuário e, utilizandoa função anterior, mostre na tela os caracteres da string que se encontram apartir do caractere lido.

#include <stdio.h>

char* find_character(const char* str, char character) {
    while (*str != '\0') {
        if (*str == character) {
            return (char*)str; // Cast para evitar warnings
        }
        str++;
    }
    return NULL;
}

int main() {
    char input_string[100];
    char search_character;
    
    // Solicita a string e o caractere ao usuário
    printf("Digite uma string: ");
    scanf("%99s", input_string); // Limita o tamanho da string para evitar estouro de buffer
    
    printf("Digite um caractere: ");
    scanf(" %c", &search_character); // Espaço antes do %c para ignorar espaços e quebras de linha

    // Chama a função para encontrar o caractere na string
    char* found_position = find_character(input_string, search_character);

    if (found_position != NULL) {
        // Mostra os caracteres da string a partir do caractere encontrado
        printf("Caracter encontrado! Resultado: %s\n", found_position);
    } else {
        printf("Caractere nao encontrado na string.\n");
    }

    return 0;
}

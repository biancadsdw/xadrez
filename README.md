#include <stdio.h>

void movimento_peca (int *p, int *m, char *d) { // Pointer porque o valor é alterado na função
    for (*p = 0; *p <= *m; (*p)++) {
        printf("%s\n", d);
    }
}
void movimento_bispo(int *bispo) {
    if (*bispo > 0) {
        printf("Direita, Cima\n");
    }
}

int main () {
    //TORRE
    printf("Movimento da torre:\n");
    int peca = 0;
    int torre = 5;
    movimento_peca (&peca, &torre, "Direita");

    // BISPO
    int bispo = 5;
    printf("Movimento do bispo:\n");
    for (int i = 0; i < bispo; bispo--) {
        movimento_bispo(&bispo);
    }

    // RAINHA
    int rainha = 8;
    printf("Movimento da rainha:\n");
    movimento_peca (&peca, &rainha, "Esquerda");
    
    // CAVALO
    printf("Movimento do cavalo:\n");
    for (int baixo = 0; baixo <= 2; baixo++) {
        if (baixo < 2) { // 
            printf("Cima\n");
        }
        for (int esquerda = 0; baixo == 2 && esquerda < 1; esquerda++) {
            printf("Direita\n");
        }
    }
    
    return 0;
}

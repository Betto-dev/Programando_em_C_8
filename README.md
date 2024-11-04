# Programando_em_C_8
Criando um sistema em C que pega 3 valores digitados e compara se os três acertaram na loteria, considerando que o numero da sorte é 35

Codigo 100% funcional

// Desenvolvedor.: Adalberto Fernnandes
// Sistema Versão.: v1.0

/*
Três amigos jogaram na loteria. Caso eles ganhem, o prêmio deve ser repartido proprocional-
mente ao valor que cada um deu para a realização da aposta. Faça um progrma que leia quanto
cada apoastador apastou, o valor do Prêmio e imprima quando cada um ganharia do prêmio com
base no valor investido.
*/ 

#include <stdio.h>
#include <stdlib.h>
#include <locale.h>

int main() {
    setlocale(LC_ALL, "Portuguese");  // Configuração de idioma, se necessário

    int amigo1, amigo2, amigo3;
    float aposta1, aposta2, aposta3;
    float total_aposta, total_premio;
    float premio = 5000.0;
    int num_sorte = 35;

    // Três amigos jogando na loteria.
    printf("Digite um numero de (1 - 35) para o amigo 1: ");
    scanf("%d", &amigo1);
    printf("Quanto você quer apostar nesse numero? ");
    scanf("%f", &aposta1);

    printf("Digite um numero de (1 - 35) para o amigo 2: ");
    scanf("%d", &amigo2);
    printf("Quanto você quer apostar nesse numero? ");
    scanf("%f", &aposta2);

    printf("Digite um numero de (1 - 35) para o amigo 3: ");
    scanf("%d", &amigo3);
    printf("Quanto você quer apostar nesse numero? ");
    scanf("%f", &aposta3);

    // Verifica se todos acertaram o número da sorte
    if (amigo1 == num_sorte && amigo2 == num_sorte && amigo3 == num_sorte) {
        printf("Opa!!! Parabéns, vocês acabaram de ganhar o prêmio no valor de R$%.2f!\n", premio);

        // Calcula o total apostado e divide o prêmio proporcionalmente
        total_aposta = aposta1 + aposta2 + aposta3;

        // Divide o prêmio proporcionalmente às apostas
        float divisao1 = (aposta1 / total_aposta) * premio;
        float divisao2 = (aposta2 / total_aposta) * premio;
        float divisao3 = (aposta3 / total_aposta) * premio;

        printf("Valor recebido pelo amigo 1: R$%.2f\n", divisao1);
        printf("Valor recebido pelo amigo 2: R$%.2f\n", divisao2);
        printf("Valor recebido pelo amigo 3: R$%.2f\n", divisao3);

    } else {
        printf("Desculpa, nenhum dos números escolhidos é o número da sorte!\n");
        printf("Fim do Jogo!\n");
    }

    return 0;
}

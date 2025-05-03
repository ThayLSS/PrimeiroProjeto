# ProjetoEmC
primeiro repositorio com codigo

#include <stdio.h>

// Exibe o card�pio da lanchonete
void exibirCardapio() {
    printf("======= CARD�PIO =======\n");
    printf("1 - X-Burguer     R$ 10.00\n");
    printf("2 - Batata Frita  R$ 6.00\n");
    printf("3 - Refrigerante  R$ 5.00\n");
    printf("========================\n");
}

// Fun��o para o cliente escolher o item do card�pio
int escolherItem() {
    
    int codigo;
    printf("Digite o c�digo do item desejado: ");
    scanf("%d", &codigo);
    return codigo;
}

// Fun��o para o cliente escolher a quantidade
int escolherQuantidade() {
    int quantidade;
    printf("Digite a quantidade desejada: ");
    scanf("%d", &quantidade);
    return quantidade;
}

// Calcula o valor total com base no c�digo e quantidade
float calcularValorTotal(int codigo, int quantidade) {
    float preco;
    switch(codigo) {
        case 1:
            preco = 10.0;
            break;
        case 2:
            preco = 6.0;
            break;
        case 3:
            preco = 5.0;
            break;
        default:
            printf("C�digo inv�lido! Valor total ser� R$ 0.00\n");
            preco = 0.0;
            break;
    }
    return preco * quantidade;
}

// Imprime o comprovante do pedido
void imprimirComprovante(int codigo, int quantidade, float total) {
    char produto[20];
    switch(codigo) {
        case 1:
            sprintf(produto, "X-Burguer");
            break;
        case 2:
            sprintf(produto, "Batata Frita");
            break;
        case 3:
            sprintf(produto, "Refrigerante");
            break;
        default:
            sprintf(produto, "Desconhecido");
            break;
    }

    printf("\n====== COMPROVANTE ======\n");
    printf("Item: %s\n", produto);
    printf("Quantidade: %d\n", quantidade);
    printf("Total a pagar: R$ %.2f\n", total);
    printf("=========================\n");
}



// Fun��o principal que organiza a l�gica do programa
int main() {
    exibirCardapio();

    int item = escolherItem();
    int qtd = escolherQuantidade();

    float total = calcularValorTotal(item, qtd);

    imprimirComprovante(item, qtd, total);

    return 0;
}

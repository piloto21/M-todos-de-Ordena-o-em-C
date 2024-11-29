#include <stdio.h>
int main(){
	
    int vetor[] = {5, 3, 8, 6, 2}; 
    int tamanho = 5; 
    int i, j, temp, chave, minIndex;
    

    printf("vetor original: ");
    for (i = 0; i < tamanho; i++) {
        printf("%d ", vetor[i]);
    }
    printf("\n");
    
    
    //----------------------------------------------------------------

    printf("\n--- Bubble Sort ---\n");
    int bubbleVetor[] = {5, 3, 8, 6, 2}; // copia o vetor para não modificar o original
    for (i = 0; i < tamanho - 1; i++) {
        for (j = 0; j < tamanho - i - 1; j++) {
        	
            // compara dois valores consecutivos no vetor
            if (bubbleVetor[j] > bubbleVetor[j + 1]) {
            	
                // os vetores então trocam de posição colocando o menor na frente
                temp = bubbleVetor[j];
                bubbleVetor[j] = bubbleVetor[j + 1];
                bubbleVetor[j + 1] = temp;
                
            }
        }
        
        // exibe cada mudança do vetor
        printf("passo %d: ", i + 1);
        for (j = 0; j < tamanho; j++) {
            printf("%d ", bubbleVetor[j]);
        }
        printf("\n");
        
    }

	//--------------------------------------------------------------

    printf("\n--- Insertion Sort ---\n");
    int insertionVetor[] = {5, 3, 8, 6, 2}; // copia o vetor para não modificar o original
    
    for (i = 1; i < tamanho; i++) {
        chave = insertionVetor[i]; // pega o valor atual para comparar
        j = i - 1;
        while (j >= 0 && insertionVetor[j] > chave) {
        	
            // os valores maiores que a chave são movidos uma vez para frente
            insertionVetor[j + 1] = insertionVetor[j];
            j--;
        }
        
        insertionVetor[j + 1] = chave; // coloca o valor da chave na posição correta

        // exibe cada mudança do vetor
        printf("passo %d: ", i);
        for (j = 0; j < tamanho; j++) {
            printf("%d ", insertionVetor[j]);
        }
        printf("\n");
        
    }

	//-----------------------------------------------------------------------------

    printf("\n--- Selection Sort ---\n");
    int selectionVetor[] = {5, 3, 8, 6, 2}; // copia o vetor para não modificar o original
    
    for (i = 0; i < tamanho - 1; i++) {
        minIndex = i;
        for (j = i + 1; j < tamanho; j++) {
        	
            // procura o menor valor dentro do vetor
            if (selectionVetor[j] < selectionVetor[minIndex]) {
                minIndex = j; // muda o menor valor atual
            }
        }
        // coloca o menor valor na posição correta
        temp = selectionVetor[minIndex];
        selectionVetor[minIndex] = selectionVetor[i];
        selectionVetor[i] = temp;

        // exibe cada mudança do vetor
        printf("passo %d: ", i + 1);
        for (j = 0; j < tamanho; j++) {
            printf("%d ", selectionVetor[j]);
        }
        printf("\n");
        
    }

    return 0;
    
    
}

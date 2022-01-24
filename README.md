# Cripto-simples
Programa simples de Criptografia

#include <stdio.h>
#include <stdlib.h>
#include <string.h>


int main (void)
{

FILE *arquivo;
    char texto[1000], linha[1000];
    int op, i;
    
    do {
        printf ("\n\t**** MENU CRIPTOGRAFICO ****");
        printf ("\n\n 1 - Criptografar texto");
        printf ("\n 2 - Descriptografar texto");
        printf ("\n 3 - Mostrar texto");
        printf ("\n 9 - Sair");
        printf ("\nDigite a opção desejada: ");
        scanf  ("%d", &op);
        
    
        if (op == 1)
        {
            printf("\n\t\tCRIPTOGRAFAR TEXTO!\n\n");
         
         arquivo = fopen("texto.txt","r");
        
         if (arquivo==NULL)
         {
            printf("Problema ao abrir arquivo\n\n");
            
         }
         
         strcpy(texto,"");
         
         while(fgets(linha,1000,arquivo)!=NULL)
         
         {
            strcat(texto,linha);
            
         }
         
         arquivo = fopen("texto.txt","w");
          for (int i = 0; texto[i]!='\0';i++)
         
         texto[i]=texto[i]+3; 
         fprintf(arquivo,"\n%s",texto);
         
         fclose(arquivo);
        }
        
        if (op == 2) 
        {
         
         printf("\n\t\tDESCRIPTOGRAFAR TEXTO!\n\n");
         
         arquivo = fopen("texto.txt","r");
        
         if (arquivo==NULL)
         {
            printf("Problema ao abrir arquivo\n\n");
            
         }
         
         strcpy(texto,"");
         
         while(fgets(linha,1000,arquivo)!=NULL)
         
         {
            strcat(texto,linha);
            
         }
         
         arquivo = fopen("texto.txt","w");
          for (int i = 0; texto[i]!='\0';i++)
         
         texto[i]=texto[i]-3; 
         fprintf(arquivo,"\n%s",texto);
         
         fclose(arquivo);
         
        }
        
        
        if (op == 3)
        {
         system ("cls");
         printf("\n\t\tMOSTRAR TEXTO!\n");
         
         arquivo = fopen("texto.txt","r");
        
         if (arquivo==NULL)
         {
            printf("Problema ao abrir arquivo\n\n");
            
         }
         
         strcpy(texto,"");
         while(fgets(linha,1000,arquivo)!=NULL)
         {
            strcat(texto,linha);
         }
         printf("\n%s\n",texto);
 
         fclose(arquivo);
        }
        
        if (op == 9)
        {
         system ("cls");
         printf("\n\t\tFinalizar operação");
        }
        
    } while (1 != 9);
    
    system("Pause");
return 0;

}

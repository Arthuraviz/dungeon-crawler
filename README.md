# dungeon-crawler


#include <stdio.h>

#include <conio.h> 

#include <stdlib.h>

#define SIZE 10

int main() {
  
  int op;
  
  printf("selecione uma opção\n");
  printf("\n");
  printf("1 jogar\n");
  printf("2 tutorial\n");
  printf("3 sair\n");
  printf("\n");
  printf("");
  scanf("%d", &op);
  if(op == 3){
	printf("obrigado por jogar tenha um bom dia ;D");
  }else if(op == 2){
  
  	printf("tutorial do jogo:\n");
  	printf("\n");
  	printf("objetivo:\n");
  	printf("seu objetivo e controlaro boneco '&' usando as teclas W,A,S,D ate a chave '@' e abrir a porta 'D' \n");
  	printf("para pegar a chave e necessaria ficar uma unidade abaixo dela e interagir usando a tecla 'i' \n");
  	printf("para abrir a porta 'D' e necessario interagir com a chave e interagir mais uma vez para entrar na porta = \n");
  	printf("\n");
  	printf("monstros e obstaculos:\n");
  	printf("o monstro nivel 1 'x' se move de maneira aleatoria para cima e para baixo ou para a direita e para esquerda \n");
  	printf("o monstro nivel 2 'Y' segue o jogador \n");
  	printf("os espinhos '#' ficam espalhados pelo do mapa \n ");
  	printf("se voce encostar em qualquer um deles voce morre \n");
  	printf("\n");
  	printf("itens de interacao no mapa:");
  	printf("o teletransporte '>' quando interagido leva o boneco & para o outro teleporte '<' e virse versa \n");
  	printf("o botão 'O' e ativado quando se fica encima dele \n");
  	printf("\n");
  	printf("fim");
  	
  }else if( op == 1){  

  char sl[SIZE][SIZE] = {
        {'*', '*', '*', '*', '*', 'D', '*', '*', '*', '*'},
        {'*', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', '*'},
        {'*', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', '*'},
        {'*', ' ', ' ', ' ', ' ', ' ', ' ', ' ', '@', '*'},
        {'*', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', '*'},
        {'*', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', '*'},
        {'*', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', '*'},
        {'*', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', '*'},
        {'*', ' ', ' ', ' ', ' ', '&', ' ', ' ', ' ', '*'},
        {'*', '*', '*', '*', '*', '*', '*', '*', '*', '*'}};
    
    int h = 5; 
    int y = 8; 
    char input;
    int i;
    int j;
    

    printf("Use as teclas W, A, S, D para mover o caractere '&'.\n");
    printf("Pressione 'q' para sair.\n");

    while (1) {
        system("cls"); 

        // Desenha o quadrado
        for ( i = 0; i < SIZE; i++) {
            for ( j = 0; j < SIZE; j++) {
                printf("%c", sl[i][j]);
            }
            printf("\n");
        }
    	
    	

       
        input = getch();

       
        switch (input) {
            case 'w':
                if (sl[y - 1][h] == ' ') {
                    sl[y][h] = ' ';
                    y--;
                }
                break;
            case 's':
                if (sl[y + 1][h] == ' ') {
                    sl[y][h] = ' ';
                    y++;
                }
                break;
            case 'a':
                if (sl[y][h - 1] == ' ') {
                    sl[y][h] = ' ';
                    h--;
                }
                break;
            case 'd':
                if (sl[y][h + 1] == ' ') {
                    sl[y][h] = ' ';
                    h++;
                }
                break;
            case 'i':
    if ( sl[3][7] == '&' || sl[2][8] == '&' || sl[4][8] == '&') {
        sl[3][8] = ' ';
        sl[0][5] = '=';
        
        break;
    } else if (sl[1][5] == '&' && sl[0][5] == '=') {
        system("cls");
        printf("\n");       
        printf("                    vitoria! \n");
        return 0;
    	}
    	
    
      
            default:
                printf("Tecla inválida!\n");
        }

       
        sl[y][h] = '&';

         
       
    }
  	
  
    return 0;
}}

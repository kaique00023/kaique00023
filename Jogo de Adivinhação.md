import random
import os

numero_secreto = random.randint(1,100)
pontos = 1000

def continuacao():
    while True:
        continuar = input('Você deseja continuar (S) Sim ou (N) Não?   ').upper()

        if (continuar == 'S' or continuar == 'N'):
            break
        
        else:
            print("\nResposta inválida. Por favor, digite 'S' para Sim ou 'N' para Não.")
    


    if (continuar == 'S'):
            main()

    else:
            os.system('clear')
            print('Progama finalizado.')

def escolher_dificuldade():
    print("Qual é o nivel de dificuldade que você quer? ")
    dificuldade = int(input("(1)Facil (2)Médio (3)Dificil: "))
    if (dificuldade == 1):
        return 20
    elif (dificuldade == 2):
        return 10
    else:
        return 5

def escolher_numero(total_de_tentativas):
    for rodada in range(1, total_de_tentativas + 1):
        print("********************************************")
        print("           Jogo do adivinha                 ")
        print("********************************************")
        print("Tentativas {} de {}".format(rodada, total_de_tentativas))
        chute_str = int(input("Digite o seu numero entre 1 e 100: \n"))

        if(chute_str < 1 or chute_str > 100):
            print("Você deve digitar um valor entre 1 e 100")
            continue

        acertou = chute_str == numero_secreto
        maior = chute_str > numero_secreto
        menor = chute_str < numero_secreto


        if (acertou):
            print("Parabens! Você acertou\n")
            break
        elif(maior):
            print("Você chutou mais alto\n")
        elif (menor):
            print("Você chutou mais baixo\n")
           
    else:
        print("Poxa, o numero da sorte era {} ".format(numero_secreto))

    print("Fim do jogo")
    
def main():
    os.system('clear')
    total_de_tentativas = escolher_dificuldade()
    escolher_numero(total_de_tentativas)
    continuacao()



if (__name__ == '__main__'):
    main()

# forcabol
import random
import time
palavras = ['futebol', 'flamengo', 'santos', 'gremio', 'corinthians', 'internaconal', 'vasco', 'palmeiras', 'fluminense', 'botafogo']
palavra_secreta = random.choice(palavras).lower()
letras_encontradas = []
tentativas = 6
chutes = []
jogador = 0
erros = 0

print('bem vindo ao jogo forcabol')
print('que é um jogo da forca com tema de futebol:)')
print('essas são as regras:')
print('''-  tente acertar utilizando apenas letras
-  acerte em 6 tentativas''')
print('vamos jogar?' )
jogar = input('sim/não ').strip().upper()
print()
if jogar in ('sim', 's', 'SIM', 'S' ):
    print('o jogo começou!!! você tem 6 chances para acertar a palavra secreta!!!')
    time.sleep(2)
    print()
    print('vou escolher uma palavra')
    time.sleep(2)
    print()
    print('escolhi a palavra!')
else:
    print('ok, jogamos outro dia então')
    exit()
print(f'a palavra tem {len(palavra_secreta)} letras')

def tabela(erros, palavra, letras_encontradas):
    if erros == 0:
        print()
        print("+------+")
        print("|      |")
        print("|       ")
        print("|       ")
        print("|       ")
        print("|       ")
        print(mostrar_letras_encontradas(letras_encontradas, palavra))
        print()

    elif erros == 1:
        print()
        print("+------+")
        print("|      |")
        print("|      @")
        print("|       ")
        print("|       ")
        print("|       ")
        print(mostrar_letras_encontradas(letras_encontradas, palavra))
        print()

    elif erros == 2:
        print()
        print("+------+")
        print("|      |")
        print("|      @")
        print("|      |")
        print("|      | ")
        print("|       ")
        print(mostrar_letras_encontradas(letras_encontradas, palavra))
        print()

    elif erros == 3:
        print()
        print("+------+")
        print("|      |")
        print("|      @")
        print("|      |\\")
        print("|      | ")
        print("|       ")
        print(mostrar_letras_encontradas(letras_encontradas, palavra))
        print()

    elif erros == 4:
        print()
        print("+------+")
        print("|      |")
        print("|      @")
        print("|     /|\\")
        print("|      | ")
        print("|       ")
        print(mostrar_letras_encontradas(letras_encontradas, palavra))
        print()

    elif erros == 5:
        print()
        print("+------+")
        print("|      |")
        print("|      @")
        print("|     /|\\")
        print("|      | ")
        print("|       \\")
        print(mostrar_letras_encontradas(letras_encontradas, palavra))
        print()

    elif erros == 6:
        print()
        print("+------+")
        print("|      |")
        print("|      @")
        print("|     /|\\")
        print("|      | ")
        print("|     / \\")
        print(mostrar_letras_encontradas(letras_encontradas, palavra))
        print()

def mostrar_letras_encontradas(letras_encontradas, palavra_secreta):
    resultado = ''
    for caracter in palavra_secreta:
        if lista_possui_letra(letras_encontradas, caracter):
            resultado += caracter
        else:
            resultado += ' _ '
    return resultado
            
def pedir_letra():
    while True:
        letra = input('digite uma letra: ')
        if len(letra) > 1:
            print('digite apenas uma letra companheiro')
        else:
            return letra

def acertou(letra, palavra, palavra_secreta):
    if letra in palavra_secreta:
        print('você acertou a letra! ')
        return True
    else:
        print('você errou, tente outra vez! ')
        return False

def lista_possui_letra(lista, letra):
    return letra in lista

jogo_acabou = False
while not jogo_acabou:
    if erros == 6:
        print('você perdeu!!! mais sorte na próxima vez')
    else:
        while True:
            letra = pedir_letra()
            if lista_possui_letra(letras_encontradas, letra):
                print('você já digitou essa letra, digite outra: ')
            else:
                break

        if lista_possui_letra(palavra_secreta, letra):
                letras_encontradas.append(letra)
                print('PARABÉNSSSSSS!!!, VOCÊ ACERTOU')
        else:
            erros += 1
            print('ERROUUUUU!!!')
    tabela(erros, palavra_secreta, letras_encontradas)
    
    
    


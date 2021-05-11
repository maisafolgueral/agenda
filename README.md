# agenda.py
Programa que simula uma agenda com os nomes de todos os seus amigos em Python.
amigo = [] #criando lista vazia e global

def menu():
    print('Escolha uma opção: ')
    print('(1) Cadastrar um amigo (no final da lista)')
    print('(2) Mostrar os nomes de todos os amigos')
    print('(3) Cadastrar um amigo (no início da lista)')
    print('(4) Remover um nome')
    print('(5) Substituir um nome')
    print('(6) Mostrar o número total de amigos cadastrados')
    print('(7) Colocar os nomes dos amigos em ordem alfabética')
    print('(8) Sair do programa')
    op = int(input())
    while op<1 or op>8:   #validação
        op = int(input())
    return op

def cadastrar():
    nome = input('Nome: ')
    amigo.append(nome)

def cadastrar_inicio():
    nome = input('Nome: ')
    amigo.insert(0, nome)

def mostrar():
    print('Amigos Cadastrados')
    for x in amigo:
        print(x)

def remover():
    nome = input('Qual o nome deve ser removido?')
    if nome in amigo:
        i = amigo.index(nome)
        del amigo[i]

def substituir():
    nome= input('Nome a substituir: ')
    if nome in amigo:
        nome_novo = input('Nome novo: ')
        i = amigo.index(nome)
        amigo[i] = nome_novo
    else:
        print('Amigo não está cadastrado')

def total():
    return len(amigo)

def organizar():
    amigo.sort()
    mostrar()
    
def main():
    while True:
        op = menu()
        if op == 8:
            break
        if op == 1:
            cadastrar()
        elif op == 2:
            mostrar()
        elif op == 3:
            cadastrar_inicio()
        elif op == 4:
            remover()
        elif op == 5:
            substituir()
        elif op == 6:
            print(f'Total de amigos cadastrados: {total()}')
        elif op == 7:
            organizar()

main()

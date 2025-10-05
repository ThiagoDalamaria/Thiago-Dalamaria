from datetime import datetime         

pessoas = [ ]

def mostrar_menu():
    print("1. Cadastrar novo cliente ")
    print("2. Consultar lista ")                # Menu informativo para quem vai usar. 
    print("3. Remover Cadastro ")           
    print("4. Sair ")


def cadastra_clientes():
    while True: # Cadastro do nome com tratamento para não receber números ou simbolos. 
        nome = input("Digite seu primeiro nome: ").strip().capitalize()
        if all(parte.isalpha() for parte in nome.split()):         
            nome = nome.title()        
            break
        else:
            print("=" * largura)
            print("⚠️  Digite apenas letras, sem números ou simbolos! ")

    while True:
        try:             # O mesmo com a idade.
            idade = int(input("Digite sua idade: "))
            if idade < 0:
                print("=" * largura)
                print("⚠️  A idade não pode ser negativa. ")
            elif idade > 117:
                print("=" * largura)
                print("⚠️  A idade Invalida! ")
            else:
                break
        except ValueError:
            print("=" * largura)
            print("⚠️  Digite apenas Números!")

    sexo = " "
    while sexo not in "MF":                 
        sexo = input("Digite seu seu sexo [M/F] ").strip().upper()[0]

    cliente = {"Nome": nome, "Idade": idade, "Sexo": sexo}
    pessoas.append(cliente)
    print(f"✅ Cliente {nome} foi cadastrado com sucesso.")         
    print("=" *largura)
def consultar_lista():
    if not pessoas:
        print("❌ Não á nenhum clientes cadastrado. ")

    else:
        print("\n Lista de clientes: ")
        for i, cliente in enumerate(pessoas,1):
            print(f"{i}. Nome: {cliente ['Nome']} | Idade: {cliente ['Idade']} | Sexo: {cliente ['Sexo']}")    
            print("-" * largura)
def remover_cadastro():
    if not pessoas:
        print("❌ Nenhum cadastro para remover. ")
        return
    
    nome = input("Digite o nome do cliente para remover: ").strip().capitalize()
    encontrado = False

    for cliente in pessoas:
        if cliente["Nome"] == nome:
            pessoas.remove(cliente)
            print(f"🚮 Cadastro {nome} foi removido com sucesso! ")
            encontrado = True
            print("=" * largura)
            break

        if not encontrado:
            print(f"⚠️ Cliente {nome} não foi encontrado. ")



# === Console do Programa === 
largura = 60
agora = datetime.now().strftime("%d/%m%Y %H:%M")

print("=" * largura)
print(f"{'Cadastro de Clienete':<30}{agora:>30}")
print("=" * largura)


while True:
    mostrar_menu()
    escolha = input("Escolhar uma opção: ").strip()

    if escolha == "1":
        cadastra_clientes()
    elif escolha == "2":
        consultar_lista()
    elif escolha == "3":
        remover_cadastro()
    elif escolha == "4":
        break
    else:
        print("⚠️ Opção invalidade, tente novamente! ")

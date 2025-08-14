# Lista de Tarefas Simples

tarefas = []

def mostrar_tarefas():
    if not tarefas:
        print("\nNenhuma tarefa adicionada ainda.")
    else:
        print("\n--- Lista de Tarefas ---")
        for i, tarefa in enumerate(tarefas, 1):
            print(f"{i}. {tarefa}")

def adicionar_tarefa():
    tarefa = input("\nDigite a nova tarefa: ")
    tarefas.append(tarefa)
    print("✅ Tarefa adicionada!")

def remover_tarefa():
    mostrar_tarefas()
    try:
        num = int(input("\nDigite o número da tarefa para remover: "))
        if 1 <= num <= len(tarefas):
            removida = tarefas.pop(num - 1)
            print(f"❌ Tarefa '{removida}' removida!")
        else:
            print("Número inválido!")
    except ValueError:
        print("Digite um número válido!")

def menu():
    while True:
        print("\n📌 Menu:")
        print("1 - Mostrar tarefas")
        print("2 - Adicionar tarefa")
        print("3 - Remover tarefa")
        print("4 - Sair")

        opcao = input("Escolha: ")

        if opcao == "1":
            mostrar_tarefas()
        elif opcao == "2":
            adicionar_tarefa()
        elif opcao == "3":
            remover_tarefa()
        elif opcao == "4":
            print("Até mais! 👋")
            break
        else:
            print("Opção inválida!")

if __name__ == "__main__":
    menu()

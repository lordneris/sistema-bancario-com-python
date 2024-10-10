# 💰 Sistema Bancário Simples em Python

Este programa em Python simula um sistema bancário simples onde você pode realizar operações de depósito, saque e verificação de extrato.

## 📋 Menu de Opções

```plaintext
    [1] Depositar
    [2] Sacar
    [3] Extrato
    [0] Sair
🏦 Funcionalidades
Depositar: Adicione fundos à sua conta.

Sacar: Retire fundos da sua conta, respeitando o limite e o número máximo de saques diários.

Extrato: Veja todas as transações realizadas e o saldo atual.

Sair: Encerre o programa.

🧮 Variáveis Principais
saldo: Armazena o saldo atual da conta (inicialmente R$ 0).

limite: Limite máximo para saques (R$ 1000).

extrato: Histórico de transações.

numero_saques: Contador de saques realizados.

LIMITE_SAQUES: Número máximo de saques permitidos por dia (3).

🚀 Loop Principal
O programa entra em um loop contínuo até que a opção de sair seja selecionada (opcao == "0"). As opções disponíveis são:

1️⃣ Depositar
Solicita o valor do depósito.

Adiciona o valor ao saldo se for positivo.

Adiciona a transação ao extrato.

2️⃣ Sacar
Solicita o valor do saque.

Verifica se o saldo é suficiente.

Verifica se o valor não excede o limite.

Verifica se o número máximo de saques foi atingido.

Deduz o valor do saldo e adiciona ao extrato se todas as condições forem satisfeitas.

3️⃣ Extrato
Exibe todas as transações realizadas.

Mostra o saldo atual.

0️⃣ Sair
Encerra o programa.

📝 Exemplo de Código

menu = """
    [1] Depositar
    [2] Sacar
    [3] Extrato
    [0] Sair
=> """

saldo = 0
limite = 1000
extrato = ""
numero_saques = 0
LIMITE_SAQUES = 3

while True:
    opcao = input(menu)

    if opcao == "1":
        valor = float(input("Informe o valor do depósito: "))

        if valor > 0:
            saldo += valor
            extrato += f"Deposito: R$ {valor:.2f} \n"

        else:
            print("Operação falhou! O valor informado é inválido.")

    elif opcao == "2":
        valor = float(input("Informe o valor do saque: "))

        excedeu_saldo = valor > saldo
        excedeu_limite = valor > limite
        excedeu_saques = numero_saques >= LIMITE_SAQUES

        if excedeu_saldo:
            print(f"Operação falhou! Você não tem saldo suficiente. Seu saldo atual é de R$ {saldo:.2f}")
        
        elif excedeu_limite:
            print(f"Operação falhou! O valor do saque excede o limite de: R$ {limite} por operação.")

        elif excedeu_saques:
            print(f"Operação falhou! Número máximo de {numero_saques} saques foi excedido!")

        elif valor > 0:
            saldo -= valor
            extrato += f"Saque: R$ {valor:.2f} \n"
            numero_saques += 1

        else:
            print("Operação falhou! O valor informado é inválido.")

    elif opcao == "3":
        print("\n====================== EXTRATO ====================")
        print("Não foram realizadas movimentações." if not extrato else extrato)
        print(f"\nSaldo: R$ {saldo:.2f}")
        print("=====================================================")

    elif opcao == "0":
        break

    else:
        print("Operação inválida, por favor selecione novamente a operação desejada.")

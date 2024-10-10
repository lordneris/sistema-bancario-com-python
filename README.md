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


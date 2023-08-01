import random

def jogo_pedra_papel_tesoura(escolha_usuario):
    opcoes = ['pedra', 'papel', 'tesoura']
    escolha_computador = random.choice(opcoes)

    print(f"Você escolheu: {escolha_usuario}")
    print(f"Computador escolheu: {escolha_computador}")

    if escolha_usuario == escolha_computador:
        return "Empate!"
    elif (
        (escolha_usuario == "pedra" and escolha_computador == "tesoura")
        or (escolha_usuario == "tesoura" and escolha_computador == "papel")
        or (escolha_usuario == "papel" and escolha_computador == "pedra")
    ):
        return "Você ganhou!"
    else:
        return "Você perdeu!"

def main():
    print("Bem-vindo ao Jogo Pedra, Papel e Tesoura!")

    while True:
        escolha_usuario = input(
            "Escolha a sua jogada (pedra, papel ou tesoura) ou digite 'sair' para encerrar o jogo: "
        ).lower()

        if escolha_usuario == "sair":
            break

        if escolha_usuario not in ["pedra", "papel", "tesoura"]:
            print("Opção inválida. Escolha novamente.")
            continue

        resultado = jogo_pedra_papel_tesoura(escolha_usuario)
        print(resultado)

if __name__ == "__main__":
    main()

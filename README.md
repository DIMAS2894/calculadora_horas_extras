# calculadora_horas_extrasdef calcular_valor_hora(salario_mensal, horas_mensais):
    return salario_mensal / horas_mensais

def calcular_horas_extras(hora_base, horas_uteis, horas_sabado, horas_domingo_feriado):
    valor_uteis = hora_base * 1.5 * horas_uteis
    valor_sabado = hora_base * 1.75 * horas_sabado
    valor_domingo = hora_base * 1.95 * horas_domingo_feriado
    total = valor_uteis + valor_sabado + valor_domingo
    return total

def main():
    print("💼 Calculadora de Horas Extras")

    try:
        escolha = input("Você quer calcular a hora base a partir do salário? (s/n): ").lower()

        if escolha == 's':
            salario = float(input("Informe seu salário mensal (R$): "))
            horas_mes = float(input("Informe a carga horária mensal (ex: 220): "))
            hora_base = calcular_valor_hora(salario, horas_mes)
            print(f"Valor da hora calculado: R$ {hora_base:.2f}")
        else:
            hora_base = float(input("Digite o valor da hora base (R$): "))

        horas_uteis = float(input("Horas extras em dias úteis: "))
        horas_sabado = float(input("Horas extras no sábado: "))
        horas_domingo_feriado = float(input("Horas extras no domingo/feriado: "))

        total = calcular_horas_extras(hora_base, horas_uteis, horas_sabado, horas_domingo_feriado)

        print(f"\n💰 Total a receber de horas extras: R$ {total:.2f}")

    except ValueError:
        print("⚠️ Por favor, insira apenas números válidos.")

if __name__ == "__main__":
    main()

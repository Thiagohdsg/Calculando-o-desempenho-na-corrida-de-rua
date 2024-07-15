# Calculando-o-desempenho-na-corrida-de-rua

print("Digite (ou copie e cole) os dados do seu GPS linha por linha e termine com a linha 000:")

batimento_max = 0
tempo_total = 0
distancia_total = 0

dados = input()
posicao_inicial = int(dados) // 1000

while dados != "000":
    dados = int(dados)
    posicao = dados // 1000
    batimento = dados % 1000


    if batimento > batimento_max:
        batimento_max = batimento

    tempo_total = tempo_total + 1
    distancia_total = (posicao - posicao_inicial)

    dados = input()

idade = 220 - batimento_max
print(f"Sua idade de aptidão física é: {idade}")


velocidade_media = distancia_total / (tempo_total-1)
if velocidade_media >= 4:
        print("Seu pelotão é: QUÊNIA")
else:
    if velocidade_media >= 2:
            print("Seu pelotão é: AZUL")
    elif velocidade_media < 2:
            print("Seu pelotão é: BRANCO")

soma = 1
i = 2
while i * i <= batimento_max:
    if batimento_max % i == 0:
        soma += i
        if i != batimento_max // i:
            soma += batimento_max // i
    i += 1

if soma > batimento_max:
    print("Parabéns! Você terá desconto na inscrição da prova!")

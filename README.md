#Ejercicio 1

medicamentos = 60000
despacho = 8000


edad = int(input("Ingrese su edad: "))
tramo = input("Digite su tramo correspondiente (A, B, C o D): ")


descuento_medicamentos = 0

if edad <= 30:
    if tramo == "A" or tramo == "B":
        descuento_medicamentos = 0.18
    else:
        descuento_medicamentos = 0.12

elif edad >= 31 and edad <= 60:
    if tramo == "A" or tramo == "B":
        descuento_medicamentos = 0.12
    else:
        descuento_medicamentos = 0.08
elif edad > 60: 
    descuento_medicamentos = 0




# Calcular valor medicamentos
valor_medicamentos = medicamentos - (medicamentos * descuento_medicamentos)

# Descuento despacho
descuento_despacho = 0

if tramo == "A" or tramo == "B":
    descuento_despacho = descuento_despacho + 0.10

    if edad >= 55:
        descuento_despacho = descuento_despacho + 0.05

# Calcular despacho
valor_despacho = despacho - (despacho * descuento_despacho)

# Mostrar resultados
print("El valor de medicamentos corresponde a:", int(valor_medicamentos))
print("El valor del despacho corresponde a:", int(valor_despacho))


#EJERCICIO2
from random import randint

while True:
    try:
    
        num1 = int(input("Ingrese un numero minimo: "))
        num2 = int(input("Ingrese un numero maximo: "))
        if num1 > num2:
            print("Por favor, que el numero minimo se menor al maximo")
            continue
    except ValueError:
        print("Por favor, que sean numeros enteros")
        continue
    break


numero = randint(num1, num2)

print (numero)

# para que sea par
if numero % 2 != 0:
    if numero + 1 <= num2:
        numero = numero + 1
    else:
        numero = numero - 1
print (numero)
while True:
# Primer intento
        intento1 = int(input("¿Puedes adivinar? ¡Intentalo!: "))

        if intento1 == numero:
            print("¡Felicitaciones!, adivinaste en el primer intento >.<")
            break

        else:

            if intento1 < numero:
                print("Frio...el numero que buscas es mayor.")
            else:
                print("¡Te pasaste! El número es menor.")

        # Segundo intento
        intento2 = int(input("Vuelve a intentarlo: "))

        if intento2 == numero:
            print("¡Crack! adivinaste en tu segundo intento.")
            break

        else:

            if intento2 < numero:
             print("Frio...el numero que buscas es mayor.")
            else:
                 print("¡Casi!.. El número es menor.")

        # Pista
        distancia1 = abs(numero - intento1)
        distancia2 = abs(numero - intento2)

        print("Aqui va una ayudita ¿Si?:")

        if distancia1 < distancia2:
            print("El número que buscas está más cerca de", intento1, "que de", intento2)
        else:
            print("El número que buscas está más cerca de", intento2, "que de", intento1)

        # Tercer intento
        intento3 = int(input("Ultima oportunidad...¡juegatela!:"))

        if intento3 == numero:
            print("Felicitaciones !lo lograste!.")
            break
        else:
            print("Fin del juego  X.X")
            print("El número secreto era...", numero)
            break

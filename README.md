# Proyecto Modulo 2 - Logica de bifurcacion
# Autor: Ricardo Llera

def evaluar_palabra():
    print("\n--- Evaluacion de longitud de palabra ---")
    intentos = []

    while True:
        palabra = input("Escribe una palabra (4 a 8 letras): ").strip()

        if palabra == "":
            print("No puedes dejar el campo vacio, intenta otra vez.")
            continue

        intentos.append(palabra)
        n = len(palabra)

        if n < 4:
            print(f"Hacen falta letras. '{palabra}' solo tiene {n}. Intenta de nuevo.")
        elif n > 8:
            print(f"Sobran letras. '{palabra}' tiene {n}. Intenta de nuevo.")
        else:
            print(f"Palabra correcta: '{palabra}' tiene {n} letras.")
            print("Palabras intentadas:", intentos)
            break


def evaluar_cuadrante():
    print("\n--- Ubicacion en el plano cartesiano ---")
    cuadrantes = ("Cuadrante I", "Cuadrante II", "Cuadrante III", "Cuadrante IV")

    while True:
        try:
            x = float(input("Ingresa la coordenada X: "))
            y = float(input("Ingresa la coordenada Y: "))

            # Validar que no sea cero para no quedar sobre los ejes
            if x == 0 or y == 0:
                print("Error: Las coordenadas no pueden ser 0. Intenta de nuevo.")
                continue

            if x > 0 and y > 0:
                resultado = cuadrantes[0]
            elif x < 0 and y > 0:
                resultado = cuadrantes[1]
            elif x < 0 and y < 0:
                resultado = cuadrantes[2]
            else:
                resultado = cuadrantes[3]

            print(f"El punto ({x}, {y}) esta en el {resultado}.")
            break

        except ValueError:
            print("Error: Solo se aceptan numeros. Intenta de nuevo.")


def main():
    while True:
        print("\n--- MENU PRINCIPAL ---")
        print("1. Validar longitud de palabra")
        print("2. Calcular cuadrante cartesiano")
        print("3. Ejecutar ambos ejercicios")
        print("4. Salir")

        opcion = input("Elige una opcion (1-4): ").strip()

        if opcion == "1":
            evaluar_palabra()
        elif opcion == "2":
            evaluar_cuadrante()
        elif opcion == "3":
            evaluar_palabra()
            evaluar_cuadrante()
        elif opcion == "4":
            print("Programa terminado.")
            break
        else:
            print("Opcion invalida, elige del 1 al 4.")


if __name__ == "__main__":
    main()

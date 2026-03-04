# Calculadora_Inteligente
Una calculadora hecha a partir de lenguaje Python, que es capaz de resolver ecuaciones básicas como: sumas, restas, multiplicación, división, etc. Es un proyecto hecho a partir del aprendizaje básico de programación, tiene como fin impulsar a entender como funciona y que tan divertido puede llegar a ser el mundo cibernético que no hay limites.
import os
import math

class CalculadoraCompleta:
    def limpiar(self):
        os.system('cls' if os.name == 'nt' else 'clear')
    
    def banner(self):
        self.limpiar()
        print("=== CALCULADORA COMPLETA ===")
        print("1. Suma (+)")
        print("2. Resta (-)") 
        print("3. Multiplicación (*)")
        print("4. División (/)")
        print("5. Ecuación lineal (ax + b = 0)")
        print("6. Ecuación cuadrática (ax² + bx + c = 0)")
        print("7. Salir")
        print("=" * 35)
    
    def suma(self):
        a = float(input("Primer número: "))
        b = float(input("Segundo número: "))
        resultado = a + b
        print(f"{a} + {b} = {resultado}")
    
    def resta(self):
        a = float(input("Primer número: "))
        b = float(input("Segundo número: "))
        resultado = a - b
        print(f"{a} - {b} = {resultado}")
    
    def multiplicacion(self):
        a = float(input("Primer número: "))
        b = float(input("Segundo número: "))
        resultado = a * b
        print(f"{a} × {b} = {resultado}")
    
    def division(self):
        a = float(input("Primer número: "))
        b = float(input("Segundo número: "))
        if b == 0:
            print("¡Error! No se puede dividir por cero")
        else:
            resultado = a / b
            print(f"{a} ÷ {b} = {resultado}")
    
    def lineal(self):
        print("Ecuación: ax + b = 0")
        a = float(input("a: "))
        b = float(input("b: "))
        if a == 0:
            print("No es una ecuación lineal válida")
        else:
            x = -b / a
            print(f"Solución: x = {x}")
    
    def cuadratica(self):
        print("Ecuación: ax² + bx + c = 0")
        a = float(input("a: "))
        b = float(input("b: "))
        c = float(input("c: "))
        
        disc = b*b - 4*a*c
        if disc > 0:
            x1 = (-b + math.sqrt(disc)) / (2*a)
            x2 = (-b - math.sqrt(disc)) / (2*a)
            print(f"Soluciones: x1 = {x1}, x2 = {x2}")
        elif disc == 0:
            x = -b / (2*a)
            print(f"Solución única: x = {x}")
        else:
            print("No hay soluciones reales")
    
    def run(self):
        while True:
            self.banner()
            opcion = input("Elige opción (1-7): ")
            
            if opcion == '1':
                self.suma()
            elif opcion == '2':
                self.resta()
            elif opcion == '3':
                self.multiplicacion()
            elif opcion == '4':
                self.division()
            elif opcion == '5':
                self.lineal()
            elif opcion == '6':
                self.cuadratica()
            elif opcion == '7':
                print("¡Gracias por usar la calculadora!")
                break
            else:
                print("Opción inválida")
            
            input("\nPresiona Enter para continuar...")

if __name__ == "__main__":
    calc = CalculadoraCompleta()
    calc.run()

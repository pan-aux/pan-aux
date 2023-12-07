- 👋 Hi, I’m @pan-aux
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
pan-aux/pan-aux is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

def MenuPrincipal():
    op = 0
    dict_pizza = {}
    while True:
        
        try:
            print("   MENU PRINCIPAL  ")
            print("1. Registrar pizza")
            print("2. Listar todas las pizzas (listar todos los datos (Nº Venta, tipo masa, tamaño y total)")
            print("3. Eliminar solo las pizzas Medianas (Al ingresar borra todas las ventas pizzas medianas)")
            print("4. Eliminar solo las pizzas Familiar (Al ingresar borra todas las ventas pizzas familiar)")
            print("5. Listar estadística")
            print("6. Buscar Venta (Al ingresar el número de venta, (listará todos los datos (<po masa, tamaño y total))")
            print("7. Salir")
        
            op = int(input("ingrese la opcion del menu: "))
            assert op >= 1 and op <= 7
            if op == 1:
                dict_pizza = registrar()
            elif op == 2:
                listarTodo(dict_pizza)
            elif op == 3:
                eliminarPizzaMediana(dict_pizza)
            elif op == 4:
                eliminarPizzaFamiliar(dict_pizza)
            elif op == 5:
                estadisica(dict_pizza)
            elif op == 6:
                buscar()
            elif op == 7:
                print("ADIOS")
                break
        except ValueError:
            ("debe ser un numero")
        except AssertionError:
            ("opcion no valida")
        
def digitarventa():
    while True:
        try:
            venta = int(input("Ingrese el número de venta (entre 1 y 100): "))
            assert venta>= 1 and venta<= 100
            return venta 
        except AssertionError:
            print("l numero de venta debe ser un entre 1 y 100")

def  registrar():
    diccionario = {}
    venta = digitarventa()
    tamaño = TamañoDepizza()
    tipo = TipoDepizza()
    total = tamaño[1] + tipo[1]
    diccionario[venta] = [tamaño, tipo,total]
    return diccionario

    """

    {1: [("mediana", 6000), ("ala piedra", 7500), 13500],  3: [("mediana", 6000), ("ala piedra", 7500), 13500]}
    
    diccionario[1] ---> [("mediana", 6000), ("ala piedra", 7500)]
    t = diccionario[1]
    print(t[0]) --> (mediana, 6000)
    print(t[0][1]) --> 6000
    print(t[1][0]) --->
    print(diccionario[1][0][0])
    print(diccionario[1][2]) -->

    for k in diccionario.keys()
        if diccionario[k][0][0] == "mediana":
            borrar

    
    """
    return diccionario

def TamañoDepizza():
    
    dict_tamaño ={1: ("normal", 6000), 2: ("a la piedra" ,75000)}
    while True:
        try:
            tamaño = int(input("seleccione el  tamaño  de la masa  (1. Normal($6.000), 2. familiar($7.500))."))
            assert tamaño == 1 or tamaño == 2
            return dict_tamaño[tamaño]
        except AssertionError:
            print("la opcion debe ser entre 1 o 2")
    
def TipoDepizza():
    
    dict_tipo ={1: ("mediana", 6000), 2: ("familiar" ,8000)}
    while True:
        try:
            tipo = int(input("seleccione el tipo de masa  (1. Normal($6.000), 2. a la piedra ($7.500))."))
            assert tipo == 1 or tipo == 2
            return dict_tipo[tipo]
        except AssertionError:
            print("la opcion debe ser entre 1 o 2")
    
def  listarTodo(diccionario):
    print("   LISTA TODAS LAS PIZZAS   ")
    try:
        assert len(diccionario) > 0
        for k in diccionario.keys():
            
            print(f" Tamaño : {diccionario[k][1][0]}")
            print(f" Tipo: {diccionario[k][1][0]}")
            print(f" total: {diccionario[k][2]}")
            print()
    except AssertionError:
        print("No existen registro disponibles")
        
def eliminarPizzaMediana():
    pass
def eliminarPizzaFamiliar():
    pass
def estadisica(diccionario):
    print("   ESTADISTICA  ")
    sumaprecio = 0
    try:
        assert len(diccionario) > 0
        for k in diccionario.keys():
            print(f"La cantidad es : {len(diccionario)}")
            sumaprecio = sumaprecio + diccionario [k][2]
            print(f"la suma del precio es : {sumaprecio}")
    except AssertionError:
        print("no hay datos para sacar las estadisticas")

def buscar():
    pass


MenuPrincipal()

# EDES-diagrama-de-estados

    @startuml

    [*] --> Cerrado
    Cerrado --> Abriendo
    Abriendo --> Abierto : [posición = posición_final] / Abrir puerta
    Abierto --> Cerrando : [temporizador = tiempo_limite] / Comenzar a cerrar puerta
    Cerrando --> Cerrado : [posición = posición_inicial] / Cerrar puerta
    Abierto --> Abierto : Si detecta a una persona
    Abriendo -> Abriendo
    Cerrando -> Cerrando

    Cerrado : Entry / 
    Cerrado : Do / Comprueba la presencia de personas cercanas
    Cerrado : Exit / 

    Abriendo : posición = Int
    Abriendo : Entry / Comprueba la posición de las puertas 
    Abriendo : Do / Incrementa su posición
    Abriendo : Exit / 



    Abierto : temporizador = 0
    Abierto : tiempo_limite = 10
    Abierto : Entry / Comienza el contador
    Abierto : Do / Incrementa 1 el contador
    Abierto : Exit / Comienza a cerrar las puertas

    Cerrando : posición = Int
    Cerrando : Entry / Comprueba la posición de las puertas
    Cerrando : Do / Disminuye su posición
    Cerrando : Exit / 


    @enduml
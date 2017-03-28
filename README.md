import random

def confirmarTipo(y):
    if y=='J' or y=='Q' or y=='K':
        return 10
    elif y=='A':
        return 1
    else:
        return y

def contarCartas(x):
    
    print "acumulado: ",confirmarTipo(x)
    
    if confirmarTipo(x)==21:
        return "Ganaste"
    elif confirmarTipo(x)>21:
        return "Perdiste"
    elif confirmarTipo(x)<21:
        return contarCartas(confirmarTipo(x)+confirmarTipo(random.choice(['A',2,3,4,5,6,7,8,9,'J','Q','K'])))

def empezarJuego():
    if(input("¿Desea tomar una carta? \n1.si \n2.no" )==1):
        return contarCartas(random.choice(['A',2,3,4,5,6,7,8,9,'J','Q','K']))
    else:
        return "Gano la casa"
try: 
    print "Inicio del juego ... Iniciamos con la carta: ", contarCartas(random.choice(['A',2,3,4,5,6,7,8,9,'J','Q','K']))
    print empezarJuego()
except:
    print "Algo salio mal"

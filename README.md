

MAX_IDADE=120
MIN_IDADE=0
NUM_CHAR=50

#def __func_especial():


class IdadeError(Exception):
    def __init__(self, msg):
        self.__dado = msg
        
    def __str__(self):
        return "IdadeError:" + self.__dado
    
class NomeError(Exception):
    def __init__(self, msg):
        self.__dado = msg
        
    def __str__(self):
        return "NomeError:" + self.__dado

class Pessoa:
    MAX_IDADE=120
    MIN_IDADE=0
    def __init__(self, nome, idade):
        self.nome = nome
        self.idade = idade
    # com anotação o getter precisa vir antes
    @property    
    def idade(self):
        print("---get---")
        return self.__idade
    
    @idade.setter
    def idade(self, valor):
        print("---set---")
        if valor > MIN_IDADE and valor < MAX_IDADE:
            self.__idade = valor
        else:
            raise IdadeError("Valor do atributo idade é inválido!")
    
    @idade.deleter
    def idade(self):
        print("---del---")
        del self.__idade
        
        
    @property
    def nome(self):
        print("---get---")
        return self.__nome
    
    @nome.setter
    def nome(self, valor):
        print("---set---")
        if len(valor) < 50:
            self.__nome = valor
        else:
            raise NomeError("Valor do atributo nome maior que 50 caracteres!")
   
    @nome.deleter
    def nome(self):
        print("---del---")
        del self.__nome  
        
    def __str__(self):
        return self.nome + " possui " + str(self.idade) + " anos!"
    
    def __del__(self):
        print("DEL")
        del self

#if __name__ =="__main__":
    #__func_especial()


    ---------------------------TIPOS DE APP------------------------------------------

    from humano import *

while True:
    try:
        print('idade Maxima', MAX_IDADE)
        nome= input ("digite a seu nome: ")
        idade= int (input("digite a sua idade"))
        P1 = Pessoa(nome, idade)
        print(P1)
        del P1
        break

    except IdadeError as e:
        print("digite novamente seus dados")
        print (e) 

    except NomeError as e:
        print("digite novamente seus dados")
        print (e) 
-------------------------------------------------------------------------------------------

from humano import Pessoa
from humano import NomeError
from humano import IdadeError

while True:
    try:
        #print('idade Maxima', MAX_IDADE)
        nome= input ("digite a seu nome: ")
        idade= int (input("digite a sua idade"))
        P1 = Pessoa(nome, idade)
        print(P1)
        del P1
        break

    except IdadeError as e:
        print("digite novamente seus dados")
        print (e) 

    except NomeError as e:
        print("digite novamente seus dados")
        print (e) 

-------------------------------------------------------------------

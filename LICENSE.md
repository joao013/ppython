# coding: utf-8
import os
os.system("cls")
enem = open('enem2014.csv')
l = list(enem)

def busca_escolas():
        escola = str(raw_input("Digite o nome da escola: ")).upper()
        for i in l:
            dados = i.split(";")
            if escola == dados[1] or escola in dados[1]:
                print dados[0],dados[1]
        

def top_ranking():
        cc = input("Digite a quantidade de escolas: ")
        ranking = []
        escolas = []
        for i in l:
            dados = (i.split(";"))
            ranking.append(dados[0])
            escolas.append(dados[1])
        for j in range(cc):
                print ranking[j],escolas[j]
                
                    
                

def busca_municipio():
        municipio = str(raw_input("Digite o Municipio: ")).upper()
        for i in l:
            dados = i.split(";")
            if municipio in dados[2]:
                print dados[0],dados[1]
        
def busca_uf():
        UF = str(raw_input("Digite a sigla do estado: ")).upper()
        for i in l:
            dados = i.split(";")
            if UF == dados[3]:
                print dados[3],dados[1]
        

def top_uf():
        UF = str(raw_input("Digite o Estado: ")).upper()
        cc = input("Digite a quantidade de escolas: ")
        top = []
        notas = []
        for i in l:
                 dados = i.split(";")
                 if UF in dados[3]:
                        top.append(dados[1])
                        notas.append(dados[7])
        for i in range(cc):
                print top[i]
                        
                    
def busca_rede():
        UF = str(raw_input("Digite a sigla do estado: ")).upper()
        rede = str(raw_input("Digite o tipo da rede: ")).capitalize()
        for i in l:
            dados = i.split(";")
            if rede in dados[4] and UF in dados[3]:
                    print dados[2],dados[1]

def per():
        UF = str(raw_input("Digite a sigla do estado: ")).upper()
        rede = str(raw_input("Digite o tipo da rede: ")).capitalize()
        municipio = str(raw_input("Digite o municipio: ")).upper()
        for i in l:
            dados = i.split(";")
            if UF in dados[3] and rede in dados[4] and municipio in dados[2]:
                    print dados[0],dados[1],dados[5]

 
def clear():
    os.system("cls")
                
def menu():
        inicio = "**************** SISTEMA DE BUSCA ENEM 2014 ********************"
        texto = ' 1 - Buscar por nome da escola \n 2 - Top ranking Nacional \n 3 - Buscar por municipio \n 4 - Buscar por Estado \n 5 - Top escolas por Estado \n 6 - Buscar por Rede de Ensino \n 7 - Indicador de Permanencia na Escola \n 8 - Sair \n 0 - Para limpar a tela'
        print inicio
        print texto
        op = input("Digite sua opcao: ")
        while (op != 8):
                if op == 1:
                        busca_escolas()
                elif op == 2:
                        top_ranking()
                elif op == 3:
                        busca_municipio()
                elif op == 4:
                        busca_uf()
                elif op == 5:
                        top_uf()
                elif op == 6:
                        busca_rede()
                elif op == 7:
                         per()
                elif op == 0:
                        clear()
                print inicio
                print texto
                op = input()
        print 'Sessao encerrada.'
menu()  



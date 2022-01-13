import os
os.system('cls') #limpar o terminal
listaonibus = []
listapontosa = []
listapontosb = []
listapontosc = []
listapontosd = []
insercao = None
antes = None
depois = None
exclua = None
class onibus:
    def _init_ (self, idonibus,  nomemotorista, nomefiscal):
        self.idonibus = idonibus
        self.nomemotorista = nomemotorista
        self.nomefiscal = nomefiscal
    def inseredados(self):
        self.nomemotorista = input("Insira o nome do motorista: ")
        self.nomefiscal = input("Insira o nome do fiscal: ")

class pontos:
    def _init_ (self, ponto, listapontos):
        self.ponto = ponto
        self.listapontos = listapontos

    def inserirponto(self, listapontos, insercao):
        insercao = str(input("Digite o ponto que deseja adicionar (Rio de Janeiro, Bahia ou Amazonas): "))
        if (listapontos.count('Rio de Janeiro' or 'Bahia' or 'Amazonas') >= 1):
            print("Não é possivel adicionar esseponto pois já está presente na lista")
        else:
            if insercao == 'Amazonas':
                self.ponto =  insercao
                listapontos.append(self.ponto)
            elif insercao == 'Bahia':
                self.ponto =  insercao
                listapontos.append(self.ponto)
            elif insercao == 'Rio de Janeiro':
                self.ponto =  insercao
                listapontos.append(self.ponto)
            else:
                print("Esse ponto não está no serviço.")

    def excluirponto(self, listapontos, exclua):
        exclua = input("Escolha o ponto que deseja exluir: ")
        if exclua in listapontos:
            listapontos.pop(listapontos.index(exclua))
        else:
            print("Não há esse ponto.")

    def mostrarpontos(listapontos):
            return listapontos


    def substituirponto(self, listapontos, antes, depois):

        antes = input('Digite o ponto que você deseja substituir: ')
        depois = input('Digite o ponto que estara no lugar dele: ')
        if depois in listapontos:
            print("Esse ponto já existe na lista")
        else:
            listapontos[listapontos.index(antes)] = depois

a = pontos()
b = pontos()
c = pontos()
d = pontos()

listadelinhas = [a,b,c,d]

#funções para base do sistema de escrita e configuração:

def salvaronibus(listaonibus): #salvar onibus no documento txt
    with open("bancoonibuspoo.txt","w") as bancoonibus:
        for c in listaonibus:
            bancoonibus.write("{}|{}|{}\n".format(c.idonibus, c.nomemotorista, c.nomefiscal))

def carregaronibus(listaonibus): #salvar onibus no documento txtcarregar onibus para lista
    listaonibus = []
    c = onibus()
    with open("bancoonibuspoo.txt", "r") as bancoonibus:
        for linhas in bancoonibus.readlines():
            colunas = linhas.strip().split("|")

            c.idonibus = colunas[0]
            c.nomemotorista = colunas[1]
            c.nomefiscal = colunas[2]

            listaonibus.append(c)
    return listaonibus

def existenciaonibus(listaonibus, idonibus): #existencia do onibus
    if len(listaonibus) > 0:
        for c in listaonibus:
            if c.idonibus == idonibus:
                return True
    return False

#FUNÇÕES BASICAS
def insere(listaonibus): #vou usar id do onibus como forma de chave para achar o onibus
    c = onibus()
    while True:

        idonibus = input("Digite o id do onibus: ").lower()
        if not existenciaonibus(listaonibus, idonibus):
            break
        else:
            print("id de onibus já utilizado.")
            print("Tente novamente, insira outro id.")
    c.idonibus = idonibus
    c.inseredados()
    listaonibus.append(c)
    print("O onibus {} foi salvo.\n". format(c.idonibus))

def remove(listaonibus): #remover onibus
    print("============Excluir onibus============")
    if len(listaonibus) > 0:
        idonibus = input("Digite o id do onibus que você deseja apagar: ")
        if existenciaonibus(listaonibus ,idonibus):
            for i, c in enumerate(listaonibus):
                if c.idonibus == idonibus:
                    print("Segue as informações deste onibus: ")
                    print("\tnome do motorista: {}".format(c.nomemotorista))
                    print("\tid: {}".format(c.idonibus))
                    print("\tnome do fiscal: {}".format(c.nomefiscal))
                    print("==============================")
                    del listaonibus[i]
                    print("onibus com id: {}.".format(c.idonibus))
                    break
        else:
            print("Não há onibus com o id: {}.".format(c.idonibus))
    else:
        print("Ainda não há onibus neste banco de onibus.")

def edita(listaonibus): #editar onibus
    print("============Editar onibus============")
    if len(listaonibus) > 0:
        idonibus = input("Digite o id do onibus que você busca: ")
        if existenciaonibus(listaonibus , idonibus):
            for c in listaonibus:
                if c.idonibus == idonibus:
                    print("Segue as informações deste onibus: ")
                    print("\tnome do motorista: {}".format(c.nomemotorista))
                    print("\tid: {}".format(c.idonibus))
                    print("\tnome do fiscal: {}".format(c.nomefiscal))
                    print("==============================")

                    c.nomemotorista = input("Digite o novo nome do motorista do onibus: ")
                    c.nomefiscal = input("Digite o novo nome do fiscal do onibus: ")
    
                    print("O onibus com id {} foi alterado com sucesso".format(c.idonibus))
                    break
        else:
            print("Não há onibus com o idonibus: {}.".format(idonibus))
    else:
        print("Ainda não há onibus neste banco de onibus.")

def buscar(listaonibus): #procurar onibus
    print("============Busca de onibus============")
    if len(listaonibus) > 0:
        idonibus = input("Digite o id do onibus que você busca: ")
        if existenciaonibus(listaonibus ,idonibus):
            for c in listaonibus:
                if c.idonibus == idonibus:
                    print("Segue as informações deste onibus: ")
                    print("\tnome do motorista: {}".format(c.nomemotorista))
                    print("\tid: {}".format(c.idonibus))
                    print("\tnome do fiscal: {}".format(c.nomefiscal))
                    print("==============================")
                    break
        else:
            print("Não há onibus com o id: {}.".format(idonibus))
    else:
        print("Ainda não há onibus neste banco de onibus.")



def listar(listaonibus): #mostrar onibus
    if len(listaonibus) > 0:
        print("============Listar onibus============")
        for i, c in enumerate(listaonibus):
            print("onibus {}".format(i+1))
            print("\tnome do motorista: {}".format(c.nomemotorista))
            print("\tid do onibus): {}".format(c.idonibus))
            print("\tnomefiscal: {}".format(c.nomefiscal))
            print("==============================")
    else:
            print("não há onibus")

def listartudo(listaonibus):
    if len(listaonibus) > 0:
        print("============Listar onibus============")
        for i, c in enumerate(listaonibus):
            print("onibus {}".format(i+1))
            print("\tnome do motorista: {}".format(c.nomemotorista))
            print("\tid do onibus): {}".format(c.idonibus))
            print("\tnomefiscal: {}".format(c.nomefiscal))
            print("pontos: ")
            listadelinhas[i].mostrarpontos()
            print("==============================")

            

    else:
        print("não há onibus")
    
def inserirp():
    o = input("Digite em qual onibus deseja inserir um ponto (1, 2, 3 ou 4)")
    if o == '1':
        listadelinhas[0].inserirponto(listapontosa, insercao)
    if o == '2':
        listadelinhas[1].inserirponto(listapontosb, insercao)
    if o == '3':
        listadelinhas[2].inserirponto(listapontosc, insercao)
    if o == '4':
        listadelinhas[3].inserirponto(listapontosd, insercao)

def substituirp():
    o = input("Digite qual onibus deseja alterar um ponto (1, 2, 3 ou 4)")
    if o == '1':
        listadelinhas[0].substituirponto(listapontosa, antes, depois)
    if o == '2':
        listadelinhas[1].substituirponto(listapontosb, antes, depois)
    if o == '3':
        listadelinhas[2].substituirponto(listapontosc, antes, depois)
    if o == '4':
        listadelinhas[3].substituirponto(listapontosd, antes, depois)
    
def escluirp():
    o = input("Digite qual onibus deseja excluir um ponto (1, 2, 3 ou 4)")
    if o == '1':
        listadelinhas[0].excluirponto(listapontosa, exclua)
    if o == '2':
        listadelinhas[1].excluirponto(listapontosb, exclua)
    if o == '3':
        listadelinhas[2].excluirponto(listapontosc, exclua)
    if o == '4':
        listadelinhas[3].excluirponto(listapontosd, exclua)



def principal(listaonibus): #Função principal (para cada condição que o documento.txt terá uma função para salvar o documento alterado)
    listaonibus = carregaronibus(listaonibus)
    '''carregarpontos(listapontos)'''
    escolha = 0
    while escolha != 10:
        print('_Banco Onibus_')
        print("Temos 4 onibus, informações como id do onibus, nome do motorista\n e nome do fiscal serão salvas em um banco para não serem perdidas")
        print(' 1 - Adicionar onibus (id, motorista e fiscal)')
        print(' 2 - Editar onibus (motorista e fiscal')
        print(' 3 - Excluir onibus (Excluir todas infos do onibus')
        print(' 4 - Buscar onibus (Buscar informações de um onibus pelo id')
        print(' 5 - Listar onibus (Mostrar somente todos os onibus)')
        print(' 6 - Inserir pontos de onibus')
        print(' 7 - Editar pontos de onibus')
        print(' 8 - Excluir pontos de onibus')
        print(' 9 - Listar pontos de onibus')
        print(' 10 - Sair')
        escolha = int(input('Digite a opção desejada: '))

        if escolha == 1:
            insere(listaonibus)
            salvaronibus(listaonibus)

        elif escolha == 2:
            edita(listaonibus)
            salvaronibus(listaonibus)

        elif escolha == 3:
            remove(listaonibus)
            salvaronibus(listaonibus)

        elif escolha == 4:
            buscar(listaonibus)
            
        elif escolha == 5:
            listar(listaonibus)

        elif escolha == 6:
            inserirp()

        elif escolha == 7:
            substituirp()

        elif escolha == 8:
            escluirp()

        elif escolha == 9:
            listartudo(listaonibus)

        elif escolha == 10:
            print("Obrigado por utilizar o editor de banco de onibus, até mais tarde")



principal(listaonibus)

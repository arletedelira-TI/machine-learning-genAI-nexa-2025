print("testando...")

import speech_recognition as sr
import os


# Função responsável por ouvir e reconhecer a fala
def ouvir_microfone():
    # Habilita o microfone para ouvir o usuário
    microfone = sr.Recognizer()

    # Usando o microfone
    with sr.Microphone() as source:
        # Chama um algoritmo de redução de ruídos no som
        microfone.adjust_for_ambient_noise(source)
        
        # Avisa o usuário que está pronto para ouvir
        print("Diga alguma coisa: ")
        
        # Armazena a informação de áudio na variável
        audio = microfone.listen(source)

    try:
        # Passa a variável para o algoritmo reconhecedor de padrões
        frase = microfone.recognize_google(audio, language='pt-BR')

        if "navegador" in frase:
            os.system("start chrome.exe")
            return False
        
        elif "Excel" in frase:
            os.system("start excel.exe")
            return False
        
        elif "PowerPoint" in frase:
            os.system("start POWERPNT.exe")
            return False
        
        elif "Edge" in frase:
            os.system("start msedge.exe")
            return False
        
        elif "Fechar" in frase:
            os.system("exit")
            return True
    
        # Retorna a frase pronunciada
        print("Você disse: " + frase)
    
    # Se não reconheceu o padrão de fala, exibe a mensagem
    except sr.UnknownValueError:
        print("Não entendi")
    
    return False
    
while True:
    if ouvir_microfone():
        break

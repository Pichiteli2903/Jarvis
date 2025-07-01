import tkinter as tk
import pyttsx3
from tkinter import simpledialog

# Inicializar o mecanismo de voz
engine = pyttsx3.init()
engine.setProperty('rate', 160)  # velocidade da fala

def falar(texto):
    engine.say(texto)
    engine.runAndWait()

def perguntar(titulo, pergunta):
    falar(pergunta)
    resposta = simpledialog.askstring(titulo, pergunta)
    return resposta

def iniciar_jarvis():
    root = tk.Tk()
    root.withdraw()  # Oculta a janela principal

    falar("Olá, eu sou Jarvis, seu assistente pessoal de inteligência artificial.")
    falar("Fui criado para conhecer você melhor e ajudar no que for possível.")

    nome = perguntar("Nome", "Qual é o seu nome?")
    if nome:
        falar(f"Prazer em conhecê-lo, {nome}!")

    comida = perguntar("Comida Favorita", "Qual é a sua comida favorita?")
    if comida:
        falar(f"Hmm, {comida} parece deliciosa!")

    hobby = perguntar("Hobby", "Qual é o seu passatempo favorito?")
    if hobby:
        falar(f"Que legal! Eu adoraria aprender mais sobre {hobby}.")

    animal = perguntar("Animal Favorito", "Qual é o seu animal favorito?")
    if animal:
        falar(f"Ah, {animal}s são incríveis!")

    falar("Obrigado por compartilhar um pouco sobre você.")
    falar("Estarei sempre por aqui quando precisar de mim.")
    falar("Encerrando a sessão... Até logo!")

# Executar
iniciar_jarvis()

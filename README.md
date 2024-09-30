# aula-de-IA
codigo: 
from openai import OpenAI


client = OpenAI(api_key="sk-Oc_9kkywBkfshaM3aa9K6rINz_htsubCoO77YXLcDIT3BlbkFJdymgawpYxB6SERdsyaFucZ5xqB617iEAY0JF1b_agA")

def chat_with_gpt(prompt):
    response = client.chat.completions.create(
        model="gpt -3,5-" ,
        menssages=[{"role": "user", "content": prompt}]
    )

    return response.choices[0].menssage.content.strip()

if __name__ == "__main__":
    while True:
        user_input = input("Você: ")
        if user_input.lower() in ["quit", "exit", "bye", "sair", "tchau"]:
            break
        response = chat_with_gpt(user_input)
        print("ChatBot: ", response)

import gradio as gr
from app.llm import get_llm

llm = get_llm()

def chat(message, history):
    response = llm.invoke(message)
    return response.content

def create_interface():
    return gr.ChatInterface(
        fn=chat,
        title="Simple LLM Chatbot",
        description="Chatbot built using Groq + LangChain"
    )
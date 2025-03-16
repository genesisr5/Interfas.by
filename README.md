import tkinter as tk
from tkinter import messagebox

def agregar_elemento():
    elemento = entrada_texto.get()
    if elemento:
        lista.insert(tk.END, elemento)
        entrada_texto.delete(0, tk.END)
    else:
        messagebox.showwarning("Advertencia", "El campo de texto está vacío.")

def limpiar_lista():
    lista.delete(0, tk.END)

# Configuración de la ventana principal
root = tk.Tk()
root.title("Aplicación con Tkinter")
root.geometry("400x300")

# Widgets de la interfaz
tk.Label(root, text="Ingrese un elemento:").pack(pady=5)

entrada_texto = tk.Entry(root, width=40)
entrada_texto.pack(pady=5)

boton_agregar = tk.Button(root, text="Agregar", command=agregar_elemento)
boton_agregar.pack(pady=5)

lista = tk.Listbox(root, width=50, height=10)
lista.pack(pady=5)

boton_limpiar = tk.Button(root, text="Limpiar", command=limpiar_lista)
boton_limpiar.pack(pady=5)

# Ejecutar la aplicación
root.mainloop()


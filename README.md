class Archivo:
    def __init__(self, nombre):
        """
        Constructor de la clase Archivo.
        Inicializa el objeto con el nombre del archivo y abre el archivo en modo escritura.
        """
        self.nombre = nombre
        self.archivo = open(nombre, 'w')
        print(f"Archivo '{self.nombre}' creado y abierto para escritura.")

    def escribir(self, texto):
        """
        Método para escribir texto en el archivo.
        """
        self.archivo.write(texto + '\n')
        print(f"Texto escrito en '{self.nombre}'.")

    def __del__(self):
        """
        Destructor de la clase Archivo.
        Cierra el archivo cuando el objeto es eliminado.
        """
        self.archivo.close()
        print(f"Archivo '{self.nombre}' cerrado y recursos liberados.")

# Demostración del uso de la clase
if __name__ == "__main__":
    archivo1 = Archivo("ejemplo.txt")  # Se invoca el constructor
    archivo1.escribir("Hola, mundo!")
    del archivo1  # Se invoca el destructor

    # Creando otro archivo para demostrar eliminación automática
    archivo2 = Archivo("otro_ejemplo.txt")
    archivo2.escribir("Python es genial!")

    # El destructor se invoca automáticamente cuando el objeto sale del ámbito

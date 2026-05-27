# pagina-web-simple-
from flask import Flask, render_template, request

app = Flask(__name__)

# Página principal
@app.route("/")
def inicio():
    return render_template("index.html")

# Registro
@app.route("/registro", methods=["GET", "POST"])
def registro():

    if request.method == "POST":

        nombre = request.form["nombre"]
        email = request.form["email"]

        return f"""
        <h1>Registro exitoso</h1>
        <p>Bienvenido {nombre}</p>
        <p>Email: {email}</p>
        """

    return render_template("registro.html")

# Ejecutar servidor
if __name__ == "__main__":
    app.run(debug=True)

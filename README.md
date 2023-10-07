# Script-Base-De-Datos

CREATE DATABASE FabricaDeSillas;
USE FabricaDeSillas;

CREATE TABLE Material (
    id INT PRIMARY KEY,
    descripcion VARCHAR(200),
    precio DECIMAL(8,2),
    cantidad INT
);

CREATE TABLE Producto (
    codigo INT PRIMARY KEY,
    descripcion VARCHAR(200),
    precio DECIMAL(8,2),
    cantidad INT,
    Materialmaterial INT,
    FOREIGN KEY (Materialmaterial) REFERENCES Material(id)
);

CREATE TABLE Cliente (
    cui INT PRIMARY KEY,
    nombres VARCHAR(50),
    apellidos VARCHAR(50),
    nit VARCHAR(20),
    direccion VARCHAR(200)
);

CREATE TABLE Orden (
    numero INT PRIMARY KEY,
    fecha VARCHAR(15),
    total DECIMAL(8,2),
    Productoproducto INT, 
    Clientecliente INT, 
    FOREIGN KEY (Productoproducto) REFERENCES Producto(codigo),
    FOREIGN KEY (Clientecliente) REFERENCES Cliente(cui)
);

CREATE TABLE Factura (
    serie VARCHAR(10), 
    numero INT,
    fecha VARCHAR(15),
    Ordenorden INT, 
    Clientecliente INT, 
    FOREIGN KEY (Ordenorden) REFERENCES Orden(numero),
    FOREIGN KEY (Clientecliente) REFERENCES Cliente(cui)
);



![Diagrama de entidad relación](https://github.com/rramirezg18/Script-Base-De-Datos/blob/main/Diagrama%20intidad%20relacion%20base%20de%20datos.png)


![Captura sql](https://github.com/rramirezg18/Script-Base-De-Datos/blob/main/Captura%20Script%20base%20de%20datos.png)


# Subida de Archivos a Amazon S3 con Python

Este proyecto permite subir archivos a un bucket de Amazon S3 utilizando boto3. Ofrece la opción de crear un nuevo bucket o usar uno existente. Se asegura el manejo seguro de credenciales mediante variables de entorno.

### 📌 Requisitos Previos

Antes de ejecutar el script, asegúrate de cumplir con los siguientes requisitos:

  - Tener una cuenta de AWS y configurar tus credenciales.

  - Instalar Python (versión 3.7 o superior recomendada).

  - Instalar las dependencias necesarias ejecutando:

      pip install boto3

  - Configurar las credenciales de AWS mediante variables de entorno:

      ## En Linux/macOS (añadir a ~/.bashrc o ~/.zshrc):

        export AWS_ACCESS_KEY_ID="TU_ACCESS_KEY"
        export AWS_SECRET_ACCESS_KEY="TU_SECRET_KEY"
        export AWS_REGION="us-east-1"  # Cambia por la región deseada

      ## En Windows (CMD o PowerShell):
      
        setx AWS_ACCESS_KEY_ID "TU_ACCESS_KEY"
        setx AWS_SECRET_ACCESS_KEY "TU_SECRET_KEY"
        setx AWS_REGION "us-east-1"
      
      ## Verificar que las claves están configuradas:
      
        echo $AWS_ACCESS_KEY_ID
        echo $AWS_SECRET_ACCESS_KEY
        echo $AWS_REGION

### 🚀 Cómo Ejecutar el Script

  Clona este repositorio o descarga el script:
  
    git clone https://github.com/DaniB-11/s3-uploader.git
    cd s3-uploader
  
  Ejecuta el script de Python:
  
    python upload_to_s3.py
  
  Sigue las instrucciones en la terminal:
  
  - Se te preguntará si deseas crear un nuevo bucket o usar uno existente.
  
  - Si eliges crear un bucket, ingresa el nombre deseado.
  
  - Luego, ingresa la ruta del archivo que deseas subir sin comillas.

### 📂 Ejemplo de Uso

¿Quieres crear un nuevo bucket o usar uno existente? (crear/usar): crear

Ingresa el nombre del nuevo bucket: mi-bucket-prueba

Bucket 'mi-bucket-prueba' creado exitosamente en la región 'us-east-1'.

Ingresa la ruta del archivo a subir: /home/user/documento.pdf

Archivo 'documento.pdf' subido exitosamente a 'mi-bucket-prueba'.


### ✅ Validación de la Carga

Para confirmar que el archivo se ha subido correctamente, puedes revisar tu bucket en la consola de AWS.

### 🛠 Posibles Errores y Soluciones

| Error                          | Causa Posible                                      | Solución                                           |
|--------------------------------|---------------------------------------------------|---------------------------------------------------|
| No se encontraron credenciales de AWS | Variables de entorno no configuradas           | Verifica con `echo $AWS_ACCESS_KEY_ID`.           |
| El archivo no existe          | Ruta incorrecta                                  | Usa la ruta completa del archivo sin comillas.    |
| El bucket ya existe y es de otra cuenta | Nombre ya tomado                              | Usa un nombre único o selecciona otro bucket.    |

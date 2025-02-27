# Blueprints API

## Descripción

Blueprints API es una aplicación RESTful que permite gestionar planos (blueprints) de manera eficiente. La API permite realizar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) sobre los planos, y está diseñada para ser utilizada en un entorno concurrente.

## Tabla de Contenidos

- [Características](#características)
- [Tecnologías Utilizadas](#tecnologías-utilizadas)
- [Instalación](#instalación)
- [Uso](#uso)
- [Endpoints](#endpoints)
- [Análisis de Concurrencia](#análisis-de-concurrencia)
- [Contribuciones](#contribuciones)
- [Licencia](#licencia)

## Características

- Gestión de planos con operaciones CRUD.
- Soporte para múltiples autores y planos.
- Manejo de concurrencia para asegurar la integridad de los datos.
- Respuestas en formato JSON.

## Tecnologías Utilizadas

- Java 1.8
- Spring Boot
- Maven
- JUnit (para pruebas)
- Concurrent Collections (para manejo de concurrencia)

## Instalación

1. Clona el repositorio:
   ```bash
   git clone https://github.com/ARSWLABS/Lab5/blueprints-api.git
   ```

2. Navega al directorio del proyecto:
   ```bash
   cd blueprints-api
   ```

3. Compila el proyecto usando Maven:
   ```bash
   mvn clean install
   ```

4. Ejecuta la aplicación:
   ```bash
   mvn spring-boot:run
   ```

## Uso

Una vez que la aplicación esté en ejecución, puedes interactuar con la API utilizando herramientas como `curl` o Postman.

### Ejemplo de Petición POST

```bash
curl -i -X POST -H "Content-Type: application/json" -H "Accept: application/json" \
http://localhost:8080/blueprints -d '{
    "name": "Blueprint Example",
    "author": "Juan",
    "points": [
        {"x": 1, "y": 2},
        {"x": 3, "y": 4}
    ]
}'
```

## Endpoints

- `GET /blueprints`: Obtiene todos los planos.

![image](https://github.com/user-attachments/assets/ccc1f1f2-24ef-4994-a30e-8e668e3ec591)


- `GET /blueprints/{author}`: Obtiene todos los planos de un autor específico.


![image](https://github.com/user-attachments/assets/9d2bd076-fa09-473d-a3f5-d9eecfd9151e)

- `GET /blueprints/{author}/{plano}`: Obtiene todo de un plano especifico de un autor específico.

![image](https://github.com/user-attachments/assets/2744df5b-bf1d-42d1-bfc6-e07bbbe7eb4a)
  
- `POST /blueprints`: Agrega un nuevo plano.


![image](https://github.com/user-attachments/assets/86a205a2-5d5c-4c8d-bd54-9f0144402fc2)

![image](https://github.com/user-attachments/assets/17260818-74d6-443d-9690-fa428b55f8e7)

![image](https://github.com/user-attachments/assets/1f5e31e4-ead7-40d6-8647-b190b32cfcc9)


## Análisis de Concurrencia

El componente BlueprintsRESTAPI está diseñado para manejar múltiples peticiones simultáneamente. Se han implementado colecciones seguras para hilos y métodos atómicos para evitar condiciones de carrera. Para más detalles, consulta el archivo [ANALISIS_CONCURRENCIA.txt](ANALISIS_CONCURRENCIA.txt).

## Contribuciones

Las contribuciones son bienvenidas. Si deseas contribuir, por favor sigue estos pasos:

1. Haz un fork del proyecto.
2. Crea una nueva rama (`git checkout -b feature/nueva-caracteristica`).
3. Realiza tus cambios y haz commit (`git commit -m 'Agregada nueva característica'`).
4. Haz push a la rama (`git push origin feature/nueva-caracteristica`).
5. Abre un Pull Request.

## Licencia

Este proyecto está bajo la Licencia MIT. Para más detalles, consulta el archivo [LICENSE](LICENSE).


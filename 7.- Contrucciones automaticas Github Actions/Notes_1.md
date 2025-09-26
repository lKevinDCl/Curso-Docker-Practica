# Github Actions

> Se crea un nuevo repositorio (voy a ver si lo puedo hacer desde el que tengo actualmente creado)

>> Tiene que ser un repositorio publico 

> Se crean llaves privadas:

![alt text](../screenshots-Lesson-7/image1.png)

> Se crean variables de entorno secretas:

![alt text](../screenshots-Lesson-7/image2.png)

>> Utilizamos Github Actions:

![alt text](../screenshots-Lesson-7/image3.png)

> 

![alt text](../screenshots-Lesson-7/image4.png)


>> Con respecto a lo investigado indica que se debe generar obligatoriamente un nuevo repositorio para poder trabajar con los github actions:

¡Buena pregunta! En GitHub Actions, los archivos de workflow siempre deben estar dentro del directorio .github/workflows/ para que GitHub los reconozca y los ejecute automáticamente. No puedes moverlos a otra ruta arbitraria como ci/docker-image.yml o infra/workflows.yml sin perder esa funcionalidad. -Respuesta de Microsoft COPILOT 

> asi que seguiremos el github action igual que digital ocean, viendo los videos y tomando nota de lo mas importante


>> El codigo de docer-image.yml: permite realizar alguna accion predeterminada cada que se haga un psh a la rama main como ejemplo, es decir digamos que tengo una nueva version de una imagen, y en lugar de yo ejecutar la imagen, esperar a que se cree para cada version, se le dice a github que se encargue de hacerlo tra haber ehecho el push a la rama main y este desplegara los cambios dentro de mi dockehub, automatizando este proceso a solo un click.

>> A si mismo lo que se busca con esto es mejorar el entorno de producción para que los despliegues sean versionados y centralizados.


# docker-image.yml

name: Docker Image CI

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:

  build:

    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v3
      with:
        fetch-depth: 0
    
    - name: Git Semantic Version
      uses: PaulHatch/semantic-version@v4.0.3
      with:
        major_pattern: "major:"
        minor_pattern: "feat:"
        format: "${major}.${minor}.${patch}-prerelease${increment}"
      id: version
    
    - name: Docker Login
      env:
        DOCKER_USER: ${{ secrets.DOCKER_USER }}
        DOCKER_PASSWORD: ${{ secrets.DOCKER_PASSWORD }}
        
      run: |
        docker login -u $DOCKER_USER -p $DOCKER_PASSWORD
        
    - name: Build Docker Image
      env:
        NEW_VERSION: ${{ steps.version.outputs.version }}
      run: |
        docker build -t klerith/docker-graphql:$NEW_VERSION .
        docker build -t klerith/docker-graphql:latest .
        
    - name: Push Docker Image
      env:
        NEW_VERSION: ${{ steps.version.outputs.version }}
      run: |
        docker push klerith/docker-graphql:$NEW_VERSION
        docker push klerith/docker-graphql:latest
      
    
    
    
    
    
    
    
    
#     - name: Build the Docker image
#       run: docker build . --file Dockerfile --tag my-image-name:$(date +%s)




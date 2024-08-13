## DOCKERFILES

### How to run build docker image from Dockerfile in this repo ?

- Create your project using the desired technology
- Copy the appropriate **Dockerfile** in the project's directory
- Build the image
  > [!NOTE]  
  > You need to be in the project's directory before build the image
- Run your container
  
> [!NOTE]  
> Each time you update your code base, you just have to build a new image to make this last one stay up to date.


> [!WARNING]  
> I suppose docker is installed on your desktop.
> If not, follow the instruction on [this page to install it](https://docs.docker.com/engine/install/ubuntu/).

  ![Vue](https://img.shields.io/badge/Vue%20js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D)

  ```bash
  # Create a vuejs's project
    npm create vue@latest

  # Copy the appropriate dockerfile in your vue directory
    mv vuejs/* <your-project-name>

  # Build your image
    docker build -t <image-name>:<tag-name> .

  # Run your countainer
    docker run -d -p 8000:80 <image-name>:<tag-name>

    # if the specified port(8000) is not available, you can change it to another one.

  # Stop the docker (if you finished using it)

    docker stop <container-id>

    # You can get the container id by running "docker ps -a"
  ```

  ![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)

 ```bash
  # Create a vuejs's project
    npx create-react-app 

  # Copy the appropriate dockerfile in your vue directory
    mv react/* <your-project-name>

  # Build your image
    docker build -t <image-name>:<tag-name> .

  # Run your countainer
    docker run -d -p 8000:80 <image-name>:<tag-name>

    # if the specified port(8000) is not available, you can change it to another one.

  # Stop the docker (if you finished using it)

    docker stop <container-id>

    # You can get the container id by running "docker ps -a"
  ```
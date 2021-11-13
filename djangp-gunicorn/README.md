### Django app deployment with Gunicorn app server

These are the following steps for deploying a django app in a gunicorn server:

1. Install **python, pip and python virtual env**

- pip was installed in the system with

  ```
  sudo apt install -y pip3
  ```

- Python virtual environment was installed using # sudo apt install -y python3-venv

2. Create a virtual env named venv and activated it

- A virtual environment named venv was created in a new directory using

  ```
  python3 -m venv venv

  ```

- Venv is activated with : 
    ```
    source ./venv/bin/activate 

    ```


3. Install django and gunicorn packages in the venv : 

    ```
     pip install django 
     pip install gunicorn


    ```
4. Create a django project: 

    ```

    django-admin startproject demo

    ```

5. Create gunicorn_config.py file as a configuration file of gunicorn server :

    ```
    command = './venv/bin/gunicorn'
    pythonPath = './'
    bind = '192.168.1.66:8089'
    workers = '3'

    ```

6. Edited the settings.py file and add the add host’s IP address(192.168.1.66:8089)  in the hosts array


7. Run gunicorn's comamnd to start the server: 

    ```
    gunicorn - c gunicorn_config.py demo.wsgi 

    ```
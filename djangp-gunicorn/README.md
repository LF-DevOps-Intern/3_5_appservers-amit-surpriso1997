### Django app deployment with Gunicorn app server

These are the following steps for deploying a django app in a gunicorn server:

1. Install **python, pip and python virtual env**

- pip was installed in the system with

  ```
  sudo apt install -y pip3
  ```

- Python virtual environment was installed using
  ````
  sudo apt install -y python3-venv
      ```
  ![Install python virtual env](https://github.com/LF-DevOps-Intern/3_5_appservers-amit-surpriso1997/blob/main/djangp-gunicorn/screenshots/install-python-venv.png)
  ````

2. Create a virtual env named venv and activated it

- A virtual environment named venv was created in a new directory using

  ```
  python3 -m venv venv

  ```

- Venv is activated with :

  ```
  source ./venv/bin/activate

  ```

![Created and actiaved venv](https://github.com/LF-DevOps-Intern/3_5_appservers-amit-surpriso1997/blob/main/djangp-gunicorn/screenshots/created-a-virtual-environment.png)

3. Install django and gunicorn packages in the venv :

   ```
    pip install django
    pip install gunicorn


   ```

![django](https://github.com/LF-DevOps-Intern/3_5_appservers-amit-surpriso1997/blob/main/djangp-gunicorn/screenshots/isntalled%20django-with-pip.png)
![gunicorn](https://github.com/LF-DevOps-Intern/3_5_appservers-amit-surpriso1997/blob/main/djangp-gunicorn/screenshots/installed-gunicorn.png)



4. Create a django project:

   ```

   django-admin startproject demo

   ```
![django project demo](https://github.com/LF-DevOps-Intern/3_5_appservers-amit-surpriso1997/blob/main/djangp-gunicorn/screenshots/created-demo-django-project.png)


5. Create gunicorn_config.py file as a configuration file of gunicorn server :

   ```
   command = './venv/bin/gunicorn'
   pythonPath = './'
   bind = '192.168.1.66:8089'
   workers = '3'

   ```
![gunicorn_config.py file](https://github.com/LF-DevOps-Intern/3_5_appservers-amit-surpriso1997/blob/main/djangp-gunicorn/screenshots/gunicorn-config-file.png)


6. Edited the settings.py file and add the add host’s IP address(192.168.1.66:8089) in the hosts array



7. Run gunicorn's comamnd to start the server:

   ```
   gunicorn - c gunicorn_config.py demo.wsgi

   ```

where -c stands for config file 

![runnign gunicorn command]( https://github.com/LF-DevOps-Intern/3_5_appservers-amit-surpriso1997/tree/main/djangp-gunicorn/screenshots)

![testing in the browser](https://github.com/LF-DevOps-Intern/3_5_appservers-amit-surpriso1997/blob/main/djangp-gunicorn/screenshots/testing-django-in-port-8089.png)
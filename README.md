
# Study project: Deployment of Kittygram project on a remote server
## Description:
Project infra_sprint1 is a study project to get familiar with deployment of an app on a remote server.
It is a part of Python-developer course from Yandex-practicum.
This project allows you to post cards of cats with their photos, date of birth, color and some other info.

## Running project can be seen at:
https://yapkittygramtask.dynv6.net


## how to deploy
### Clone repository and acces it through command line:
```
git clone git@github.com:RealTheOne/infra_sprint1.git
cd infra_sprint1
```
### Create and activate virtual environment:
```
cd backend
python3 -m venv venv
source venv/bin/activate
```
### Install requirements from requirements.txt:
```
python install -r requirements.txt
```
### Do migrations:
```
python manage.py migrate
```
### Change your data for Gunicorn:
```
1. In WorkingDirectory parameter:
sudo nano /etc/systemd/system/gunicorn.service
---------------------
Path to project's directory:
/home/<user-name>/
<directory-with-project>/<manage.py-directory>/

2. In ExecStart parameter:
Automate start:
/home/<user-name>/
<directory-with-project>/<path-to-gunicorn> --bind 0.0.0.0:8080
backend.wsgi
```
### Launch Gunicorn:
```
sudo systmectl start gunicorn_kittygram
```
### Launch Nginx:
```
sudo systmectl start nginx
```

## stack
1. Python
2. Django
3. DRF
4. JWT + Djoser
5. NGinx
6. Gunicorn
7. React

## Author:
 Idrisov Arthur

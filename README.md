# drf-hackathon-template
When I needed such template, I tried different ones available on github including cookicutter, which was an overkill, and didn't find the fitting setup with docker/compose, poetry, postgres integration, custom user, jwt by email out of the box. Luckily, my template fits all of these needs and even has a useful cheatsheet. This repo wasnt made for public, so you may tweak some little things that you dont need


In order to start developing you should:
- add .env
- install poetry
- run `poetry install`
- run `createdb {name}`
- activate venv with poetry shell
- `poetry install`
- migrate 

dont forget to branch out

There is CheatSheet for common things

Services lie in src/services

django app lies in src

settings lie in src/hackathon_project/settings.py

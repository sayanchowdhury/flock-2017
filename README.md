# Flock 2017 - Fedora Hubs slides

## Installation

1. First [install virtualenv](https://virtualenv.pypa.io/en/stable/installation/).
```bash
sudo dnf install python3-pip
pip3 install virtualenv
```

2. Create a virtualenv
```bash
mkdir ~/.virtualenvs
virtualenv --python=`which python3` ~/.virtualenvs/slides
```

3. Then activate this virtualenv, you have to do this everytime you start
   working on the project
```
source ~/.virtualenvs/pycon/bin/activate
```

4. To get the slides working
```
pip install slidedeck
git clone https://github.com/sayanchowdhury/flock-2017
cd flock-2017/fedora_hubs
slidedeck watch
```
In a new terminal
```
python3 -m http.server
```

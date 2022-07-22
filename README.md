ansible-role-saprouter-deployment
===

Prepare ansible test environment
---

python3 -m venv ~/.ansible-role-saprouter-deployment
source ~/.ansible-role-saprouter-deployment/bin/activate
python3 -m pip install --upgrade pip
pip3 install ansible
pip3 install 'ansible-lint[yamllint]'
pip3 install 'molecule[docker]'

ansible-galaxy init

molecule init role mprusov.ansible-role-saprouter-deployment -d docker

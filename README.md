# ansible-utility-playbooks
Various Ansible playbooks

The reference documentation for the Tower API can be found at

https://docs.ansible.com/ansible-tower/latest/html/towerapi/api_ref.html
http://<Tower server name>/api/

Examples:

Add the host ttt.example.com to the group jws in the inventory "RHV Infrastructure"
ansible-playbook -i ../inventory ansible_tower_add_host.yml -e "vm_fq_hostname=ttt.example.com" -e 'tower_inventory="RHV Infrastructure"' -e 'tower_group="jws"'

Add the host ttt.example.com to the inventory "RHV Infrastructure"
ansible-playbook -i ../inventory ansible_tower_add_host.yml -e "vm_fq_hostname=ttt.example.com" -e 'tower_inventory="RHV Infrastructure"' 

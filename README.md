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

Delete the host ttt.example.com from the inventory "RHV Infrastructure"
ansible-playbook -i ../inventory ansible_tower_delete_host.yml -e "vm_fq_hostname=ttt.example.com" -e 'tower_inventory="RHV Infrastructure"'

For reference:  Example curl command to invoke a workflow template and to specify variable values
curl -s -k --user 'admin:mypw' -H 'Content-Type: application/json' -X POST https://tower.example.com/api/v2/workflow_job_templates/12/launch/ --data '{ "extra_vars": { "rhv_vm_name": "web02", "tower_group": "jws", "tower_inventory": "RHV Infrastructure", "vm_fq_hostname": "web02.aeronet.io" }}' |json_pp

```bash
cd ansible
docker-compose up
```

```bash
docker exec -w /home/ansible_controller/ansible_files/ -ti ansible_controller bash
```

```bash
ansible all -i inventory.ini -m ping
```

```bash
   ansible-playbook -i inventory.ini playbook.yml
```



-create key-pair / download to .ssh / chmod 400
-upload setup/setup-env.yml into cloudFormation & create stack
-ansible : build inventory file (hosts-dev) :: https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html
-ansible : modules etc :: https://docs.ansible.com/ansible/latest/modules/modules_by_category.html
-ansible-playbook playbooks/all-playbooks.yml
-@kubemaster :: sudo kubeadm init --pod-network-cidr=10.244.0.0/16 --ignore-preflight-errors=NumCPU
-ansible-playbook playbooks/kubectl-setup.yml
-@kubenodes:: sudo kubeadm join $some_ip:6443 --token$some_token --discovery-token-ca-cert-hash $some_hash \\
    ansible-playbook playbooks/kubeadm-join.yml
-@kubemaster :: kubectl get nodes

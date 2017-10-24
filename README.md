# ose-prep
ose prepare playbook
ansible-playbook  -i inventory/hosts.yml ose_prep.yml

#Deploy OSE cluster 
ansible-playbook -i ose-sample-v2.yml  /usr/share/ansible/openshift-ansible/playbooks/byo/config.yml --key-file "/home/ec2-user/Openshift_test.pem" -vvv

#Uninstall OSE Cluster
ansible-playbook -i ose-cohesive-containersied.yml  /usr/share/ansible/openshift-ansible/playbooks/adhoc/uninstall.yml  --key-file "/home/ec2-user/Openshift_test.pem" -vvv  -e 'host_key_checking=False'


#Deploys  metrics 
ansible-playbook -i ose-sample-v1.yml  /usr/share/ansible/openshift-ansible/playbooks/byo/openshift-cluster/openshift-metrics.yml --key-file "/home/ec2-user/Openshift_test.pem" -vvv  -e openshift_metrics_install_metrics=True -e openshift_metrics_hawkular_hostname=hawkular-metrics.openshift.local


#Deploys Logging 
ansible-playbook -i ose-sample-v1.yml  /usr/share/ansible/openshift-ansible/playbooks/byo/openshift-cluster/openshift-logging.yml --key-file "/home/ec2-user/Openshift_test.pem" -vvv


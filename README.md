# ose-prep
ose prepare playbook
ansible-playbook  -i inventory/hosts.yml ose_prep.yml

#Deploys  metrics 
ansible-playbook -i ose-sample-v1.yml  /usr/share/ansible/openshift-ansible/playbooks/byo/openshift-cluster/openshift-metrics.yml --key-file "/home/ec2-user/Openshift_test.pem" -vvv  -e openshift_metrics_install_metrics=True -e openshift_metrics_hawkular_hostname=hawkular-metrics.openshift.local


#Deploys Logging 
ansible-playbook -i ose-sample-v1.yml  /usr/share/ansible/openshift-ansible/playbooks/byo/openshift-cluster/openshift-logging.yml --key-file "/home/ec2-user/Openshift_test.pem" -vvv


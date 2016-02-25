## Tomcat Cluster Deployment

- Requires Ansible 1.2 or newer
- Expects CentOS/RHEL 6.x hosts

These playbooks deploy a very basic implementation of a Tomcat Cluster with an HAProxy in front
To use them, first edit the "hosts" inventory file to contain the
hostnames of the machines on which you want Tomcat and HAProxy deployed. Edit the
groupvars/tomcat-servers and groupvars/lbservers files to set any Tomcat and HAProxy configuration parameters respectively.

Then run the playbook, like this:

	ansible-playbook -i hosts site.yml

When the playbook run completes, you should be able to see the HAProxy running on the port of your choice on the taget machines. The proxy should forward the request to the Tomcat servers based on the balance policy you chose.

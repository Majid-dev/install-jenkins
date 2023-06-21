# Install Jenkins via Ansible

## About Project
This is an Ansible code that installs Jenkins on Ubuntu Linux server and configure CI/CD on that server.

## Playbook: install-jenkins.yml
This playbook updates the apt cache, installs Java (OpenJDK 11), adds the Jenkins repository key, adds the Jenkins repository, installs the Jenkins package, and starts the Jenkins service.

## Playbook: configure-jenkins.yml
After running this playbook, you have Jenkins configured with the necessary plugins and a pipeline job ready for CI/CD.

This playbook performs the following tasks:
- Installs the required plugins for CI/CD, including Git, Workflow Aggregator, Docker Workflow, and Blue Ocean.
- Restarts the Jenkins service if any plugins were installed.
- Creates a Jenkins pipeline job named "MyPipelineJob" with predefined build, test, and deploy stages.

### How to use:
To execute the Ansible playbook and install Jenkins on your Ubuntu Linux server, you can use the following command:

```bash
ansible-playbook -i <your_inventory_file> install_jenkins.yml

ansible-playbook -i <your_inventory_file> configure_jenkins.yml
```
Make sure to replace *jenkinshost* with the appropriate server name or IP address in the playbook, and *<your_inventory_file>* with the path to your Ansible inventory file that contains the server's details.

You can modify the pipeline script within the **config** section of the *jenkins_job* task to include your specific build, test, and deployment steps.
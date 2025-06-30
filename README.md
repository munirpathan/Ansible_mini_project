## Ansible Roles Descriptions

### HTTPD Installation and Configuration

This Ansible playbook automates the installation and configuration of an Apache HTTP server (`httpd`) on managed hosts. It performs the following tasks:

1. **Install HTTPD**: Uses the `yum` module to install the Apache HTTP server (`httpd`) on the managed host.

2. **Start and Enable HTTPD**: Uses the `systemd` module to start and enable the `httpd` service, ensuring that it starts on boot.

3. **Permit Traffic in Default Zone for HTTPS Service**: Uses the `firewalld` module to permit traffic in the default zone for the HTTPS service. The port to be opened is dynamically determined based on the `http_port` variable. After configuring the firewall, a notification is sent to reload the `firewalld` service.

4. **Copy `index.html` File to the Managed Host**: Uses the `copy` module to copy an `index.html` file from the source location (`{{ html_page_src }}`) to the destination location on the managed host (`{{ html_page_dest }}`).

### Nexus Repository Manager Installation and Configuration

This Ansible playbook automates the installation and setup of Nexus Repository Manager on a target host. It performs the following tasks:

1. **Install wget**: Ensures that the `wget` package is installed on the target system.

2. **Install OpenJDK**: Installs the latest version of OpenJDK (Java Development Kit) on the target system.

3. **Create Directory**: Creates the `/app` directory if it does not exist already. This directory will be used for storing the Nexus files.

4. **Download Nexus tar.gz File**: Downloads the Nexus Repository Manager tar.gz file from the official Sonatype website.

5. **Extract Nexus tar.gz File**: Extracts the downloaded Nexus tar.gz file to the `/app` directory on the target system.

6. **Create Nexus User**: Creates a system user named "nexus" on the target system. This user will be used to run the Nexus service.

### Usage

To use these playbook:
1. Make sure Ansible is installed on your control node.
2. Update the inventory file (`hosts`) with the IP address or hostname of your target host.
3. Run the desired playbook using the `ansible-playbook` command:

   ```bash
   ansible-playbook proj-playbook.yml -i inventory/hosts

## Ansible Playbook Description

This Ansible playbook is designed to automate the installation and configuration of an Apache HTTP server (`httpd`) on managed hosts. It also configures the firewall to permit traffic for the HTTPS service and copies an `index.html` file to the managed host.

### Playbook Tasks:

1. **Install HTTPD**:
   - Use the `yum` module to install the Apache HTTP server (`httpd`) on the managed host.

2. **Start and Enable HTTPD**:
   - Use the `systemd` module to start and enable the `httpd` service, ensuring that it starts on boot.

3. **Permit Traffic in Default Zone for HTTPS Service**:
   - Use the `firewalld` module to permit traffic in the default zone for the HTTPS service.
   - The port to be opened is dynamically determined based on the `http_port` variable.
   - After configuring the firewall, a notification is sent to reload the `firewalld` service.

4. **Copy `index.html` File to the Managed Host**:
   - Use the `copy` module to copy an `index.html` file from the source location (`{{ html_page_src }}`) to the destination location on the managed host (`{{ html_page_dest }}`).


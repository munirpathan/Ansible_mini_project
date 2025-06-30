## Ansible Playbook Description

This Ansible playbook automates the installation and setup of Nexus Repository Manager on a target host. It performs the following tasks:

1. **Install wget**: Ensures that the `wget` package is installed on the target system.

2. **Install OpenJDK**: Installs the latest version of OpenJDK (Java Development Kit) on the target system.

3. **Create Directory**: Creates the `/app` directory if it does not exist already. This directory will be used for storing the Nexus files.

4. **Download Nexus tar.gz File**: Downloads the Nexus Repository Manager tar.gz file from the official Sonatype website.

5. **Extract Nexus tar.gz File**: Extracts the downloaded Nexus tar.gz file to the `/app` directory on the target system.

6. **Create Nexus User**: Creates a system user named "nexus" on the target system. This user will be used to run the Nexus service.


# Odoo Installation Scripts

Bash scripts for installing Odoo (versions 12-19) on Linux systems.

## Available Linux Distros [Tested]

### Ubuntu Based

```bash
./odoo-install-ubuntu.sh
```

#### Script Summary

This Bash script automates the installation of Odoo on any Ubuntu-based distribution with dynamic version selection. It performs the following tasks:

1. **Version Selection:**
    - Prompts user to input desired Odoo version (12-19).
    - Validates input (numbers only, removes decimals if present, ensures version is in range).
    - Repeats prompt until valid input is provided.

2. **System Update:**
    - Updates the system repositories to ensure the latest packages are installed.

3. **Python 3.12 Installation:**
    - Checks if Python 3.12 is installed.
    - Installs it using deadsnakes PPA or compiles it from source if unavailable.

4. **Dependencies Installation:**
    - Installs required dependencies like PostgreSQL, Wkhtmltopdf, and various libraries for Odoo.

5. **PostgreSQL Setup:**
    - Starts and enables PostgreSQL.
    - Creates a PostgreSQL user named `odoo` if not already existing.

6. **User and Directory Setup:**
    - Creates a system user `odoo`.
    - Sets up necessary directories for Odoo, including `/opt/odoo/odoo-custom-addons`.

7. **Odoo Source Code:**
    - Clones the selected Odoo version repository from GitHub (if not already cloned).

8. **Virtual Environment:**
    - Creates a Python virtual environment for Odoo and installs Python dependencies.

9. **Configuration File:**
    - Creates an Odoo configuration file (`/etc/odoo.conf`).

10. **Odoo Service Setup:**
    - Configures Odoo as a systemd service to manage its startup and operation.

11. **Service Management:**
    - Reloads the systemd daemon, starts, and enables the Odoo service.

12. **Completion:**
    - Provides the URL to access Odoo and ensures all steps are complete.

The script includes error handling, checks for existing installations, and outputs color-coded messages for easier tracking of progress and errors.
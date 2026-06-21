ansible-role-taskfile
=====================

Installs the [Task](https://taskfile.dev) CLI tool using the official install script.

Requirements
------------

- `curl` must be installable via the system package manager (the role installs it automatically).
- The managed host needs internet access to reach `https://taskfile.dev/install.sh`.
- The role uses `become: true` when writing to system directories.

Role Variables
--------------

| Variable | Default | Description |
|---|---|---|
| `taskfile_version` | `""` | Version to install (e.g. `"v3.40.0"`). Empty installs the latest release. |
| `taskfile_install_dir` | `"/usr/local/bin"` | Directory to install the `task` binary into. |
| `taskfile_force` | `false` | Force reinstall even if the installed version already matches. |

Dependencies
------------

None.

Example Playbook
----------------

Install the latest version to the default location (`/usr/local/bin`):

```yaml
- hosts: servers
  roles:
    - role: bartdorlandt.taskfile
```

Pin a specific version and install to a custom path:

```yaml
- hosts: servers
  roles:
    - role: bartdorlandt.taskfile
      vars:
        taskfile_version: "v3.40.0"
        taskfile_install_dir: "/opt/bin"
```

License
-------

MIT

Author Information
------------------

Bart — dream@dreamnetworking.nl

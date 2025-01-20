# action-debian-package-upload

A simple action to upload a debian package to an apt server using ssh.

### Input 
```yaml
  private_key:
    description: 'Private key'
    required: true
    type: string
  repo_name:
    description: 'Repository Name'
    required: true
    type: string
  debian_package_file:
    description: 'Debian package file'
    required: true
    type: string
  remote_user:
    description: 'Remote user'
    required: true
    type: string
  remote_host:
    description: 'Remote host'
    required: true
    type: string
  remote_dir:
    description: 'Remote directory'
    required: true
    type: string
```

### Usage
```yaml
on:
  push:
    branches:
      - master

jobs:
  release:
    runs-on: ubuntu-latest    
    steps:
      - name: Upload Debian Package
        uses: qcode-software/action-debian-package-upload@v0.3
        with:
          private_key: <<PRIVATE_KEY>>
          repo_name: <<REPO_NAME>>
          debian_package_file: <<DEBIAN_PACKAGE_FILE>>
          remote_user: <<REMOTE_USER>>
          remote_host: <REMOTE_HOST>>
          remote_dir: <<REMOTE_DIRECTORY>>
```

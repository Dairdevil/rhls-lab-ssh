# rhls-lab-ssh

Util script for configuring and connecting to an RHLS lab via SSH

## Usage

### Initialising a connection

```sh
rhls-lab init
```

This starts a wizard that prompts for each required value. See configuration values table below. If there is no profile
currently set to default then the newly created profile is automatically set to default. The wizard will prompt for the
location on the local filesystem of the SSH Key obtained from the RHLS Lab Controls page.

Alternatively the wizard can be skipped by specifying arguments as follows:
```sh
rhls-lab init -p <profile_name> -i <public_ip_address> -k <path_to_ssh_key> [-d]
```
where the flags correspond to

| Flag | Value                                |
|------|--------------------------------------|
| p    | Profile Name                         |
| i    | Public IP Address                    |
| k    | Path to SSH Key                      |
| d    | (Optional) Make this profile default |

All other values are set to their defaults (see Configuration table).

### Connecting to a lab environment

```sh
rhls-lab connect [-p <profile_name>]
```

This connects to the lab environment as configured. If no profile is specified the default profile is used.

### Changing default profile

```sh
rhls-lab profile <profile_name>
```

The default profile is changed to the named profile.

### Adding or Changing an SSH Key

```sh
rhls-lab add-key [-p <profile_name>] -k <path_to_ssh_key>
```

The SSH Key is moved into the configuration directory and the appropriate permissions are applied. If no profile is
specified the default profile is used. Any existing key for the named profile is removed.

## Configuration

The following variables are set in each `config` file for the lab environment.

| Value             | Variable Name        | Description                                                                                    | Default      |
|-------------------|----------------------|------------------------------------------------------------------------------------------------|--------------|
| Public IP Address | RHLS_PUBLIC_IP       | The externally facing IP address to connect to. This should be unique for each lab environment | N/A          |
| Public Port       | RHLS_PUBLIC_PORT     | The externally facing port to connect to                                                       | 22022        |
| Public Username   | RHLS_PUBLIC_USERNAME | The external username to connect to the public facing address as                               | cloud-user   |
| Local IP Address  | RHLS_LOCAL_IP        | The local IP address of the workstation                                                        | 172.25.252.1 |
| Local Port        | RHLS_LOCAL_PORT      | The local port to connect to the workstation                                                   | 53009        |
| Local Username    | RHLS_LOCAL_USERNAME  | The local username to be used when connecting to the workstation                               | student      |

## Author

Alasdair Preston (alasdair.preston@gmail.com)
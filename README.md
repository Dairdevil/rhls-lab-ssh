# rhls-lab-ssh
Util script for configuring and connecting to an RHLS lab via SSH

## Usage

### Initialising a connection
```sh
rhls-lab init
```
This starts a wizard that prompts for each required value. See configuration values table below.

### Connecting to a lab environment

#### Pre-requisites
The SSH key provided in the lab interface must be available at `~/.ssh/rht_classroom.rsa`

#### Connecting
```sh
rhls-lab connect
```
This connects to the lab environment as configured.

## Configuration

The following variables are set in each `config` file for the lab environment.
| Value             | Variable Name    | Description                                                                                    | Default      |
|-------------------|------------------|------------------------------------------------------------------------------------------------|--------------|
| Public IP Address | RHLS_PUBLIC_IP   | The externally facing IP address to connect to. This should be unique for each lab environment | N/A          |
| Public Port       | RHLS_PUBLIC_PORT | The externally facing port to connect to                                                       | 22022        |
| Username          | RHLS_USERNAME    | The local username to be used when connecting to the workstation                               | student      |
| Local IP Address  | RHLS_LOCAL_IP    | The local IP address of the workstation                                                        | 172.25.252.1 |
| Local Port        | RHLS_LOCAL_PORT  | The local port to connect to the workstation                                                   | 53009        |

## Author
Alasdair Preston (alasdair.preston@gmail.com)
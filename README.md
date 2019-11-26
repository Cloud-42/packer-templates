# packer-templates
A collection of useful Packer ( https://www.packer.io/ ) templates.

#### packer_encrypted_base_image.json 
Creates an encrypted base AMI. To build the template use:
packer build  -var 'instance_type=t3.medium' packer_encrypted_base_image.json

##### Variables
| Variable | Meaning |
| :------- | :----- |
| `region`| Region in which to launch the build |
| `instance_type` | Instance type for the temporary ec2 intance |


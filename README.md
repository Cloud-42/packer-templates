# packer-templates
A collection of useful Packer ( https://www.packer.io/ ) templates.

#### packer_encrypted_base_image.json 
Creates an encrypted base AMI. Details:
 * Uses the latest Amazon Linux 2 AMI as its base.
 * Temp IAM profile grants access to SSM parameters.
 * Resultant AMI will be encrypted by default using the KMS key "KMS_KEY_ARN" 

##### Variables
| Variable | Meaning |
| :------- | :----- |
| `region`| Region in which to launch the build |
| `instance_type` | Instance type for the temporary ec2 intance |


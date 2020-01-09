<p align="center">
  <a href="https://www.cloud42.io/" target="_blank" rel="Homepage">
  <img width="200" height="200" src="https://www.cloud42.io/wp-content/uploads/2020/01/transparent_small.png">
  </a>
</p>

---
<p align="center">Need help with your Cloud builds <a href="https://www.cloud42.io/contact/" target="_blank" rel="ContactUS"> DROP US A LINE</a>.</p>

---
# packer-templates
A collection of useful <a href="https://www.packer.io/" target="_blank">Packer</a> templates.

#### Usage & assumptions
 * Local directory "scripts" is created that contains any provisioning scripts 

#### [packer_encrypted_base_image.json](https://github.com/Cloud-42/packer-templates/blob/master/packer_encrypted_base_image.json "packer_encrypted_base_image.json")  
Creates an encrypted base AMI. Details:
 * Uses the latest Amazon Linux 2 AMI as its base.
 * Temp IAM profile grants access to SSM parameters.
 * Resultant AMI will be encrypted by default using the KMS key "KMS_KEY_ARN" 
 * **Spot instances** are used to create the ec2 host.

#### [packer_windows_complex_provisioner.json](https://github.com/Cloud-42/packer-templates/blob/master/packer_windows_complex_provisioner.json "packer_windows_complex_provisioner.json")
Complex template for provisioning a Windows AMI via various methods:
 * Provisioned using file & Powershell provisioners.
 * Secondary volume is added to the AMI based upon the snapshot id given.

##### Variables reference
| Variable | Meaning |
| :------- | :----- |
| `region`| Region in which to launch the build |
| `instance_type` | Instance type for the temporary ec2 intance |
| `media_snapshot_id`| Snapshot id upon which the 2nd volume is based.  |
| `winrm_timeout` | WinRM timeout value |
| `access_key` | Access key |
| `secret_key` | Secret key |

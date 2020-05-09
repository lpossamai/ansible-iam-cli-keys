# ansible-iam-cli-keys
Creating the retrieving the IAM Access and Secret Access Keys using Ansible.


### Ansible IAM module

As per May 2020, the [IAM Ansible module](https://docs.ansible.com/ansible/latest/modules/iam_module.html) allows you to create the AWS [IAM Access Key](https://docs.ansible.com/ansible/latest/modules/iam_module.html#parameter-access_key_state), but unfortunately, [it does not allow you to retrive the nearly created Secret Access Key](https://stackoverflow.com/a/61624771/11053962).

I was trying to automate the creation of my IAM users and had to come up with a workaround.


### This repository

Using this provided code, you'll be able to:

1. Creates IAM Users and their Access and Secret Access Keys for CLI usage
2. Creates FullAdmin (AdministratorAccess) and ReadOnly (ReadOnlyAccess) groups for IAM users
3. Creates and applies the [Force MFA policy](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_users-self-manage-mfa-and-creds.html) to the groups
4. Creates and applies an IAM Password Policy


> This is a work in progress

If you have suggestions, please, submit a Pull Request.


### USAGE

1. Set the [AWS_PROFILE](https://github.com/ansible/ansible/issues/13637#issuecomment-212772817) in your environment - I'm using Arch Linux here: `export AWS_PROFILE=test-profile`
2. Clone the repository
3. Change the variables 'vars/user-list.yml'
4. Update the usernames in the groups for 'task/create-group.yml'

Note: The password to access the Console will be saved in the "passwordfile" file.
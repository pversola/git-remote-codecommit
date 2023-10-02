# Access Services and AWS Resources (AWS CLI)

## How to install aws-azure-login
Befor you can use ***aws-azure-login***, you must install some prerequisites on yout local computer. There include:
- aws-cli
- nodejs 

***aws-azure-login*** requires nodejs version 12 or later. To check your version of nodejs, run the following command:
```
$ node --version
$ npm --version
```
Install aws-azure-login using npm
```
$ npm install -g aws-azure-login
```

### How to configure aws-azure-login
```
$ aws-azure-login --configure
Configuring profile 'default'
? Azure Tenant ID: 95exxxx-xxxx-xxxx-xxxx-xxxxxxxxxxe6
? Azure App ID URI: 528xxxx-xxxx-xxxx-xxxx-xxxxxxxxxx54
? Default Username: m00gen-osc.xxxx@thxxxl.co.th
? Stay logged in: skip authentication while refreshing aws credentials (true|false) false
? Default Role ARN (if multiple): arn:aws:iam::27xxxxxxxx31:role/TMGEcomProjectRole
? Default Session Duration Hours (up to 12): 1
Profile saved.
```

## How to assume roles when run CLI
~./aws/credentials
```
[default]
aws_access_key_id=ASIA...R45
aws_secret_access_key=GbMKC...mvN/d...3
aws_session_token="FwoGZXIv...7RT9NA=="
aws_expiration=2023-10-02T03:18:29.000Z

[ecom-nonprod]
role_arn=arn:aws:iam::86xxxxxxx44:role/TMGEcomDevRole
source_profile=default
```
~./aws/config
```
[default]
azure_tenant_id=95exxxx-xxxx-xxxx-xxxx-xxxxxxxxxxe6
azure_app_id_uri=528xxxx-xxxx-xxxx-xxxx-xxxxxxxxxx54
azure_default_username=m00gen-osc.xxxx@themall.co.th
azure_default_role_arn=arn:aws:iam::27xxxxxxxx31:role/TMGEcomProjectRole
azure_default_duration_hours=1
azure_default_remember_me=false

[profile ecom-nonprod]
output=json
region=ap-southeast-1
```
## How to access Code Commit using (GRC)
### Install Python3   
**git-remote-commit** is require pip version 9.3 or later.   
To check your version of pip run the following command.
```
$ pip --version
```
You can run the fllowing two commands to update your version of pip to the latest version.
```
$ curl -O https://bootstrap.pypa.io/get-pip.py
$ python3 get-pip.py --user
```

Install Get remote CodeCommit using pip
```
$ pip intsall git-remote-codecommit
```

Can you test clone project
```
$ git clone codecommit://<PROFILE>@<REPO-NAME>
```

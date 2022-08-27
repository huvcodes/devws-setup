## ssh-keypair
* ssh-keygen command to generate a ssh keypair

  - Note: [Click here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) for more info
  ```shell
    $ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
  ```


## Setting up multiple Github and/or Git accounts in same PC/workstation
* Create a file named config under your user profile directory (C:\Users\\<your_profile>\\.ssh)
* In the config file, you can setup multiple Git accounts in same computer

  ```shell
    # Profile for AWS Codecommit
    Host git-codecommit.*.amazonaws.com
        User AXXXXXXXXXXXXXXXXXXX                   # AWS KeyID
        IdentityFile ~/.ssh/id_rsa_aws              # RSA file for your AWS Codecommit keys
    # Clone Commands:
    # Windows Hosts : git clone ssh://AXXXXXXXXXXXXXXXXXXX@git-codecommit.*.amazonaws.com/v1/repos/<repo-name>
    # Linux Hosts : git clone ssh://git-codecommit.*.amazonaws.com/v1/repos/<repo-name>



    # Profile for Enterprise/Corporate/Work Github account
    Host github.company.com
        HostName github.company.com
        User git
        IdentityFile ~/.ssh/id_rsa_work             # RSA file for your Github work profile
    # git clone git@github.myorg.com:org-account/<company-project-name>.git



    # Profile for Github Personal Account - 01
    Host github-<your-personal-github-profile-01-name>
        HostName github.com
        IdentityFile ~/.ssh/id_rsa_personal_01      # RSA file for your Github profile - 01
    # git clone git@github-<your-personal-github-profile-01-name>:<your-personal-github-profile-01-name>/<repo-name>.git



    # Profile for Github Personal Account - 02
    Host github-<your-personal-github-profile-02-name>
        HostName github.com
        IdentityFile ~/.ssh/id_rsa_personal_02      # RSA file for your Github profile - 02
    # git clone git@github-<your-personal-github-profile-02-name>:<your-personal-github-profile-02-name>/<repo-name>.git
    # git clone git@github-huvcodes:huvcodes/devws-setup.git
  ```

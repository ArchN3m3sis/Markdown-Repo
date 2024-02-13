As we bgin to push forward with more technically sound ways of markdown backup and personal repository management, the time for true 'git' awareness is upon us. In this tutorial series I will be showing you how to back up your local files to Github Repository database stored securely online... 

The first step we need to complete will be "caching out git credentials", which is just nerd speak for saving your username and passw3ord locallyy on your device, so that you can push the local changes to a remote repository... 

- [0] To install github-cli on linux, copy and paste the code block below into your terminal... 

```bash
type -p curl >/dev/null || (sudo apt update && sudo apt install curl -y)
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
&& sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y
```

>***Take Note!***
>Github was recently forced to change our GPG signing key. If you've previously downloaded the `githubcli-archive-keyring.gpg` file, you should re-download it again per above instructions. If you are using a keyserver to download the key, the ID of the new key is `23F3D4EA75716059`.

- [1] Once you have successfully executed the above command, run the following code: 

```bash
sudo apt update 
sudo apt install gh
```

> ***Reference***
> If you are running a different operating system or if further detailed instruction is needed, you can follow this link to visit the github-cli github page >>> [github-cli repository webpage](https://github.com/cli/cli/blob/trunk/docs/install_linux.md) If you really want to become a Github wiz kid, then you can read additional documentation on the github cli wiki, which can be found in this link: [github-cli](https://cli.github.com/manual/)

- [3] Now that you have updated your system and installed the github-cli application, you will need to enter the followinhg command to login to your account. Carefully follow all of the prompts after this as well...

```bash
gh auth login
```



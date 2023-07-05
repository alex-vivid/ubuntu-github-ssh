# ubuntu-github-ssh-keygen
#### Script for setting up GitHub SSH keys on Ubuntu
```sh
ssh-keygen -t ed25519 -C "alex@vivid-machines.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
sudo apt install xclip
cat ~/.ssh/id_ed25519.pub | xclip -selection clipboard
```
After running the above in your terminal, go to the 'SSH and GPG keys' tab in your GitHub account settings, create a new SSH key, and paste your key from your clipboard. Note that the final command `cat ~/.ssh/id_ed25519.pub | xclip -selection clipboard` may put a timer on what's copied to your clipboard, so just re-run this command to get it again. Alternatively, you can download the bash file, make it executeable with `chmod +x github_ssh_setup.sh`, and run it with `./github_ssh_setup.sh`.

To switch a repo from, say, HTTPS to SSH, run something like `git remote set-url origin git@github.com:alex-vivid/repo.git` after cloning the repository.
# ubuntu-github-ssh
Setup GitHub SSH keys on Ubuntu

# new-linux-setup

install programs
```bash
sudo apt install zsh git make g++ gcc python3 python3-pip
```

latest rustup
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
cargo install ripgrep
```


latex
```bash
sudo apt-get install libfontconfig1-dev libgraphite2-dev libharfbuzz-dev libicu-dev libssl-dev zlib1g-dev
cargo install tectonic
```


setup [gitmoji](https://github.com/carloscuesta/gitmoji-cli)
```bash
sudo apt install npm
sudo npm i -g gitmoji-cli
```

setup keyfiles
```bash
ssh-keygen #click enter for all options
cat /home/{username}/.ssh/id_rsa.pub #copy the output and save it to github
```

setup git
populate git hooks with the content of the folder in this repo
```bash
git config --global user.name "github username"
git config --global user.email "github email" #for example use private mail offerd by github
git config --global core.hooksPath /home/kleingeld/bin/githooks
```

add [commit verification](https://help.github.com/en/articles/managing-commit-signature-verification)
```bash
sudo apt install gpg
# as we are setting up for use with github use your github username and 
# github email for Real Name and email during key generation
gpg --full-generate-key  # default settings except key length use 4096
gpg --list-secret-keys --keyid-format LONG  # copy the bit after 'sec rsa4096/' call it A
gpg --armor --export <A>  # paste this key at github.com/settings/keys
git config --global user.signingkey <A>
git config --global commit.gpgsign true
# sign tags using git tag -s
```

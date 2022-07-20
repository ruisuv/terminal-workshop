# Threshold

## Get the code

### If you have a GitHub account 
Create a fork from this repo [kafka-hello-world-terminal](https://github.com/ruisuv/kafka-hello-world-terminal).


#### Best way: SSH keys
1. Generate SSH keys for Ubuntu machine. 
[Official Guide](https://docs.github.com/es/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
    ```
    ssh-keygen -t ed25519 -C "your_email@example.com"
    ```
2. SSH Agent
    ```
   eval "$(ssh-agent -s)" && ssh-add ~/.ssh/id_ed25519
   ```
3. Add Key to your GitHub account. [Official Guide](https://docs.github.com/es/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)
    ```
     cat ~/.ssh/id_ed25519.pub
    ```
4. Clone it
    ```
    git clone git@github.com:your_user/kafka-hello-world-terminal.git
    ```


#### Not so good: get the zip
1. Download it
2. Copy it to Ubuntu image
    ```
    docker cp 2_threshold/kafka-hello-world-terminal-main.zip $CONTAINER_ID:/repos
    ```
3. 

# Setup SSH credentials for github
## Step 1: Setup ssh credentials
Create ssh credentials
```
ssh-keygen -t ed25519 -C "your-email@example.com" -f ~/.ssh/aliasOfId
```

## Step 2: Add SSH key to SSH agent
1. Start ssh agent: `eval "$(ssh-agent -s)"`
2. Add key to agent: `ssh-add ~/.ssh/personal_email@gmail.com`

## Step 3: Add the key to the github account
1. Read the contents of the key `cat ~/.ssh/personal_email@gmail.com.pub`
2. Copy the entire output (starts with ssh-ed25519).
3. Go to GitHub.com and log in to your personal account.
4. Navigate to: Settings → SSH and GPG keys → New SSH key
5. Give it a title and paste the key.
6. Verify setup: `ssh -T git@github.com`

## Step 4: Configure Git to use the SSH key
This step can be ignored if only one Github account is being used.
Work email is assumed to be the default account.

- Edit SSH config `nano ~/.ssh/config`
- Setup the config
```
# Example config
# Personal GitHub account
Host github-personal
	HostName github.com
	User git
	IdentityFile ~/.ssh/personal_email@gmail.com

# Work GitHub account (default)
Host github.com
	HostName github.com
	User git
	IdentityFile ~/.ssh/your-email@example.com
```

## Step 5: Verify that the setup works
- Verify personal account `ssh -T git@github-personal`
- Verify work account `ssh -T git@github.com`

## Step 6: Setup config at startup time
- Open or create the bash profile: `nano ~/.bash_profile`
- Add the following into the file:
```
# Start SSH agent if not already running
env=~/.ssh/agent.env

agent_load_env () { test -f "$env" && . "$env" >| /dev/null ; }

agent_start () {
    (umask 077; ssh-agent >| "$env")
    . "$env" >| /dev/null
}

agent_load_env

# Check if agent is running
if ! kill -0 "$SSH_AGENT_PID" 2>/dev/null; then
    agent_start
fi

# Add keys in preferred order
ssh-add ~/.ssh/key1
ssh-add ~/.ssh/key2
```
The ssh agent will now always be available when using git bash.
Verify using `source ~/.bash_profile`

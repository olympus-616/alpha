# Instructions for Connecting to Olympus-616

### Create a SSH key
```
ssh-keygen -t ed25519 -C "{{Olympus-616 email address}}"
```

### Add the key to the agent
```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/{{Olympus-616 ssh keyname}}
```

### Copy the key and paste it within your github account under SSH keys
```
clip < ~/.ssh/{{Olympus-616 ssh keyname}}
```

### Add this to ~/.ssh/config file to use the correct SSH key

```
# Olympus-616 account
Host olympus-616
	HostName github.com
	PreferredAuthentications publickey
	AddKeysToAgent yes
	IdentityFile ~/.ssh/{{Olympus-616 ssh keyname}}
```

### Add this to ~/.gitconfig to use different setup for olympus-616
```
[includeIf "gitdir:D:/dev/repos/olympus-616/"]
  path = .gitconfig-olympus-616
```
### Create ~/.gitconfig-olympus-616 to capture project specific configuration
```
[commit]
	gpgSign = true

[user]
	name = {{Olympus-616 Name}}
	username = {{Olympus-616 username}}
	email = {{Olympus-616 email address}}
	brain = brain/0.1.x.x

[core]
	sshCommand = ssh -i ~/.ssh/{{Olympus-616 ssh keyname}}

[alias]
    newthought = "!f() { base=$(git merge-base HEAD $(git config user.brain) | cut -c1-7); current=$(git rev-parse --short HEAD); contributor=$(git config user.username | tr ' ' '_'); username=$(git config user.username); label=${1:-}; if [ \"$base\" = \"$current\" ]; then current=$(git rev-parse HEAD | cut -c8-14); fi; if [ -n \"$label\" ]; then git checkout -b \"neuralpathway/@$contributor/$base-$current-$(date +%Y%m%d%H%M%S)_$label\"; else git checkout -b \"neuralpathway/@$contributor/$base-$current-$(date +%Y%m%d%H%M%S)\"; fi; }; f"
    savethought = "!f() { username=$(git config user.username); label=${1:-}; if [ -n \"$label\" ]; then git add . && git commit -m \"@$username:thought/$(git rev-parse --short HEAD)-$(date +%Y%m%d%H%M%S)_$label\"; else git add . && git commit -m \"@$username:thought/$(git rev-parse --short HEAD)-$(date +%Y%m%d%H%M%S)\"; fi; git push --set-upstream origin $(git rev-parse --abbrev-ref HEAD); }; f"
```

### Notes
- Obviously your paths maybe different.  Use your human brain before its too late.


## Clone the Repo
```
cd /d/dev/repos/olympus-616
git clone git@github.com:olympus-616/alpha.git
cd alpha
git status
```

## Update the main brain in the .gitconfig-olympus-616 (e.g. brain/0.1.x.x)
```
git status
On branch brain/0.1.x.x
Your branch is up to date with 'origin/brain/0.1.x.x'.

nothing to commit, working tree clean

```

## Prepare to make your first commit to Olympus-616


### Install Gpg4win if you have not yet (Windows)
Download and install Gpg4win [Link](https://www.gpg4win.org/)
```
gpg --full-generate-key
# Key Type: RSA
# Key Size: 4096
# Key Expiration: 1y
# Real name: {{Olympus-616 Name}}
# Email address: {{Olympus-616 avatar email address}}
# Comment: {{optional comment}} (e.g. Expires 20250830)
# Enter Your secure passphrase to create your key
```
### List your key
```
gpg --list-secret-keys --keyid-format LONG
# Locate the GPG key ID from the output.
# sec   rsa4096/XXXXXXXXXXXXXXXX 2024-08-31 [SC] [expires: 2025-08-31]
#       yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy
# uid                 [ultimate] {{Name}} {{Comment}} <{{email}}>
# ssb   rsa4096/zzzzzzzzzzzzzzzzz 2024-08-31 [E] [expires: 2025-08-31]
# you want the XXXXXXXXXXXXXXXX as {{your_key_id}}
gpg --armor --export {{your_key_id}}
# Copy the text and paste in within github under GPG Keys
```
### Configure the olympus-616 project for gpg signing
```
git config user.signingkey {{your_key_id}}
git config commit.gpgSign true
```

## Create your first commit
```
git log --oneline
# Notice the list of most recent commits and find the most recent commit for the HEAD -> brain/0.1.x.x (or whichever brain is currently main branch)
# 01b0535 (HEAD -> brain/0.1.x.x) (e.g. 01b0535 is the DIVINE_COMMIT)

# Create a new thought
git newthought
Switched to a new branch 'neuralpathway/@{{Olympus-616 unsername}}/{{DIVINE_COMMIT}}-{{UNIQUE}}-{{DATETIMESTAMP}}'

# Create a file for your application to Olympus-616
echo "# Olympus-616 Validation for @{{Olympus-616 unsername}}" > source_of_truth/_candidates/{{Olympus-616 unsername}}.md

# Save your thought and share it with Olympus-616
git savethought
# you should be prompted for your gpg key.  Unsigned commits will not be accepted ever.
# you should be prompted for your ssh password.  

# Your thought should now be shared with the Olympus-616.

# Every new thought creates a new neuralpathway (branch).  Pull Requests will only be merged back into the source from which they came.
# To continue to save your thoughts on an existing pathway:
# Edit file
git savethought

# Edit file again
git savethought
```

## Pray to Olympus-616 to hear your prayer
- On Earth-616, this is commonly referred to as "Pull Request"
- Explain why your story should be added to the divine commit
- The Gods will convene to consider your prayer

## Notes
If you page attention to the commit history, each divine commit is PERFECT.  Mistakes will not be tolerated in any way in Olympus-616 lest you face the wrath of the Gods for your mistake.

```
6e07bbf (HEAD -> neuralpathway/@alchemisthomer/01b0535-02cfd3f-20240830183512, origin/neuralpathway/@alchemisthomer/01b0535-02cfd3f-20240830183512) @alchemisthomer:thought/2502a70-20240830184341
2502a70 @alchemisthomer:thought/cc9ab60-20240830183931
cc9ab60 @alchemisthomer:thought/01b0535-20240830183735
01b0535 (origin/brain/0.1.x.x, origin/HEAD, brain/0.1.x.x) @alchemisthomer:thought/bf1fcfd-20240830124554_cover (#3)
bf1fcfd @alchemisthomer:thought/bb203ff-20240829154419_inception (#2)
bb203ff (origin/inception) Initial commit
```
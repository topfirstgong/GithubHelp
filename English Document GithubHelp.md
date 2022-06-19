### Generating a new SSH key and adding it to the ssh-agent
In this article
About SSH key generation
Generating a new SSH key
Adding your SSH key to the ssh-agent
Generating a new SSH key for a hardware security key
Further reading
After you've checked for existing SSH keys, you can generate a new SSH key to use for authentication, then add it to the ssh-agent.

Mac
Windows
Linux
About SSH key generation
If you don't already have an SSH key, you must generate a new SSH key to use for authentication. If you're unsure whether you already have an SSH key, you can check for existing keys. For more information, see "Checking for existing SSH keys."

If you want to use a hardware security key to authenticate to GitHub, you must generate a new SSH key for your hardware security key. You must connect your hardware security key to your computer when you authenticate with the key pair. For more information, see the OpenSSH 8.2 release notes.

If you don't want to reenter your passphrase every time you use your SSH key, you can add your key to the SSH agent, which manages your SSH keys and remembers your passphrase.

Generating a new SSH key
Open Git Bash.

Paste the text below, substituting in your GitHub email address.

$ ssh-keygen -t ed25519 -C "your_email@example.com"
Note: If you are using a legacy system that doesn't support the Ed25519 algorithm, use:

$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
This creates a new SSH key, using the provided email as a label.

> Generating public/private algorithm key pair.
When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.

> Enter a file in which to save the key (/c/Users/you/.ssh/id_algorithm):[Press enter]
At the prompt, type a secure passphrase. For more information, see "Working with SSH key passphrases."

> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
Adding your SSH key to the ssh-agent
Before adding a new SSH key to the ssh-agent to manage your keys, you should have checked for existing SSH keys and generated a new SSH key.
If you have GitHub Desktop installed, you can use it to clone repositories and not deal with SSH keys.

Ensure the ssh-agent is running. You can use the "Auto-launching the ssh-agent" instructions in "Working with SSH key passphrases", or start it manually:

# start the ssh-agent in the background
$ eval "$(ssh-agent -s)"
> Agent pid 59566
Add your SSH private key to the ssh-agent. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_ed25519 in the command with the name of your private key file.

$ ssh-add ~/.ssh/id_ed25519
Add the SSH key to your account on GitHub. For more information, see "Adding a new SSH key to your GitHub account."

Generating a new SSH key for a hardware security key
If you are using macOS or Linux, you may need to update your SSH client or install a new SSH client prior to generating a new SSH key. For more information, see "Error: Unknown key type."

Insert your hardware security key into your computer.

Open Git Bash.

Paste the text below, substituting in the email address for your account on GitHub.

$ ssh-keygen -t ed25519-sk -C "your_email@example.com"
Note: If the command fails and you receive the error invalid format or feature not supported, you may be using a hardware security key that does not support the Ed25519 algorithm. Enter the following command instead.

$ ssh-keygen -t ecdsa-sk -C "your_email@example.com"
When you are prompted, touch the button on your hardware security key.

When you are prompted to "Enter a file in which to save the key," press Enter to accept the default file location.

> Enter a file in which to save the key (/c/Users/you/.ssh/id_ed25519_sk):[Press enter]
When you are prompted to type a passphrase, press Enter.

> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
Add the SSH key to your account on GitHub. For more information, see "Adding a new SSH key to your GitHub account."

Further reading
"About SSH"
"Working with SSH key passphrases"
"Authorizing an SSH key for use with SAML single sign-on" in the GitHub Enterprise Cloud documentation

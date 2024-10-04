# Enable signed commits 
*Using SSH keys on GitHub for a Windows user, using PowerShell commands and the ed25519 algorithm*

 1. Generate a New SSH Key:
	   - Open a PowerShell session
	   - Generate an SSH key for signing by running :
 
	     `ssh-keygen -t ed25519 -C "your.name@dept.gc.ca"`
	   - Follow the prompts to save the key in the default location.

2. Tell Git About Your Signing Key:
   - Configure Git to use your SSH key for signing commits:
     
     `git config --global gpg.format ssh`
     
     `git config --global user.signingkey ~/.ssh/id_ed25519`
     
     `git config --global commit.gpgSign true`
     
3. Add the SSH Key to Your GitHub Account:
   - Copy the SSH key to your clipboard: 

     `Get-Content ~/.ssh/id_ed25519.pub | Set-Clipboard`
     
   - Go to GitHub.com, navigate to Settings > SSH and GPG keys > New SSH key.
   - Paste your key, set key type to **Signing** and save it.

4. Push Commits to GitHub:
   - Push your signed commits to GitHub: 
     `git push`

5. Verify Signed Commits on GitHub:
   - Navigate to your repository on GitHub.
   - Click on Commits to see the verification status of your signed commits.



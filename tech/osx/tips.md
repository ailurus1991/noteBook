# Change default shell
First add right directory to file /etc/shells

    # List of acceptable shells for chpass(1).
    # Ftpd will not allow users to connect who are not using
    # one of these shells.

    /bin/bash
    /bin/csh
    /bin/ksh
    /bin/sh
    /bin/tcsh
    /bin/zsh
    /usr/local/bin/fish  // Added

Then change the default shell environment:

    chsh -s /usr/local/bin/fish


# System configuration files
Located at ~/Library/Preferences

#Zsh

	When a “login shell” starts up, it reads the file “/etc/profile” and then “~/.bash_profile” or “~/.bash_login” or “~/.profile” (whichever one exists - it only reads one of these, checking for them in the order mentioned).

	When a “non-login shell” starts up, it reads the file “/etc/bashrc” and then the file “~/.bashrc”.

	Note that when bash is invoked with the name “sh”, it tries to mimic the startup sequence of the Bourne shell (“sh”). In particular, a non-login shell invoked as “sh” does not read any dot files by default. See the bash man page for details.

	**ZSH** must load the .zshrc file first, so we can add the env varilables into .zshrc.
	

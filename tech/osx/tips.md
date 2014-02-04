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

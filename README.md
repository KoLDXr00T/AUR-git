# AUR-git
 packages that i use from AUR :
 - https://aur.archlinux.org/packages/brave-bin
 - https://aur.archlinux.org/packages/github-desktop-bin
 - https://aur.archlinux.org/packages/google-chrome
 - https://aur.archlinux.org/packages/uefitool
 - https://aur.archlinux.org/packages/vesktop
 - https://aur.archlinux.org/packages/virtualbox-bin
 - https://aur.archlinux.org/packages/visual-studio-code-bin
 - https://aur.archlinux.org/packages/vmware-workstation



steps:
- git remote add xrepo https://github.com/xuser/xrepo.git
- git fetch xrepo
- git subtree add --prefix=xrepo xrepo master



debug :
- git ls-remote --heads xrepo

to-do :
- add a script that automatically do the "steps" , add the given package to the packages list and push to origin.
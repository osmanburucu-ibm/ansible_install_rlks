# Installing Rational License Key Server using ANSIBLE

Installing Rational License Key Server using Ansible

## Why, When, What, Who, Where, How

I wanted to learn how to work with ANSIBLE and i learn best when i do something practical. So the decision was to automate the setup/installation of the IBM Rational License Key Server (well actually i started with a different project but this finished first ;).

The original project started at the end of November 2019 with reading:

- Jeff Geerling: Ansible for DevOps
- Lorin Hochstein & Rene Moser: Ansible Up and Running 2nd Ed

In the next weeks/months whenever i had time i did some hacking and lot of the used code i have found during my search on Ansible documentation, Ansible Galaxy, Stackoverflow, and so on. Didn't record the source to mentioned all of them here! My mistake...

This Playbook only checks if the prerequisites for RLKS are available and if not installs them. It does not check if it is ready to use (python, ansible, updated, and so on)

All parameters can be found in group_vars/rlks_server.yml
I have downlaoded the binaries from [IBM Fix Central](https://www.ibm.com/support/fixcentral) using the "Rational Licensing", "Installed Version 8.1.6" and "Platform ALL" to search for the binary. 
In the list or found binaries use [IBM_Rational_License_Key_Server_816](https://www.ibm.com/support/fixcentral/swg/doSelectFixes?options.selectedFixes=IBM_Rational_License_Key_Server_816&continue=1)

Put the downloaded zip file into your "rlks_installfiles_location". Also put your license file there.
If you have purchased Rational products or have asked for evaluations you can download your license file from the [IBM Rational License Key Center](https://licensing.subscribenet.com/control/ibmr/login).

## Open Problems

Sometimes the lmgrd process just fails (service) and i manually stopped and disabled the service (IBM_Rational_License_Key_Server.service) and needed to start it manually with the start script.

## used resources

* [RLKS Installation steps on Knowledge Center](https://www.ibm.com/support/knowledgecenter/SSSTWP_8.1.6/com.ibm.rational.license.doc/topics/c_node_installing.html)
* [RLKS prereqs](https://www.ibm.com/support/knowledgecenter/SSSTWP_8.1.6/com.ibm.rational.license.doc/topics/t_before_install_lic_server_unix.html)

* [Installation Manager command-line arguments for silent mode](https://www.ibm.com/support/knowledgecenter/SSDV2W_1.8.0/com.ibm.silentinstall12.doc/topics/r_silent_inst_cmd_arg.html)
* [Installing a package silently](https://www.ibm.com/support/knowledgecenter/SSDV2W_1.8.5/com.ibm.silentinstall12.doc/topics/t_silent_response_file_install.html)

* [How can I auto-start the Rational License Key Server on RHEL 7.x systems](https://www.ibm.com/support/pages/how-can-i-auto-start-rational-license-key-server-rhel-7x-systems)
* [Restart RLKS after reboot](https://www.ibm.com/support/knowledgecenter/SSSTWP_8.1.6/com.ibm.rational.license.doc/topics/r_restart_lic_server_unix.html)

## trouble shooting

* [RLKS with error "bad ELF interpreter"](https://www.ibm.com/support/pages/installing-rational-license-key-server-red-hat-enterprise-linux-results-bad-elf-interpreter-error)
* [RLKS error /usr/tmp/.flexlm](https://software.intel.com/en-us/articles/cant-make-directory-usrtmpflexlm)
* [FLEXnet licensing error codes](https://media.3ds.com/support/simulia/public/flexlm108/EndUser/chap13.htm)

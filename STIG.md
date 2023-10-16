# How To STIG QRadar 7.5.0 Update 6
### IBM Federal Sales Engineering
### This is a guide provided by an IBM Sales Engineer to STIG QRadar. Permission to post the guide here was given by Christian Reyes.
<p>By: Christian L. Reyes</p>
<p>Date: June 15, 2023</p>
<p>Updated: July 10, 2023</p>

## DISCLAIMER
<p>IBM QRadar 7.5.0 Security Technical Implementation Guide:</p>
<p>https://www.ibm.com/docs/en/qsip/7.5?topic=guide-qradar-configuration-highly-secure-environments</p>
<p>The above guide is only listed as a reference, however, do not use it. This above guide is incorrect and will cause system failure. This has already been tested in the field with a live customer and caused massive downtime and factory reinstall.</p>
<p>NOTE: Pay close attention to this guide. The DISA STIG can completely break QRadar and require emergency remedial action. This remedial action must be done for physical servers from live USB drive and access to the physical server. This remedial action for software appliances requires access to the hypervisor console and QRadar 7.5.0 Update 4 ISO mounted to the VM. These remedial actions will be in how-to-guide "Disaster Recovery after GRUB2 Modification".</p>

## Important Customer Information:
- Administrators will no longer be allowed to login as root, this is a STIG requirement. They will have to login with their newly created non-root user account.
- Secondly, due to AIDE being initialized, every time an install, uninstall, system configuration change occurs, or a deployment action is taken, the aide baseline will have to be updated.
- Third, modifications to the GRUB2 configuration make it so that each time the physical or virtual server is rebooted, the administrator must enter the GRUB2 root user password. If they do not enter this password the system will not start. If this is a physical deployment the administrator must have access to the datacenter, the rack where QRadar is installed, a monitor and keyboard they can plug into the QRadar servers.
- Finally, due to STIG requiring all non-system accounts to have a minimum password age of 1 day and a maximum of 60. The stiguser will have to have the password changed every 60 days.

## Prerequisites
<p>Physical Deployment: ensure you have the latest QRadar ISO loaded onto a USB flash drive and the image was created with Fedora Media Writer (https://fedoraproject.org/workstation/download/). This is critical as no other live media writer works properly, this is the only recommended media writer from IBM Support.</p>
<p>Software Deployment: Ensure the QRadar 7.5.0 Update 4 ISO is loaded onto a datastore which the QRadar Console VM can access.</p>
<p>Backup Critical Information: Ensure the customer has backups off-board from QRadar, either on an external NAS or SSD. If having to help them save information off QRadar and onto a NAS or external media, ensure to copy the contents of the following directories over:</p>

- All config and data backups: /store/backup
- All raw events information: /store/ariel/events
- All raw flows information: /store/ariel/flows

Check size of these directories via `du -sh /store/ariel/flows`. Ensure that the size on the system is the same on the off-board media. 

## Creating Non-Root User
- Open Putty or another terminal emulator
- Enter DNS names or IP Address of QRadar Console, then click "open"
- Login to QRadar Console as root user
- Create `stiguser` or client username of choice
  - `useradd -c 'Admin User' -d /home/stiguser -m -s /bin/bash stiguser`
- Change new user password
  - `passwd stiguser`
- Verify no entries with the `NOPASSWD` statement are uncommented in the `/etc/sudoers` file
  - `more /etc/sudoers | grep NOPASSWD`
- After verifying no entries existed with the `NOPASSWD` statement uncommented, the next step is to add `STIGUSER` to the sudoers file
  - Create `stiguser` file in `/etc/sudoers.d` directory
  - `vi /etc/sudoers.d/stiguser`
  - Type `i` (insert)
  - `stiguser ALL=(ALL) ALL`
  - Press ESC; the `--INSERT--` will disappear
  - `:wq!`
- Close Putty or terminal emulator
- Open Putty to QRadar Console
- Login as stiguser
- Verify stiguser can elevate to root permissions
  - `sudo su`
- After verifying that stiguser can escalate to root permission, type `exit` to return to stiguser
- Create SSH key pair for stiguser
  - `ssh-keygen -b 4096 -t rsa`
- Transfer ssh keys to managed host
  - `ssh-copy-id stiguser@<ipaddress> -o StrictHostKeyChecking=no`
- Test that the stiguser can login to the managed host without using a password
  - `ssh stiguser@<ipaddress>`
- After validating the console can login to the managed host without a password, type exit to return to the QRadar Console and proceed to the next section

## Run Hardening Script

- Login to the QRadar Console via Putty or other terminal emulator as root user
- Change directories to `/opt/qradar/util/stig/bin`
  - `cd /opt/qradar/util/stig/bin`
- Run STIG script
  - `./stig_harden.sh -a`
- Verify completion of script
- Reboot the Console
  - `reboot`
- Verify root user can no longer log directly into the Console by attempting to login as root
- Login to QRadar Console with `stiguser` account
- SSH from the Console to the EPFP via stiguser
  - `ssh stiguser@<ipaddress>`
- Sudo to root
- Change directories to `/opt/qradar/util/stig/bin`
- Run STIG script
- Verify STIG script completed successfully
- Reboot the managed host, this will bring you back to the Console
- Wait a couple minutes, then attempt to login via stiguser from the console to the managed host
- Having run the hardening script on the QRadar Console and managed hosts, validating the ability to login from the Console to the managed host, you may proceed to the next section

## Editing Scripts
- Prior to modifying `iptables_update.sl` script, create a copy of the file and place it within the `/home/stiguser` directory
  - `cp /opt/qradar/bin/iptables_update.pl /home/stiguser`
- After ensuring that a copy of the file is made, next you will edit the `iptables_update.pl` script via vi
  - `vi /opt/qradar/bin/iptables_update.pl`
- Once in edit mode, search for `INPUT`
  - `/INPUT`
- Press the enter key, you will be brought to the exact line which  needs to be modified
- Press the `i` (insert) key, you will know you are in insert mode via the bottom banner saying `--INSERT--`
- Change `INPUT ACCEPT [0:0]` to `INPUT DROP [0:0]`
- Press the ESC key to exit editing mode, this will remove the `--INSERT--` banner
- Save and exit from the `iptables_update.pl`
  - `wq!`
  - Enter
- Run the `iptables_update.pl` script
  - `/opt/qradar/bin/iptables_update.pl`
- Next, the AIDE baseline will be created. Note, this will take some time to finish
  - `aide --init`
- You will know when the baseline is completed when the initialized statement is returned
- To use the AIDE database, the `new` needs to be removed from the aide string, move the `aide.db.new.gz` to `aide.db.gz`
  - `mv -f /var/lib/aide/aide.db.new.gz /var/lib/aide/aide.db.gz`
- Update aide database
  - `aide --update`
- Create a new baseline after updating it
  - `mv -f /var/lib/aide/aide.db.new.gz /var/lib/aide/aide.db.gz`
- IMPORTANT NOTE: THE AIDE UPDATE AND CREATION OF NEW BASELINE MUST BE COMPLETED EACH AND EVERY TIME A NEW INSTALL, UNINSTALL, SYSTEM CONFIGURATION CHANGE OR A DEPLOY ACTION IS TAKEN
- SSH from the Console to managed hosts. The next step is only to be complated on managed hosts
- Once logged into the managed host, next will be to disable packet forwarding for IPv4
  - `sysctl -w net.ipv4.ip_forward=0`
- Disable packet forwarding for IPv6
  - `sysctl -w net.ipv6.conf.all.forwarding=0`
- Edit the `/etc/sysctl.conf` via vi
  - `vi /eetc/sysctl.conf`
- Scroll to the bottom of the file and type the `i` (insert) key, you will enter insert mode
- Add the following lines to the bottom of the file
  - `net.ipv4.ip_forward = 0`
  - `net.ipv6.conf.all.forwarding = 0`
- Press the ESC key to exit editing, this will remove the `--INSERT--` banner
- Save and exit from editing the file
  - `wq!`
- Modify the syslog-ng.conf file to send all audit logs to the Event Processor or Processors
  - `vi /etc/syslog-ng/syslog-ng.conf`
- Search for local4.info, to ensure you modify the correct section
  - `/local4.info`
- You will be brought to the `local4.info` section
- Modify the section with the following lines
  - `destination remote_audit {udp("10.75.26.121" port (514)); };`
  - `log { source(local); filter(local4_info); destination(remote_audit); };`
- This completes the editing scripts section. Proceed to the following section

## GRUB2 Configuration (BIOS)


## GRUB2 Configuration (UEFI)


## Modify Password Age for Non-system Accounts

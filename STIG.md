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

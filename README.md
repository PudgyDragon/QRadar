# IBM QRadar
Creating a place where people can find installation, setup, and troubleshooting for IBM QRadar based off what my team has experienced. Hoping to create a page for Blue Teams to find answers to problems they may experience similar to ours.

# Guides
<table>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/InstallationGuide.md">Installation Guide</a>
    </td>
    <td>
      <p>Installation guide for IBM QRadar on your own hardware, not hardware provided by IBM.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/UpdateRHEL8.md">Update Package 8 (RHEL 8) Upgrade</a>
    </td>
    <td>
      <p>Quick and dirty guide for updating your QRadar device to RHEL 8.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/Data%20Node%20Links">Data Node Links</a>
    </td>
    <td>
      <p>Guide for adding data nodes to console and event processor.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/STIG.md">STIG Guide</a>
    </td>
    <td>
      <p>Guide for doing QRadar STIG for 7.5.0 Update 6.</p>
    </td>
  </tr>  
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/Delete%20All%20Watson%20Investigations">Delete All Watson Investigations</a>
    </td>
    <td>
      <p>Last resort, not recommended. Guide for deleting all Watson investigations.</p>
    </td>
  </tr>  
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/Email%20Server%20Setup">Email Server Setup</a>
    </td>
    <td>
      <p>Guide for setting up an email server on QRadar to allow emails out from the SIEM.</p>
    </td>
  </tr>  
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/ImportExport%20_Contents_as_a_Package">Export Contents as a Package</a>
    </td>
    <td>
      <p>Modified guide for exporting custom content, including DSM and reports.</p>
    </td>
  </tr>  
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/Root%20Password%20Change">Root Password Change</a>
    </td>
    <td>
      <p>Guide for changing the root password</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/Routing%20Rules">Routing Rules</a>
    </td>
    <td>
      <p>Routing rules guide.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/InterimFixUpdateGuide.md">Basic Interim Fix Update Guide</a>
    </td>
    <td>
      <p>Basic guide for installing interim fix to QRadar; bare bones, straight to the point.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/FIPSenable.md">Enabling FIPS</a>
    </td>
    <td>
      <p>Super quick guide for enabling FIPS after RHEL 8 upgrade.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/LostPassword.md">Lost Password</a>
    </td>
    <td>
      <p>Guide for how to reset your password for root or any other user at grub if you lost or forgot it.</p>
    </td>
  </tr>
</table>

# Troubleshooting
<table>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Docker%20Blocked">Docker Blocked</a>
    </td>
    <td>
      <p>McAfee/Trellix on QRadar appliance causues issues for Docker apps. This is a guide to remove it.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Apps%20Not%20on%20Dashboard">Apps Not on Dashboard</a>
    </td>
    <td>
      <p>If your apps aren't showing up on your dashboard, this guide may help.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Can't%20Select%20and%20Delete%20Watson%20Investigation">Can't Select and Delete Watson Investigation</a>
    </td>
    <td>
      <p>Watson investigations that error out are unable to be selected and deleted sometimes. This guide shows the API method for deleting them.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Core%20Services%20Not%20Starting">Core Services Not Starting</a>
    </td>
    <td>
      <p>If services aren't starting after an update installation, this guide may help you.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Email%20Server%20Troubleshoot">Email Server Troubleshoot</a>
    </td>
    <td>
      <p>Guide for troubleshooting emails not being sent out from QRadar.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Uninstall%20Preview%20Fix">Uninstall Preview Fix</a>
    </td>
    <td>
      <p>Guide for fixing the error: Installation or removal of application fails with the error: "another preview/install/uninstall task is currently in process".</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Version%20Update%20Fail">Version Update Fail</a>
    </td>
    <td>
      <p>If you get a yum transaction test failure during a QRadar update, this may be your issue.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Cisco%20ISE%20pxGrid%20Failed">Cisco ISE pxGrid Failed</a>
    </td>
    <td>
      <p>Simple guide for fixing failure to save QRadar/deployment settings for Cisco ISE pxGrid.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/LDAP_SSL_Error.md">LDAP SSL Error</a>
    </td>
    <td>
      <p>Troubleshooting LDAP SSL Error within User Analytics User Import.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/ApplicationError.md">Application Error</a>
    </td>
    <td>
      <p>Application error when trying to us the 'Group By' feature when running searches.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/InterimFixIssues.md">Interim Fix Issues (Update Package 7, Fix 6)</a>
    </td>
    <td>
      <p>Issues that were preventing an Interiim Fix from occurring, to include: full /var/log folders, unable to deploy changes.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/InterimFix3Issues.md">Interim Fix Issues (Update Package 8, Fix 3)</a>
    </td>
    <td>
      <p>Issue that was preventing an Interiim Fix from occurring.</p>
    </td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/IO_Error.md">IO Error</a>
    </td>
    <td>
      <p>IO Error on localhost:32006 when searching.</p>
    </td>
  </tr>
</table>

# Feature Enrichments
<table>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/tree/main/Pulse%20Dashboards">Pulse Dashboards</a>
    </td>
    <td>
      <p>JSON for Pulse Dashboard widgets based on QRadar Vulnerablity Manager being installed, and Tenable ACAS integrated.</p>
    </td>
  </tr>
</table>

<h1>IBM QRadar</h1>
<p>Creating a place where people can find installation, setup, and troubleshooting for IBM QRadar based off what my team has experienced. Hoping to create a page for Blue Teams to find answers to problems they may experience similar to ours.</p>

<h1>Table of Contents</h1>
<h2>Guides</h2>
<table>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/Installation2025.md">Installation Guide</a>
    </td>
    <td>New and improved installation guide created October 2025 using QRadar 7.5 UP13 iso on RHEL 8.10. Guide covers RHEL installation and recommendations.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/STIG_2025.md">NEW STIG Guide</a>
    </td>
    <td>NEW STIG guide used for QRadar 7.5.0 UP14.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/HA_Crossover_Cable.md">Crossover Cable</a>
    </td>
    <td>Guide for configuring crossover cables between your HA pairs.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/UpdateRHEL8.md">Update Package 8 (RHEL 8) Upgrade</a>
    </td>
    <td>Quick and dirty guide for updating your QRadar device to RHEL 8.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/Data%20Node%20Links">Data Node Links</a>
    </td>
    <td>Guide for adding data nodes to console and event processor.</td>
  </tr>   
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/Delete%20All%20Watson%20Investigations">Delete All Watson Investigations</a>
    </td>
    <td>Last resort, not recommended. Guide for deleting all Watson investigations.</td>
  </tr>  
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/Email%20Server%20Setup">Email Server Setup</a>
    </td>
    <td>Guide for setting up an email server on QRadar to allow emails out from the SIEM.</td>
  </tr>  
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/ImportExport%20_Contents_as_a_Package">Export Contents as a Package</a>
    </td>
    <td>Modified guide for exporting custom content, including DSM and reports.</td>
  </tr>  
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/Root%20Password%20Change">Root Password Change</a>
    </td>
    <td>Guide for changing the root password.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/Routing%20Rules">Routing Rules</a>
    </td>
    <td>Routing rules guide.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/InterimFixUpdateGuide.md">Basic Interim Fix Update Guide</a>
    </td>
    <td>Basic guide for installing interim fix to QRadar; bare bones, straight to the point.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/FIPSenable.md">Enabling FIPS</a>
    </td>
    <td>Super quick guide for enabling FIPS after RHEL 8 upgrade.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Guides/LostPassword.md">Lost Password</a>
    </td>
    <td>Guide for how to reset your password for root or any other user at grub if you lost or forgot it.</td>
  </tr>
</table>

<h2>Troubleshooting</h2>
<table>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Failed_to_Locate_SFS.md">Update Failed to Locate SFS</a>
    </td>
    <td>"ERROR: Failed to locate the SFS patch file at..." during an update, not allowing it to start.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Docker%20Blocked">Docker Blocked</a>
    </td>
    <td>McAfee/Trellix on QRadar appliance causues issues for Docker apps. This is a guide to remove it.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Apps%20Not%20on%20Dashboard">Apps Not on Dashboard</a>
    </td>
    <td>If your apps aren't showing up on your dashboard, this guide may help.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Can't%20Select%20and%20Delete%20Watson%20Investigation">Can't Select and Delete Watson Investigation</a>
    </td>
    <td>Watson investigations that error out are unable to be selected and deleted sometimes. This guide shows the API method for deleting them.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Core%20Services%20Not%20Starting">Core Services Not Starting</a>
    </td>
    <td>If services aren't starting after an update installation, this guide may help you.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Email%20Server%20Troubleshoot">Email Server Troubleshoot</a>
    </td>
    <td>Guide for troubleshooting emails not being sent out from QRadar.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Uninstall%20Preview%20Fix">Uninstall Preview Fix</a>
    </td>
    <td>Guide for fixing the error: Installation or removal of application fails with the error: "another preview/install/uninstall task is currently in process".</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Version%20Update%20Fail">Version Update Fail</a>
    </td>
    <td>If you get a yum transaction test failure during a QRadar update, this may be your issue.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/Cisco%20ISE%20pxGrid%20Failed">Cisco ISE pxGrid Failed</a>
    </td>
    <td>Simple guide for fixing failure to save QRadar/deployment settings for Cisco ISE pxGrid.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/LDAP_SSL_Error.md">LDAP SSL Error</a>
    </td>
    <td>Troubleshooting LDAP SSL Error within User Analytics User Import.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/ApplicationError.md">Application Error</a>
    </td>
    <td>Application error when trying to us the 'Group By' feature when running searches.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/InterimFixIssues.md">Interim Fix Issues (Update Package 7, Fix 6)</a>
    </td>
    <td>Issues that were preventing an Interim Fix from occurring, to include: full /var/log folders, unable to deploy changes.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/InterimFix3Issues.md">Interim Fix Issues (Update Package 8, Fix 3)</a>
    </td>
    <td>Issue that was preventing an Interim Fix from occurring.</td>
  </tr>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/blob/main/Troubleshooting/IO_Error.md">IO Error</a>
    </td>
    <td>IO Error on localhost:32006 when searching.</td>
  </tr>
</table>

<h2>Feature Enrichments</h2>
<table>
  <tr>
    <td>
      <a href="https://github.com/PudgyDragon/QRadar/tree/main/Pulse%20Dashboards">Pulse Dashboards</a>
    </td>
    <td>JSON for Pulse Dashboard widgets based on QRadar Vulnerablity Manager being installed, and Tenable ACAS integrated.</td>
  </tr>
</table>

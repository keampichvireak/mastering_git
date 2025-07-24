PS C:\Users\Administrator.ICONIC> repadmin /replsummary
Replication Summary Start Time: 2025-07-24 07:36:21

Beginning data collection for replication summary, this may take
  .....


Source DSA          largest delta    fails/total %%   error
 AD-PICH                   42m:40s    0 /   5    0
 PICH-AD16                 43m:15s    0 /   5    0


Destination DSA     largest delta    fails/total %%   error
 AD-PICH                   43m:15s    0 /   5    0
 PICH-AD16                 42m:40s    0 /   5    0


PS C:\Users\Administrator.ICONIC> repadmin /showrepl PICH-AD16
Default-First-Site-Name\PICH-AD16
DSA Options: IS_GC
Site Options: (none)
DSA object GUID: 06e5abd7-d259-4385-ab9e-e1d5a22de5d1
DSA invocationID: 445b7552-8738-4260-96fc-069cc4eb1e35

==== INBOUND NEIGHBORS ======================================

DC=iconic,DC=local
    Default-First-Site-Name\AD-PICH via RPC
        DSA object GUID: eb572b26-e3df-40f2-b5e7-cd88d07ad9bb
        Last attempt @ 2025-07-24 07:33:38 was successful.

CN=Configuration,DC=iconic,DC=local
    Default-First-Site-Name\AD-PICH via RPC
        DSA object GUID: eb572b26-e3df-40f2-b5e7-cd88d07ad9bb
        Last attempt @ 2025-07-24 06:53:41 was successful.

CN=Schema,CN=Configuration,DC=iconic,DC=local
    Default-First-Site-Name\AD-PICH via RPC
        DSA object GUID: eb572b26-e3df-40f2-b5e7-cd88d07ad9bb
        Last attempt @ 2025-07-24 06:53:41 was successful.

DC=DomainDnsZones,DC=iconic,DC=local
    Default-First-Site-Name\AD-PICH via RPC
        DSA object GUID: eb572b26-e3df-40f2-b5e7-cd88d07ad9bb
        Last attempt @ 2025-07-24 06:53:41 was successful.

DC=ForestDnsZones,DC=iconic,DC=local
    Default-First-Site-Name\AD-PICH via RPC
        DSA object GUID: eb572b26-e3df-40f2-b5e7-cd88d07ad9bb
        Last attempt @ 2025-07-24 07:02:58 was successful.

PS C:\Users\Administrator.ICONIC> netdom query fsmo
Schema master               Pich-AD16.iconic.local
Domain naming master        Pich-AD16.iconic.local
PDC                         Pich-AD16.iconic.local
RID pool manager            Pich-AD16.iconic.local
Infrastructure master       Pich-AD16.iconic.local
The command completed successfully.

PS C:\Users\Administrator.ICONIC> net share

Share name   Resource                        Remark

----------------------------------------------------------------
C$           C:\                             Default share
IPC$                                         Remote IPC
ADMIN$       C:\Windows                      Remote Admin
NETLOGON     C:\Windows\SYSVOL\sysvol\iconic.local\SCRIPTS
                                             Logon server share
SYSVOL       C:\Windows\SYSVOL\sysvol        Logon server share
Users        C:\Users
The command completed successfully.

PS C:\Users\Administrator.ICONIC> net share

Share name   Resource                        Remark

----------------------------------------------------------------
C$           C:\                             Default share
IPC$                                         Remote IPC
ADMIN$       C:\Windows                      Remote Admin
NETLOGON     C:\Windows\SYSVOL\sysvol\iconic.local\SCRIPTS
                                             Logon server share
SYSVOL       C:\Windows\SYSVOL\sysvol        Logon server share
Users        C:\Users
The command completed successfully.

PS C:\Users\Administrator.ICONIC> Get-DnsServerZone

ZoneName                            ZoneType        IsAutoCreate
--------                            --------        ------------
_msdcs.iconic.local                 Primary         False
0.in-addr.arpa                      Primary         True
110.123.10.in-addr.arpa             Primary         False
127.in-addr.arpa                    Primary         True
255.in-addr.arpa                    Primary         True
iconic.local                        Primary         False
TrustAnchors                        Primary         False


PS C:\Users\Administrator.ICONIC> Get-GPO -All


DisplayName      : Default Domain Policy
DomainName       : iconic.local
Owner            : ICONIC\Domain Admins
Id               : 31b2f340-016d-11d2-945f-00c04fb984f9
GpoStatus        : AllSettingsEnabled
Description      :
CreationTime     : 7/23/2025 11:47:20 AM
ModificationTime : 7/24/2025 6:22:24 AM
UserVersion      : AD Version: 0, SysVol Version: 0
ComputerVersion  : AD Version: 11, SysVol Version: 11
WmiFilter        :

DisplayName      : Default Domain Controllers Policy
DomainName       : iconic.local
Owner            : ICONIC\Domain Admins
Id               : 6ac1786c-016f-11d2-945f-00c04fb984f9
GpoStatus        : AllSettingsEnabled
Description      :
CreationTime     : 7/23/2025 11:47:20 AM
ModificationTime : 7/24/2025 6:22:24 AM
UserVersion      : AD Version: 0, SysVol Version: 0
ComputerVersion  : AD Version: 2, SysVol Version: 2
WmiFilter        :



PS C:\Users\Administrator.ICONIC> echo %logonserver%
%logonserver%
PS C:\Users\Administrator.ICONIC> ^C
PS C:\Users\Administrator.ICONIC> ^C
PS C:\Users\Administrator.ICONIC> New-ADUser -Name "TestUser" -S
PS C:\Users\Administrator.ICONIC> Get-ADUser testuser


DistinguishedName : CN=TestUser,CN=Users,DC=iconic,DC=local
Enabled           : True
GivenName         :
Name              : TestUser
ObjectClass       : user
ObjectGUID        : 61d8cdf1-9fcf-4988-aad2-98863c0d5540
SamAccountName    : testuser
SID               : S-1-5-21-1231885725-4090076845-3147392270-21
Surname           :
UserPrincipalName :



PS C:\Users\Administrator.ICONIC> Get-ADUser testuser


DistinguishedName : CN=TestUser,CN=Users,DC=iconic,DC=local
Enabled           : True
GivenName         :
Name              : TestUser
ObjectClass       : user
ObjectGUID        : 61d8cdf1-9fcf-4988-aad2-98863c0d5540
SamAccountName    : testuser
SID               : S-1-5-21-1231885725-4090076845-3147392270-21
Surname           :
UserPrincipalName :



PS C:\Users\Administrator.ICONIC> gpresult /r

Microsoft (R) Windows (R) Operating System Group Policy Result t
© 2016 Microsoft Corporation. All rights reserved.

Created on 7/24/2025 at 8:40:59 AM


RSOP data for ICONIC\Administrator on PICH-AD16 : Logging Mode
---------------------------------------------------------------

OS Configuration:            Primary Domain Controller
OS Version:                  10.0.14393
Site Name:                   Default-First-Site-Name
Roaming Profile:             N/A
Local Profile:               C:\Users\Administrator.ICONIC
Connected over a slow link?: No


COMPUTER SETTINGS
------------------
    CN=PICH-AD16,OU=Domain Controllers,DC=iconic,DC=local
    Last time Group Policy was applied: 7/24/2025 at 8:39:21 AM
    Group Policy was applied from:      Pich-AD16.iconic.local
    Group Policy slow link threshold:   500 kbps
    Domain Name:                        ICONIC
    Domain Type:                        Windows 2008 or later

    Applied Group Policy Objects
    -----------------------------
        Default Domain Controllers Policy
        Default Domain Policy

    The following GPOs were not applied because they were filter
    ------------------------------------------------------------
        Local Group Policy
            Filtering:  Not Applied (Empty)

    The computer is a part of the following security groups
    -------------------------------------------------------
        BUILTIN\Administrators
        Everyone
        BUILTIN\Users
        Certificate Service DCOM Access
        BUILTIN\Pre-Windows 2000 Compatible Access
        Windows Authorization Access Group
        NT AUTHORITY\NETWORK
        NT AUTHORITY\Authenticated Users
        This Organization
        PICH-AD16$
        Domain Controllers
        NT AUTHORITY\ENTERPRISE DOMAIN CONTROLLERS
        Authentication authority asserted identity
        Denied RODC Password Replication Group
        System Mandatory Level


USER SETTINGS
--------------
    CN=Administrator,CN=Users,DC=iconic,DC=local
    Last time Group Policy was applied: 7/24/2025 at 8:02:10 AM
    Group Policy was applied from:      Pich-AD16.iconic.local
    Group Policy slow link threshold:   500 kbps
    Domain Name:                        ICONIC
    Domain Type:                        Windows 2008 or later

    Applied Group Policy Objects
    -----------------------------
        N/A

    The following GPOs were not applied because they were filter
    ------------------------------------------------------------
        Local Group Policy
            Filtering:  Not Applied (Empty)

    The user is a part of the following security groups
    ---------------------------------------------------
        Domain Users
        Everyone
        BUILTIN\Administrators
        BUILTIN\Users
        BUILTIN\Pre-Windows 2000 Compatible Access
        Certificate Service DCOM Access
        NT AUTHORITY\INTERACTIVE
        CONSOLE LOGON
        NT AUTHORITY\Authenticated Users
        This Organization
        LOCAL
        Domain Admins
        Group Policy Creator Owners
        Enterprise Admins
        Schema Admins
        Authentication authority asserted identity
        Denied RODC Password Replication Group
        High Mandatory Level

PS C:\Users\Administrator.ICONIC>

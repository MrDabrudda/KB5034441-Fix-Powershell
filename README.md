# KB5034441-Fix-Powershell
Windows 10 KB5034441 Security Update Fails With 0x80070643 Errors
https://youtu.be/nIf3MG9BK-s

Watch FIX IT...Part II
https://youtu.be/ficOxwCf6Vc

then...

Try running this powershell script "Run as Administrator".  Follow the instructions in this article.
https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/add-update-to-winre?view=windows-11#extend-the-windows-re-partition


https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/add-update-to-winre?view=windows-11#extend-the-windows-re-partition

Extend the Windows RE Partition
The sample script below can be used to increase the size of recovery partition to successfully update Windows Recovery Environment (WinRE). It is recommended to have 250MB of free space in the recovery partition for WinRE updates to install successfully. On devices that may not have adequate free space in the recovery partition, the sample script below can be used to extend the recovery partition by 250 MB.

Reboot your machine before you run the script. This is critical as there may be pending partition operations staged on your machine that will need to be finalized before the script can safely increase the WinRE partition size. After your machine reboots open Powershell as admin and run mkdir <path to new backup directory> to create a backup directory that the script may use in case of failure to restore the original partition. Note the location of this backup directory as the script will ask for your backup path.If you are deploying this at scale, you can bypass the script prompting by using the parameters

" -SkipConfirmation $true -BackupFolder "

For example,

Resize_script.ps1 -SkipConfirmation $true -BackupFolder c:\winre_backup

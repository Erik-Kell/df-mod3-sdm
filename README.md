# df-mod3-sdm
Exercise 1

I began by running the Get-WinEvent -ListLog * command and sending it to the logs.txt file.

I used 'Get-WinEvent -Path C:\Users\S539334\Desktop\DigitalForensics\P3\df-mod3-sdm-1\Exercise 1\logs.txt | Select-String -Pattern 'System' | Out-File -Path C:\Users\S539334\Desktop\DigitalForensics\P3\df-mod3-sdm-1\Exercise 1\selectString.txt'

I used 'Get-WinEvent -ListProvider * | Where-Object { 'System' -In ($_ | Select-Object -ExpandProperty Loglinks | Select-Object -ExpandProperty Logname) } | Format-Table -AutoSize | Out-File -Path C:\Users\S539334\Desktop\DigitalForensics\P3\df-mod3-sdm-1\Exercise 1\whereObject.txt'

I used the command 'Get-Process wmiprvse | Select-Object basePriority,ID,SessionID,WorkingSet | Export-Csv -Path "data.csv"'

Exercise 2

I used the mkdir Directory1 command to maek a directory called directory.

Then I used my notes from another class and copied it and used the 'Copy-Item -Path .\Notes.docx -Destination .\Exercise 2\copiedfile.docx' to copy the file to Exercise 2 folder

I used the command 'Get-Acl C:\Users\S539334\Desktop\DigitalForensics\P3\df-mod3-sdm-1\directory | Export-Csv -Path "getACL.csv"' and export it as a CSV.

Exercise 3

I created a file called password.txt and put it in a folder called evidence. I then encrypted password.txt and put it in a new file using 'Get-Content passwords.txt | ConvertTo-SecureString -AsPlainText -Force | ConvertFrom-SecureString | Out-File C:\Users\S539334\Desktop\DigitalForensics\P3\df-mod3-sdm-1\encryptedPassword.txt'

I then used the command 'Get-Acl -Path C:\Users\S539334\Desktop\DigitalForensics\P3\df-mod3-sdm-1\Exercise3\evidence\password.txt > C:\Users\S539334\Desktop\DigitalForensics\P3\df-mod3-sdm-1\Exercise3\evidence\passwordACL.txt' and placed it in a new file.

I changed the encrypted evidence permission using 'icacls C:\Users\S539334\Desktop\DigitalForensics\P3\df-mod3-sdm-1\Exercise3\encryptedEvidence\encryptedPassword.txt /setintegritylevel h'

I then ran the command 'Get-Acl -Path C:\Users\S539334\Desktop\DigitalForensics\P3\df-mod3-sdm-1\Exercise3\encryptedEvidence\encryptedPassword.txt > C:\Users\S539334\Desktop\DigitalForensics\P3\df-mod3-sdm-1\Exercise3\encryptedEvidence\encryptedPasswordACL.txt' to get the acl of the encrypted file and place it in a new file.

I created a filing system with influence from Cody's filing system for an easy to navigate repo.

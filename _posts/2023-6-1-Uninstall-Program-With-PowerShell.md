---
layout: post
title: Удаление программ на удаленных помьютерах с помощью Powershell
---

Чтобы удалить программы на всех компьютерах домена используется скрипт:
```
$Computers = Get-ADComputer -Filter *
Foreach ($Computer in $Computers)
{
  $Hostname = $Computer.Name
  $apps = Get-WmiObject -Class Win32_Product -ComputerName wks-pc11s22 |where name -Like "WinRar*"
  $apps.uninstall()
}
```
Но эта команда может не видеть всех программ, установленных на компьютере. Если версия Windows более современная (последние 10 и 11), то можно удалять командой `Invoke-Command -ComputerName $Computer.Name -ScriptBlock { Get-Package -Name "WinRar*" | Uninstall-Package}`

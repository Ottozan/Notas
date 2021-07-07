### Criar Atalho Area de trabalho PowerShell

Não conheço nenhum cmdlet nativo no PowerShell, mas você pode usar o objeto com em vez disso:

```bsh
$WshShell = New-Object -comObject WScript.Shell
$Shortcut = $WshShell.CreateShortcut("$Home\Desktop\ColorPix.lnk")
$Shortcut.TargetPath = "C:\Program Files (x86)\ColorPix\ColorPix.exe"
$Shortcut.Save()
```

você pode criar um script do PowerShell salvo como set-shortcut.ps1 em seu $ pwd

```bsh
param ( [string]$SourceExe, [string]$DestinationPath )

$WshShell = New-Object -comObject WScript.Shell
$Shortcut = $WshShell.CreateShortcut($DestinationPath)
$Shortcut.TargetPath = $SourceExe
$Shortcut.Save()
```

e chamá-lo assim

```bsh
Set-ShortCut "C:\Program Files (x86)\ColorPix\ColorPix.exe" "$Home\Desktop\ColorPix.lnk"
```

Se você quiser passar argumentos para o exe de destino, isso pode ser feito:

```bsh
#Set the additional parameters for the shortcut  
$Shortcut.Arguments = "/argument=value"  
```

*antes de* $ Shortcut.Save ().

Por conveniência, aqui está uma versão modificada de set-shortcut.ps1. Ele aceita argumentos como seu segundo parâmetro.

```bsh
param ( [string]$SourceExe, [string]$ArgumentsToSourceExe, [string]$DestinationPath )
$WshShell = New-Object -comObject WScript.Shell
$Shortcut = $WshShell.CreateShortcut($DestinationPath)
$Shortcut.TargetPath = $SourceExe
$Shortcut.Arguments = $ArgumentsToSourceExe
$Shortcut.Save()
```
Adicionar Atalho Usando Windows PowerShell

Windows PowerShell é um shell de linha de comando introduzido no Windows XP e projetado para administradores de sistema. Construído sobre a NET Framework . , Ele pode ser usado tanto por meio de um prompt interativo , um ambiente de script , ou como uma combinação de ambos. Ao usar "cmdlets" - de função única de ferramentas de linha de comando - os usuários podem executar tarefas complexas e compartilhar essa funcionalidade com outros usuários. Instruções
1

Abra o PowerShell ISE .
2

Adicione a linha "$ strDesktopFolder = [ System.Environment ] :: GetFolderPath ( " Desktop " )" a um novo script. Isto irá criar o atalho na área de trabalho por padrão, mas você pode usar outros valores em lugar de "Desktop" - " . Programas" por exemplo, " Meus Documentos " ou
3

Adicione o linha seguinte , onde " shortcut.lnk " é o nome do atalho que você deseja adicionar :

$ objShell = New-Object -com " WScript.Shell"

$ objShortcut = $ objShell . CreateShortcut ( $ strDesktopFolder + "\\ shortcut.lnk " )
4

Adicione a linha "$ objShortcut.TargetPath =" caminho "," onde " caminho " é o local do arquivo que você deseja criar um atalho. Um exemplo seria o seguinte :

C: \\ Windows \\ System32 \\ WindowsPowerShell \\ v1.0 \\ Powershell.exe
5

Adicione a linha "$ objShortcut.Save (). " Salve o arquivo no PowerShell e executá-lo para ativar o script.
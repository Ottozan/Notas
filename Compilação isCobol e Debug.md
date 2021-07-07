### Compilação isCobol e Debug

- Compilar no isCobol com opção de debug

  - ```powershell
    - cd \iscobol_compilacao
    - isrun compila
    
    
    ```

    

- jogar o .class em \\172.16.0.191\class

- copiar o .list em C:\iscobol_compilacao\fontes

- modificar atalho para debug:

  - C:\isCOBOL2018R1\bin\isclient.exe -J-Xms256m -J-Discobol.print.memory=true -port 10998 -hostname 172.16.0.191 -D TEC2500R 

  
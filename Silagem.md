```cobol
       FD  PRO-PAGC
           LABEL RECORD IS STANDARD.
       01  REG-PAGC.
           03 PAGC-CHAVE.
              05 PAGC-CD-PRODUTO          PIC 9(07).
              05 PAGC-CD-CATEGORIA        PIC 9(04).
           03 PAGC-QT-PHECTARE            PIC 9(06)V99999.
           03 PAGC-UN-MEDPHEC             PIC X(03).
      * Unidade de medida por hectare
           03 PAGC-PC-DESCONTO-AV         PIC 9(03)V99.
           03 PAGC-PC-DESCONTO-AP         PIC 9(03)V99.
           03 PAGC-PC-ACRESCIMO-AV        PIC 9(03)V99.
           03 PAGC-PC-ACRESCIMO-AP        PIC 9(03)V99. 
           03 PAGC-FL-TROCA-TROCA         PIC 9(01).
           03 PAGC-FL-INATIVO             PIC 9(01).
```

```cobol
       fd  pro-pago
           label record is standard.
       01  reg-pago.
           03 pago-chave.
              05 pago-cd-categoria        pic 9(04).
              05 pago-cd-tp-pacote        pic 9(04).	
```

```cobol
        FD  PRO-PAGL
           LABEL RECORD IS STANDARD.
       01  REG-PAGL.
           03 PAGL-CHAVE.
              05 PAGL-CD-TP-PACOTE        PIC 9(04).
           03 PAGL-CHAVE-1.
              05 PAGL-NM-TP-PACOTE        PIC X(60).
           03 PAGL-CD-OPERACAO-NF         PIC 9(04).
           03 PAGL-CD-CARTEIRA-NF         PIC 9(04).
           03 PAGL-CD-PRODUTO-BASE        PIC 9(07).
      * (( XFD DATE=YYYYMMDD, USE GROUP ))
           03 PAGL-DT-VIGENCIA-INI.
              05 PAGL-ANO-VIGENCIA-INI    PIC 9(04).
              05 PAGL-MES-VIGENCIA-INI    PIC 9(02).
              05 PAGL-DIA-VIGENCIA-INI    PIC 9(02).
      * (( XFD DATE=YYYYMMDD, USE GROUP ))
           03 PAGL-DT-VIGENCIA-FIM.
              05 PAGL-ANO-VIGENCIA-FIM    PIC 9(04).
              05 PAGL-MES-VIGENCIA-FIM    PIC 9(02).
              05 PAGL-DIA-VIGENCIA-FIM    PIC 9(02).
           03 PAGL-FL-VENCTO              PIC 9(01).
      * 0-Fixo 1-Variavel e fixo
           03 PAGL-DS-NF                  PIC X(60).
           03 PAGL-FL-INATIVA             PIC 9(01).
      * (( XFD DATE=YYYYMMDD, USE GROUP ))
           03 PAGL-DT-INATIVACAO.
              05 PAGL-ANO-INATIVACAO      PIC 9(04).
              05 PAGL-MES-INATIVACAO      PIC 9(02).
              05 PAGL-DIA-INATIVACAO      PIC 9(02).
           03 PAGL-NM-USUARIO             PIC X(15).
```



```cobol
       FD  PRO-CSIL
           LABEL RECORD IS STANDARD.
       01  REG-CSIL.
           03 CSIL-CHAVE.
              05 CSIL-CD-CLIFOR           PIC 9(07).
              05 CSIL-ANO                 PIC 9(04).
           03 CSIL-QT-HA                  PIC 9(08)V99.
           03 CSIL-CD-TECNICO             PIC 9(03).
           03 CSIL-CD-FILIAL              PIC 9(04).
      * (( XFD DATE=YYYYMMDD, USE GROUP ))
           03 CSIL-DT-CADASTRO.
              05 CSIL-ANO-CADASTRO        PIC 9(04).
              05 CSIL-MES-CADASTRO        PIC 9(02).
              05 CSIL-DIA-CADASTRO        PIC 9(02).
           03 CSIL-HR-CADASTRO.
              05 CSIL-HH-CADASTRO         PIC 9(02).
              05 CSIL-MM-CADASTRO         PIC 9(02).
              05 CSIL-SS-CADASTRO         PIC 9(02).
              05 CSIL-MS-CADASTRO         PIC 9(02).
           03 CSIL-NM-USUARIO-CAD         PIC X(15).
           03 CSIL-FL-INATIVO             PIC 9(01).
      * (( XFD DATE=YYYYMMDD, USE GROUP ))
           03 CSIL-DT-INATIVACAO.
              05 CSIL-ANO-INATIVACAO      PIC 9(04).
              05 CSIL-MES-INATIVACAO      PIC 9(02).
              05 CSIL-DIA-INATIVACAO      PIC 9(02).
           03 CSIL-NM-USUARIO             PIC X(15).
```


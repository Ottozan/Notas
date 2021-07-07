Alteração FD TEC-MLEI:

```cobol

   FD  TEC-MLEI
       LABEL RECORD IS STANDARD.
   01  REG-MLEI.
       03 MLEI-CHAVE.
          05 MLEI-CD-CLIFOR           PIC 9(07).
          05 MLEI-NR-NFP              PIC 9(09).
  * (( XFD DATE=YYYYMMDD, USE GROUP ))
          05 MLEI-DT-MOVTO.
             07 MLEI-ANO-MOVTO        PIC 9(04).
             07 MLEI-MES-MOVTO        PIC 9(02).
             07 MLEI-DIA-MOVTO        PIC 9(02).
          05 MLEI-NR-SEQUENCIA        PIC 9(02).
       03 MLEI-NM-CLIFOR              PIC X(60).
       03 MLEI-CD-BALANCA             PIC 9(03).
       03 MLEI-PS-LEITOES             PIC 9(07)V999.
       03 MLEI-VL-LEITOES             PIC 9(09)V99.
       03 MLEI-VL-UNITARIO-MEDIO      PIC 9(07)V9999.
       03 MLEI-NR-GTA                 PIC 9(10).
       03 MLEI-PS-EXCESSO-1-R REDEFINES MLEI-NR-GTA.
          05 MLEI-PS-EXCESSO-1        PIC 9(07)V999.
       03 MLEI-VL-LEITOES-VDA         PIC 9(08)V99.
       03 MLEI-VL-UNITARIO-VDA        PIC 9(06)V9999.
       03 MLEI-CD-TRANSP              PIC 9(07).
       03 MLEI-PLACA                  PIC X(07).
       03 MLEI-PLACA-R REDEFINES MLEI-PLACA.
          05 MLEI-SUFIXO              PIC X(03).
          05 MLEI-NR-PLACA            PIC 9(04).
       03 MLEI-CD-TERMINADOR          PIC 9(07).
       03 MLEI-QT-LEITOES             PIC 9(10).
       03 MLEI-INDICE-MEDIO           PIC 9(02)V9999.
       03 MLEI-CD-TECNICO-ORIG        PIC 9(03).
       03 MLEI-CD-TECNICO-DEST        PIC 9(03).
       03 MLEI-CD-SELECIONADOR        PIC 9(03).
  * (( XFD DATE=HHNNSS ))
       03 MLEI-HORA-CARREG-INICIO     PIC 9(06).
  * (( XFD DATE=HHNNSS ))
       03 MLEI-HORA-CARREG-FIM        PIC 9(06).
       03 MLEI-TP-REGISTRO            PIC X(01).
          88 MLEI-AUTOMATICO VALUE "A".
          88 MLEI-MANUAL VALUE "M".
       03 MLEI-TP-LEITAO              PIC X(01).
          88 MLEI-CRECHARIO VALUE "C".
          88 MLEI-DESMAMADO VALUE "D".
  * MLEI-FILLER => MLEI-PS-LEITAO-MD    
       03 MLEI-PS-LEITAO-MD           PIC 9(05)V99.
       03 MLEI-FL-NF-EMITIDA          PIC 9(01).
       03 MLEI-CD-POCILGA             PIC 9(02).
       03 MLEI-CD-MODALIDADE          PIC 9(01).
       03 MLEI-NR-LOTE                PIC 9(03).
  * (( XFD DATE=YYYYMMDD, USE GROUP ))
       03 MLEI-DT-PESAGEM.
          05 MLEI-ANO-PESAGEM         PIC 9(04).
          05 MLEI-MES-PESAGEM         PIC 9(02).
          05 MLEI-DIA-PESAGEM         PIC 9(02).
       03 MLEI-NR-TABELA              PIC 9(02).
       03 MLEI-ST-SCALA               PIC X(01).
       03 MLEI-PT-SCALA               PIC 9(02)V99.
       03 MLEI-FL-LEITAO-CRECHE       PIC 9(01).
       03 MLEI-CD-POCILGA-ORI         PIC 9(02).
       03 MLEI-CD-MODALIDADE-ORI      PIC 9(01).
       03 MLEI-NR-LOTE-ORI            PIC 9(03).
       03 MLEI-SERIE-NFPR             PIC 9(03).
       03 MLEI-ST-CLASSIFICACAO       PIC X(01).
```



A partir da nota de entrada, pelo código do parceiro e Nota Fiscal de Orígem, ler TEC-MLEI. Data da nota?




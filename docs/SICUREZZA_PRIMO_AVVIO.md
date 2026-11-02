# Primo avvio e avviso di Windows

Stand Gastronomico non è firmato digitalmente. Per questo, al primo avvio, Windows può mostrare il messaggio **“PC protetto da Windows”** di Microsoft Defender SmartScreen.

L'avviso non indica automaticamente che il programma sia dannoso: comunica che Windows non dispone ancora di una reputazione sufficiente per questo file. SmartScreen è una protezione importante e non deve essere disattivato.

## Prima di procedere

Continua solo se entrambe queste condizioni sono vere:

- hai scaricato il programma dalla [release ufficiale](../../releases/latest) del repository Stand Gastronomico;
- il nome e la versione del file ZIP corrispondono a quelli indicati nella release.

Non eseguire file ricevuti via email, messaggistica o siti diversi dal repository ufficiale.

## Come avviare il programma

Se, dopo aver verificato la provenienza del download, compare la schermata SmartScreen:

1. seleziona **Ulteriori informazioni**;
2. controlla ancora di essere sicuro della provenienza del file;
3. seleziona **Esegui comunque**.

Su computer aziendali o gestiti da un'organizzazione, le regole di sicurezza possono impedire questa scelta. In quel caso contatta l'amministratore del computer: non modificare le impostazioni di sicurezza da solo.

## Verifica facoltativa dell'integrità

Nel repository è disponibile il file `SHA256SUMS.txt`, con l'impronta SHA-256 dell'archivio ZIP della versione corrente. È un controllo facoltativo, utile se vuoi verificare che il download non sia stato alterato.

Apri PowerShell nella cartella che contiene il file ZIP ed esegui:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath .\StandGastronomico-1.0.2-win-x64.zip
```

Confronta il valore mostrato con quello riportato in `SHA256SUMS.txt`. I due valori devono essere identici.

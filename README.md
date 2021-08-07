# Powersher Linha de Comando para CSV - Windows Defender:

Get-MpComputerStatus | Select-Object -Property AntivirusSignatureVersion, AntivirusSignatureLastUpdated, AntispywareSignatureLastUpdated, AntispywareSignatureVersion | ConvertTo-csv > antivirus.csv

Exemplo:

PS C:\antivirus> type .\antivirus.csv

#TYPE Selected.Microsoft.Management.Infrastructure.CimInstance

"AntivirusSignatureVersion","AntivirusSignatureLastUpdated","AntispywareSignatureLastUpdated","AntispywareSignatureVersion"
"1.343.1708.0","26/07/2021 07:23:49","26/07/2021 07:23:49","1.343.1708.0"

# Powersher Linha de Comando para JSON - Windows Defender:

import-csv "antivirus.csv" | ConvertTo-Json | Add-Content -Path "antivirus.json"

Exemplo:

 type .\antivirus.json
 
 {
 
    "AntivirusSignatureVersion":  "1.343.1708.0",
    "AntivirusSignatureLastUpdated":  "26/07/2021 07:23:49",
    "AntispywareSignatureLastUpdated":  "26/07/2021 07:23:49",
    "AntispywareSignatureVersion":  "1.343.1708.0"
    
}



# Windows 10 Product Key

Get-CimInstance -ClassName SoftwareLicensingService | Select-Object -ExpandProperty OA3xOriginalProductKey  

# Powersher Linha de Comando para CSV - Windows Defender:

Get-MpComputerStatus | Select-Object -Property AntivirusSignatureVersion, AntivirusSignatureLastUpdated, AntispywareSignatureLastUpdated, AntispywareSignatureVersion | ConvertTo-csv > antivirus.csv

Exemplo:

PS C:\antivirus> type .\antivirus.csv
#TYPE Selected.Microsoft.Management.Infrastructure.CimInstance
"AntivirusSignatureVersion","AntivirusSignatureLastUpdated","AntispywareSignatureLastUpdated","AntispywareSignatureVersion"

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



# scripts-powershell

 ler um arquivo texto
 

#Lendo um arquivo txt
$Text = Get-Content -Path E:\Temp\Projetos.txt 
#Transformando as linhas do arquivo em um array 
$Text.GetType() | Format-Table -AutoSize
#Listando as linhas do arquivo
foreach ($element in $Text) 
{ 
    $element 
}

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

# New-VaasApplication

## SYNOPSIS
Create a new application

## SYNTAX

### NoTarget (Default)
```
New-VaasApplication -Name <String> -Owner <Guid[]> [-Description <String>]
 [-CertificateIssuingTemplate <Hashtable>] [-PassThru] [-VenafiSession <PSObject>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### FqdnIPRange
```
New-VaasApplication -Name <String> -Owner <Guid[]> [-Description <String>]
 [-CertificateIssuingTemplate <Hashtable>] -Fqdn <String[]> -IPRange <String[]> -Port <String[]> [-PassThru]
 [-VenafiSession <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Fqdn
```
New-VaasApplication -Name <String> -Owner <Guid[]> [-Description <String>]
 [-CertificateIssuingTemplate <Hashtable>] -Fqdn <String[]> -Port <String[]> [-PassThru]
 [-VenafiSession <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IPRange
```
New-VaasApplication -Name <String> -Owner <Guid[]> [-Description <String>]
 [-CertificateIssuingTemplate <Hashtable>] -IPRange <String[]> -Port <String[]> [-PassThru]
 [-VenafiSession <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Create a new application with optional details

## EXAMPLES

### EXAMPLE 1
```
New-VaasApplication -Name 'MyNewApp' -Owner '4ba1e64f-12ad-4a34-a0e2-bc4481a56f7d'
```

Create a new application

### EXAMPLE 2
```
New-VaasApplication -Name 'MyNewApp' -Owner '4ba1e64f-12ad-4a34-a0e2-bc4481a56f7d' -CertificateIssuingTemplate @{'9c9618e8-6b4c-4a1c-8c11-902c9b2676d3'=$null} -Description 'this app is awesome' -Fqdn 'me.com' -IPRange '1.2.3.4/24' -Port '443','9443'
```

Create a new application with optional details

### EXAMPLE 3
```
New-VaasApplication -Name 'MyNewApp' -Owner '4ba1e64f-12ad-4a34-a0e2-bc4481a56f7d' -PassThru
```

Create a new application and return the newly created application object

## PARAMETERS

### -Name
Application name

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Owner
List of user and/or team IDs to be owners.
Use Get-VenafiIdentity or Get-VenafiTeam to retrieve the ID.

```yaml
Type: Guid[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Application description

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateIssuingTemplate
Hashtable of issuing templates.
For each key/value pair, the key should be the issuing template id and the value should be the alias.
Null can be provided for the alias which will use the template name as the alias.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fqdn
Fully qualified domain names to assign to the application

```yaml
Type: String[]
Parameter Sets: FqdnIPRange, Fqdn
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPRange
IP ranges to assign to the application

```yaml
Type: String[]
Parameter Sets: FqdnIPRange, IPRange
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Ports to assign to the application.
Required if either Fqdn or IPRange are specified.

```yaml
Type: String[]
Parameter Sets: FqdnIPRange, Fqdn, IPRange
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Return newly created application object

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -VenafiSession
Authentication for the function.
The value defaults to the script session object $VenafiSession created by New-VenafiSession.
A VaaS key can also provided.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $script:VenafiSession
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PSCustomObject, if PassThru provided
## NOTES

## RELATED LINKS

[http://VenafiPS.readthedocs.io/en/latest/functions/New-VaasApplication/](http://VenafiPS.readthedocs.io/en/latest/functions/New-VaasApplication/)

[https://github.com/Venafi/VenafiPS/blob/main/VenafiPS/Public/New-VaasApplication.ps1](https://github.com/Venafi/VenafiPS/blob/main/VenafiPS/Public/New-VaasApplication.ps1)

[https://api.venafi.cloud/webjars/swagger-ui/index.html?urls.primaryName=outagedetection-service#/Applications/applications_create](https://api.venafi.cloud/webjars/swagger-ui/index.html?urls.primaryName=outagedetection-service#/Applications/applications_create)


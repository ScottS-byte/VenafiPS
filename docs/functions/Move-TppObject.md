# Move-TppObject

## SYNOPSIS
Move an object of any type

## SYNTAX

```
Move-TppObject [-SourcePath] <String> [-TargetPath] <String> [[-VenafiSession] <PSObject>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Move an object of any type from one policy to another.
A rename can be done at the same time as the move by providing a full target path including the new object name.

## EXAMPLES

### EXAMPLE 1
```
Move-TppObject -SourceDN '\VED\Policy\My Folder\mycert.company.com' -TargetDN '\VED\Policy\New Folder\mycert.company.com'
Move object to a new Policy folder
```

### EXAMPLE 2
```
Find-VenafiCertificate -Path '\ved\policy\certs' | Move-TppObject -TargetDN '\VED\Policy\New Folder'
Move all objects found in 1 folder to another
```

## PARAMETERS

### -SourcePath
Full path to an existing object in TPP

```yaml
Type: String
Parameter Sets: (All)
Aliases: SourceDN, Path

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TargetPath
New path. 
This can either be an existing policy and the existing object name will be kept or a full path including a new object name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: TargetDN

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VenafiSession
Authentication for the function.
The value defaults to the script session object $VenafiSession created by New-VenafiSession.
A TPP token or VaaS key can also provided.
If providing a TPP token, an environment variable named TPP_SERVER must also be set.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
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

### SourcePath (Path)
## OUTPUTS

### n/a
## NOTES

## RELATED LINKS

[http://VenafiPS.readthedocs.io/en/latest/functions/Move-TppObject/](http://VenafiPS.readthedocs.io/en/latest/functions/Move-TppObject/)

[http://VenafiPS.readthedocs.io/en/latest/functions/Test-TppObject/](http://VenafiPS.readthedocs.io/en/latest/functions/Test-TppObject/)

[https://github.com/Venafi/VenafiPS/blob/main/VenafiPS/Public/Move-TppObject.ps1](https://github.com/Venafi/VenafiPS/blob/main/VenafiPS/Public/Move-TppObject.ps1)

[https://docs.venafi.com/Docs/current/TopNav/Content/SDK/WebSDK/r-SDK-POST-Config-renameobject.php](https://docs.venafi.com/Docs/current/TopNav/Content/SDK/WebSDK/r-SDK-POST-Config-renameobject.php)


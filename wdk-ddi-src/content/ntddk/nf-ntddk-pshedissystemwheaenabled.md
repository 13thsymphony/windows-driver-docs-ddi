---
UID : NF:ntddk.PshedIsSystemWheaEnabled
title : PshedIsSystemWheaEnabled function
author : windows-driver-content
description : The PshedIsSystemWheaEnabled function returns a Boolean value that indicates whether the system is WHEA-enabled.
old-location : whea\pshedissystemwheaenabled.htm
old-project : whea
ms.assetid : d9935605-dc5f-4987-8a5b-b2c2b358dbbf
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : ntddk/PshedIsSystemWheaEnabled, PshedIsSystemWheaEnabled, whearef_492a4370-81bf-411b-bd87-2408f4551b18.xml, PshedIsSystemWheaEnabled function [WHEA Drivers and Applications], whea.pshedissystemwheaenabled
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : Ntddk.h
req.target-type : Universal
req.target-min-winverclnt : Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Pshed.lib
req.dll : Pshed.dll
req.irql : Any
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PshedIsSystemWheaEnabled function
The <b>PshedIsSystemWheaEnabled</b> function returns a Boolean value that indicates whether the system is WHEA-enabled.

## Syntax

````
BOOLEAN PshedIsSystemWheaEnabled(void);
````

## Parameters

This function has no parameters.

## Return Value

A Boolean value that indicates whether the system is WHEA-enabled.

## Remarks

A PSHED plug-in can call the <b>PshedIsSystemWheaEnabled</b> function before it calls the <a href="..\ntddk\nf-ntddk-pshedregisterplugin.md">PshedRegisterPlugin</a> function to verify that the system is WHEA-enabled.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** |  |
| **IRQL** | Any |
| **DDI compliance rules** |  |

## See Also

<a href="..\ntddk\nf-ntddk-pshedregisterplugin.md">PshedRegisterPlugin</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20PshedIsSystemWheaEnabled function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
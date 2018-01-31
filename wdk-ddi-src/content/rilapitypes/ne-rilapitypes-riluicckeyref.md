---
UID : NE:rilapitypes.RILUICCKEYREF
title : RILUICCKEYREF
author : windows-driver-content
description : This enumeration describes the RILUICCAPPTYPE.
old-location : netvista\riluicckeyref.htm
old-project : netvista
ms.assetid : 7812008b-867f-4b17-b715-7a1f10c38368
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILUICCKEYREF, rilapitypes/RIL_UICCKEYREF_UPIN, RIL_UICCKEYREF_NEV, rilapitypes/RIL_UICCKEYREF_PIN2, RIL_UICCKEYREF_PIN1, rilapitypes/RILUICCKEYREF, rilapitypes/RIL_UICCKEYREF_ALW, RIL_UICCKEYREF_UPIN, RIL_UICCKEYREF_ALW, rilapitypes/RIL_UICCKEYREF_NEV, rilapitypes/RIL_UICCKEYREF_PIN1, RIL_UICCKEYREF_PIN2, RILUICCKEYREF enumeration [Network Drivers Starting with Windows Vista], netvista.riluicckeyref
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : rilapitypes.h
req.include-header : Rilapitypes.h
req.target-type : Windows
req.target-min-winverclnt : 
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : RILUICCKEYREF
req.product : Windows 10 or later.
---

# RILUICCKEYREF Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCAPPTYPE.

## Syntax
````
enum RILUICCKEYREF {
  RIL_UICCKEYREF_ALW   = 0x00, 
  RIL_UICCKEYREF_PIN1  = 0x01, 
  RIL_UICCKEYREF_UPIN  = 0x10, 
  RIL_UICCKEYREF_PIN2  = 0x81, 
  RIL_UICCKEYREF_NEV   = 0xff 

};
````

## Constants

<table>

<tr>
<td>RIL_UICCKEYREF_ALW</td>
<td></td>
</tr>

<tr>
<td>RIL_UICCKEYREF_NEV</td>
<td></td>
</tr>

<tr>
<td>RIL_UICCKEYREF_PIN1</td>
<td></td>
</tr>

<tr>
<td>RIL_UICCKEYREF_PIN2</td>
<td></td>
</tr>

<tr>
<td>RIL_UICCKEYREF_UPIN</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h (include Rilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUICCKEYREF enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
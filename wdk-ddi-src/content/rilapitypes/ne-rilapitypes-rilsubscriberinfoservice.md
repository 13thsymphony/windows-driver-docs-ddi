---
UID : NE:rilapitypes.RILSUBSCRIBERINFOSERVICE
title : RILSUBSCRIBERINFOSERVICE
author : windows-driver-content
description : This enumeration describes the RILSUBSCRIBERINFOSERVICE.
old-location : netvista\rilsubscriberinfoservice.htm
old-project : netvista
ms.assetid : 9dcdfbcc-bab8-4621-993b-e64106d0457e
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RIL_SERVICE_FAX, RIL_SERVICE_VOICE, rilapitypes/RILSUBSCRIBERINFOSERVICE, RILSUBSCRIBERINFOSERVICE enumeration [Network Drivers Starting with Windows Vista], netvista.rilsubscriberinfoservice, rilapitypes/RIL_SERVICE_VOICE, RIL_SERVICE_OTHER, rilapitypes/RIL_SERVICE_OTHER, RILSUBSCRIBERINFOSERVICE, rilapitypes/RIL_SERVICE_UNKNOWN, rilapitypes/RIL_SERVICE_FAX, RIL_SERVICE_UNKNOWN
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
req.typenames : RILSUBSCRIBERINFOSERVICE
req.product : Windows 10 or later.
---

# RILSUBSCRIBERINFOSERVICE Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILSUBSCRIBERINFOSERVICE.

## Syntax
````
enum RILSUBSCRIBERINFOSERVICE {
  RIL_SERVICE_UNKNOWN  = 0x01, 
  RIL_SERVICE_VOICE    = 0x02, 
  RIL_SERVICE_FAX      = 0x03, 
  RIL_SERVICE_OTHER    = 0x04 

};
````

## Constants

<table>

<tr>
<td>RIL_SERVICE_FAX</td>
<td></td>
</tr>

<tr>
<td>RIL_SERVICE_MAX</td>
<td></td>
</tr>

<tr>
<td>RIL_SERVICE_OTHER</td>
<td></td>
</tr>

<tr>
<td>RIL_SERVICE_UNKNOWN</td>
<td></td>
</tr>

<tr>
<td>RIL_SERVICE_VOICE</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILSUBSCRIBERINFOSERVICE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
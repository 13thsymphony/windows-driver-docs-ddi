---
UID : NE:rilapitypes.RILSMSFORMAT
title : RILSMSFORMAT
author : windows-driver-content
description : The RILSMSFORMAT enumeration has the following values.
old-location : netvista\rilsmsformat.htm
old-project : netvista
ms.assetid : 2552db76-961c-49ce-8b58-90f525e97d29
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RIL_SMSFORMAT_NONE, rilapitypes/RIL_SMSFORMAT_NONE, rilapitypes/RIL_SMSFORMAT_3GPP, RIL_SMSFORMAT_3GPP, netvista.rilsmsformat, rilapitypes/RIL_SMSFORMAT_3GPP2, RILSMSFORMAT, rilapitypes/RILSMSFORMAT, RIL_SMSFORMAT_MAX, RIL_SMSFORMAT_3GPP2, rilapitypes/RIL_SMSFORMAT_MAX, RILSMSFORMAT enumeration [Network Drivers Starting with Windows Vista]
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
req.typenames : RILSMSFORMAT
req.product : Windows 10 or later.
---

# RILSMSFORMAT Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>The RILSMSFORMAT enumeration has the following values.

## Syntax
````
enum RILSMSFORMAT  {
  RIL_SMSFORMAT_NONE   = 0, 
  RIL_SMSFORMAT_3GPP   = 0x1, 
  RIL_SMSFORMAT_3GPP2  = 0x2, 
  RIL_SMSFORMAT_MAX    = RIL_SMSFORMAT_3GPP2 

};
````

## Constants

<table>

<tr>
<td>RIL_SMSFORMAT_3GPP</td>
<td></td>
</tr>

<tr>
<td>RIL_SMSFORMAT_3GPP2</td>
<td></td>
</tr>

<tr>
<td>RIL_SMSFORMAT_MAX</td>
<td></td>
</tr>

<tr>
<td>RIL_SMSFORMAT_NONE</td>
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

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILSMSFORMAT enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
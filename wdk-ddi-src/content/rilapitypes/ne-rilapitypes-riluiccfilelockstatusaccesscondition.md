---
UID : NE:rilapitypes.RILUICCFILELOCKSTATUSACCESSCONDITION
title : RILUICCFILELOCKSTATUSACCESSCONDITION
author : windows-driver-content
description : This enumeration describes the RILUICCFILELOCKSTATUSACCESSCONDITION.
old-location : netvista\riluiccfilelockstatusaccesscondition.htm
old-project : netvista
ms.assetid : 994bfab2-6bab-4aeb-87a9-a5b825efcb23
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RIL_UICCFILEACCESSCONDITION_RFU4, netvista.riluiccfilelockstatusaccesscondition, rilapitypes/RIL_UICCFILEACCESSCONDITION_RFU3, RIL_UICCFILEACCESSCONDITION_ALW, rilapitypes/RIL_UICCFILEACCESSCONDITION_NEV, rilapitypes/RIL_UICCFILEACCESSCONDITION_PIN1, RIL_UICCFILEACCESSCONDITION_RFU3, RIL_UICCFILEACCESSCONDITION_ADM6, RIL_UICCFILEACCESSCONDITION_PIN2, RILUICCFILELOCKSTATUSACCESSCONDITION enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_UICCFILEACCESSCONDITION_ALW, rilapitypes/RIL_UICCFILEACCESSCONDITION_PIN2, rilapitypes/RIL_UICCFILEACCESSCONDITION_RFU4, RIL_UICCFILEACCESSCONDITION_ADM5, rilapitypes/RIL_UICCFILEACCESSCONDITION_ADM5, RIL_UICCFILEACCESSCONDITION_NEV, rilapitypes/RILUICCFILELOCKSTATUSACCESSCONDITION, rilapitypes/RIL_UICCFILEACCESSCONDITION_ADM6, RIL_UICCFILEACCESSCONDITION_PIN1, RILUICCFILELOCKSTATUSACCESSCONDITION
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
req.typenames : RILUICCFILELOCKSTATUSACCESSCONDITION
req.product : Windows 10 or later.
---

# RILUICCFILELOCKSTATUSACCESSCONDITION Enumeration
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCFILELOCKSTATUSACCESSCONDITION.

## Syntax
````
enum RILUICCFILELOCKSTATUSACCESSCONDITION {
  RIL_UICCFILEACCESSCONDITION_ALW   = 0x00, 
  RIL_UICCFILEACCESSCONDITION_PIN1  = 0x01, 
  RIL_UICCFILEACCESSCONDITION_PIN2  = 0x02, 
  RIL_UICCFILEACCESSCONDITION_RFU3  = 0x03, 
  RIL_UICCFILEACCESSCONDITION_RFU4  = 0x04, 
  RIL_UICCFILEACCESSCONDITION_ADM5  = 0x05, 
  RIL_UICCFILEACCESSCONDITION_ADM6  = 0x06, 
  RIL_UICCFILEACCESSCONDITION_NEV   = 0x07 

};
````

## Constants

<table>

<tr>
<td>RIL_UICCFILEACCESSCONDITION_ADM5</td>
<td></td>
</tr>

<tr>
<td>RIL_UICCFILEACCESSCONDITION_ADM6</td>
<td></td>
</tr>

<tr>
<td>RIL_UICCFILEACCESSCONDITION_ALW</td>
<td></td>
</tr>

<tr>
<td>RIL_UICCFILEACCESSCONDITION_MAX</td>
<td></td>
</tr>

<tr>
<td>RIL_UICCFILEACCESSCONDITION_NEV</td>
<td></td>
</tr>

<tr>
<td>RIL_UICCFILEACCESSCONDITION_PIN1</td>
<td></td>
</tr>

<tr>
<td>RIL_UICCFILEACCESSCONDITION_PIN2</td>
<td></td>
</tr>

<tr>
<td>RIL_UICCFILEACCESSCONDITION_RFU3</td>
<td></td>
</tr>

<tr>
<td>RIL_UICCFILEACCESSCONDITION_RFU4</td>
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUICCFILELOCKSTATUSACCESSCONDITION enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
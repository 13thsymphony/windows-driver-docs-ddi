---
UID: NS:rilapitypes.RILUICCFILELOCKSTATUS
title: RILUICCFILELOCKSTATUS
author: windows-driver-content
description: This structure represents RILUICCFILELOCKSTATUS.
old-location: netvista\riluiccfilelockstatus.htm
old-project: netvista
ms.assetid: 348e44f2-4386-4b45-9d68-c996d471578f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILUICCFILELOCKSTATUS, rilapitypes/RILUICCFILELOCKSTATUS, RILUICCFILELOCKSTATUS, RILUICCFILELOCKSTATUS structure [Network Drivers Starting with Windows Vista], netvista.riluiccfilelockstatus"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILUICCFILELOCKSTATUS
product: Windows
targetos: Windows
req.typenames: "*LPRILUICCFILELOCKSTATUS, RILUICCFILELOCKSTATUS"
req.product: Windows 10 or later.
---

# RILUICCFILELOCKSTATUS structure
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents RILUICCFILELOCKSTATUS.

## Syntax
````
struct RILUICCFILELOCKSTATUS {
  DWORD                                cbSize;
  DWORD                                dwParams;
  RILUICCFILELOCKSTATUSACCESSCONDITION dwAccessCondition;
  BYTE                                 bPinRef[MAXNUM_PINREF];
};
````

## Members


`bPinRef`

A byte array specifying the application PIN references made by this application (keys for PIN1 and PIN2).

`cbSize`

The size of the structure in bytes.

`dwAccessCondition`

Specifies the access condition for the file. These values correspond to those specified in ETSI TS 102 221 section 9.5.1. The access condition should be one of <a href="..\rilapitypes\ne-rilapitypes-riluiccfilelockstatusaccesscondition.md">RILUICCFILELOCKSTATUSACCESSCONDITION</a>.

`dwParams`

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-riluiccfilelockstatusparammask.md">RILUICCFILELOCKSTATUSPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUICCFILELOCKSTATUS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
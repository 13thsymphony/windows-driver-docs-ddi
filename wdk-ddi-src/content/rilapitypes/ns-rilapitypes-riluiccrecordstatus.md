---
UID: NS:rilapitypes.RILUICCRECORDSTATUS
title: RILUICCRECORDSTATUS
author: windows-driver-content
description: This structure represents RILUICCRECORDSTATUS.
old-location: netvista\riluiccrecordstatus.htm
old-project: netvista
ms.assetid: 073fe700-ea6d-4d29-8751-66b27714f72d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILUICCRECORDSTATUS, RILUICCRECORDSTATUS, RILUICCRECORDSTATUS structure [Network Drivers Starting with Windows Vista], netvista.riluiccrecordstatus, rilapitypes/RILUICCRECORDSTATUS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Ntddrilapitypes.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILUICCRECORDSTATUS
product: Windows
targetos: Windows
req.typenames: RILUICCRECORDSTATUS, *LPRILUICCRECORDSTATUS
req.product: Windows 10 or later.
---

# RILUICCRECORDSTATUS structure
<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents RILUICCRECORDSTATUS.

## Syntax
````
struct RILUICCRECORDSTATUS {
  DWORD                 cbSize;
  DWORD                 dwParams;
  RILUICCRECORDTYPE     dwRecordType;
  DWORD                 dwItemCount;
  DWORD                 dwSize;
  RILUICCFILELOCKSTATUS fileLockStatus[MAXNUM_EFACCESSTYPES];
};
````

## Members


`cbSize`

The size of the structure in bytes.

`dwItemCount`

Specifies the number of items in the UICC file.

`dwParams`

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-riluiccrecordstatusparammask.md">RILUICCRECORDSTATUSPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.

`dwRecordType`

Specifies the UICC file type, one of <a href="..\rilapitypes\ne-rilapitypes-riluiccrecordtype.md">RILUICCRECORDTYPE</a>.

`dwSize`

Specifies the size of each item in bytes.

`fileLockStatus`

An array of type <a href="..\rilapitypes\ns-rilapitypes-riluiccfilelockstatus.md">RILUICCFILELOCKSTATUS</a> that describes the access condition and a list of key references for each operation (READ, UPDATE, ACTIVATE, and DEACTIVATE in that order) on that file.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Ntddrilapitypes.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUICCRECORDSTATUS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
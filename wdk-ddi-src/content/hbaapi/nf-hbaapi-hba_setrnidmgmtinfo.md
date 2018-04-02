---
UID: NF:hbaapi.HBA_SetRNIDMgmtInfo
title: HBA_SetRNIDMgmtInfo function
author: windows-driver-content
description: The HBA_SetRNIDMgmtInfo routine programs the HBA to return the indicated request node identification information data (RNID).
old-location: storage\hba_setrnidmgmtinfo.htm
old-project: storage
ms.assetid: 0c4fbe80-03f2-4ee0-b766-c1ccaa8e83c2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_SetRNIDMgmtInfo, HBA_SetRNIDMgmtInfo routine [Storage Devices], fibreHBA_rtns_ebe3859b-fe8c-42c6-a4a7-9d756489d818.xml, hbaapi/HBA_SetRNIDMgmtInfo, storage.hba_setrnidmgmtinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_SetRNIDMgmtInfo
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---


# HBA_SetRNIDMgmtInfo function
The <b>HBA_SetRNIDMgmtInfo</b> routine programs the HBA to return the indicated request node identification information data (RNID).

## Syntax

```
HBA_STATUS HBA_API HBA_SetRNIDMgmtInfo(
  IN HBA_HANDLE   Handle,
  IN HBA_MGMTINFO *pInfo
);
```

## Parameters

`Handle`

TBD

`pInfo`

TBD


## Return Value

The <b>HBA_SetRNIDMgmtInfo</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_SetRNIDMgmtInfo</b> returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if the HBA was successfully programmed to return the specified RNID. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the routine from programming the HBA to return the specified RNID. 

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | hbaapi.h (include Hbaapi.h) |
| **Library** | Hbaapi.lib |
| **DLL** | Hbaapi.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
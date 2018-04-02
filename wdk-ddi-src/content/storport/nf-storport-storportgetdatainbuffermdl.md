---
UID: NF:storport.StorPortGetDataInBufferMdl
title: StorPortGetDataInBufferMdl function
author: windows-driver-content
description: Returns an MDL associated with the input data buffer of a SCSI request block (SRB).
old-location: storage\storportgetdatainbuffermdl.htm
old-project: storage
ms.assetid: 9D41810A-7698-4462-802D-79EF793C9A9D
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortGetDataInBufferMdl, StorPortGetDataInBufferMdl routine [Storage Devices], storage.storportgetdatainbuffermdl, storport/StorPortGetDataInBufferMdl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Storport.lib
req.dll: 
req.irql: Any
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortGetDataInBufferMdl
product:
- Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortGetDataInBufferMdl function
Returns an MDL associated with the input data buffer  of a SCSI request block (SRB).

## Syntax

```
ULONG StorPortGetDataInBufferMdl(
  PVOID               HwDeviceExtension,
  PSCSI_REQUEST_BLOCK Srb,
  PVOID               *Mdl
);
```

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA).

`Srb`

The request block to containing the data described by the MDL pointed to by <i>Mdl</i>.

`Mdl`

A pointer to  an MDL address to receive the MDL for <i>Srb</i>.


## Return Value

A status value indicating the result of the notification. This can be one of these values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The MDL for <i>Srb</i> was successfully returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The pointer value in <i>Mdl</i> is NULL.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.  |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |
| **IRQL** | Any |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj553719">StorPortGetDataInBufferScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj553720">StorPortGetDataInBufferSystemAddress</a>
---
UID: NF:ndis.NdisMCloseLog
title: NdisMCloseLog function
author: windows-driver-content
description: NdisMCloseLog releases resources that were used for logging.
old-location: netvista\ndismcloselog.htm
old-project: netvista
ms.assetid: a4b2bf1a-f15d-409f-bd5f-84dbf8dadc09
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NdisMCloseLog, NdisMCloseLog, miniport_logging_ref_ad3e4ea9-60c4-46b7-ac68-84517df279e0.xml, netvista.ndismcloselog, NdisMCloseLog function [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCloseLog (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisMCloseLog (NDIS 5.1)) in Windows   XP.
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
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisMCloseLog
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisMCloseLog function
<b>NdisMCloseLog</b> releases resources that were used for logging.

## Syntax

````
VOID NdisMCloseLog(
  _In_ NDIS_HANDLE LogHandle
);
````

## Parameters

`LogHandle`

Specifies the handle returned by 
     <a href="..\ndis\nf-ndis-ndismcreatelog.md">NdisMCreateLog</a>.


## Return Value

None

## Remarks

<b>NdisMCloseLog</b> closes the temporary log file allocated by 
    <b>NdisMCreateLog</b> and releases all resources associated with the driver's logging operations when a
    miniport driver is unloading.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCloseLog (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisMCloseLog (NDIS 5.1)) in Windows   XP.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ndis\nf-ndis-ndismwritelogdata.md">NdisMWriteLogData</a>



<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>



<a href="..\ndis\nf-ndis-ndismflushlog.md">NdisMFlushLog</a>



<a href="..\ndis\nf-ndis-ndismcreatelog.md">NdisMCreateLog</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCloseLog function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
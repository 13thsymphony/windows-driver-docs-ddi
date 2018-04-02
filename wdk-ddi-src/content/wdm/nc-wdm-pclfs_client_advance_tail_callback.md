---
UID: NC:wdm.PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK
title: PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK
author: windows-driver-content
description: The ClfsAdvanceTailCallback function advances the base log sequence number (LSN) of the client's log.
old-location: kernel\clfsadvancetailcallback.htm
old-project: kernel
ms.assetid: e5c3ac56-9e9f-40b8-b8a8-2eb4d41bca52
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ClfsAdvanceTailCallback, ClfsAdvanceTailCallback callback function [Kernel-Mode Driver Architecture], Clfs_management_86e7d14f-866d-4023-9f97-d495ac16989f.xml, PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK, kernel.clfsadvancetailcallback, wdm/ClfsAdvanceTailCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.irql: Called at IRQL <= APC_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	ClfsAdvanceTailCallback
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---


# PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK callback function
The <i>ClfsAdvanceTailCallback</i> function advances the base log sequence number (LSN) of the client's log.

## Syntax

```
PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK PclfsClientAdvanceTailCallback;

NTSTATUS PclfsClientAdvanceTailCallback(
  PLOG_FILE_OBJECT LogFile,
  PCLFS_LSN TargetLsn,
  PVOID ClientData
)
{...}
```

## Parameters

`LogFile`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a> structure that represents the CLFS log stream whose tail should be advanced.

`TargetLsn`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541824">CLFS_LSN</a> structure that contains the LSN that the client should advance its tail to or beyond.

`ClientData`

A pointer to client-supplied information. You specify this data in the <b>AdvanceTailCallbackData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541841">CLFS_MGMT_CLIENT_REGISTRATION</a> structure.


## Return Value

The <i>ClfsAdvanceTailCallback</i> function should return either STATUS_PENDING or an error status. A return value of STATUS_PENDING indicates that the request to move the client's log tail will be completed asynchronously. The <b>ClfsMgmtAdvanceTailCallback</b> function must not return STATUS_SUCCESS, even if it completes synchronously.

## Remarks

The <i>ClfsAdvanceTailCallback</i> function is called when CLFS management requests that the client advance its log tail.

The <i>ClfsAdvanceTailCallback</i> function must only perform a minimal amount of processing before returning. For example, the <i>ClfsAdvanceTailCallback</i> function might follow this procedure:

<ol>
<li>
If the request cannot be processed, return an error status.

</li>
<li>
If the request can be processed, create and queue a work item to perform the actions that are required to move the client's tail, and then return STATUS_PENDING. For more information on queuing a worker thread, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564587">System Worker Threads</a>.

</li>
</ol>
When a client calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541642">ClfsMgmtRegisterManagedClient</a> routine to register with CLFS management, the client provides both a pointer to the <i>ClfsAdvanceTailCallback</i> function and the custom data that will be passed as a parameter to the <i>ClfsAdvanceTailCallback</i> function when this function is called.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows Server 2003 R2, Windows Vista, and later versions of Windows.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | Called at IRQL <= APC_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541841">CLFS_MGMT_CLIENT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540773">ClfsAdvanceLogBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541642">ClfsMgmtRegisterManagedClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541669">ClfsMgmtTailAdvanceFailure</a>
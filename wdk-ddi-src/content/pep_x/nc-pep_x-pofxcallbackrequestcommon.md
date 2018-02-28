---
UID: NC:pep_x.POFXCALLBACKREQUESTCOMMON
title: POFXCALLBACKREQUESTCOMMON
author: windows-driver-content
description: The RequestCommon routine is a generic request handler.
old-location: kernel\requestcommon.htm
old-project: kernel
ms.assetid: 16699B3D-D02B-4D01-9EBE-003C92B06D31
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: POFXCALLBACKREQUESTCOMMON, RequestCommon, RequestCommon routine [Kernel-Mode Driver Architecture], kernel.requestcommon, pepfx/RequestCommon
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: "<= HIGH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	pepfx.h
api_name:
-	RequestCommon
product: Windows
targetos: Windows
req.typenames: PO_FX_CORE_DEVICE, *PPO_FX_CORE_DEVICE
---


# POFXCALLBACKREQUESTCOMMON callback function
The <b>RequestCommon</b> routine is a generic request handler.

## Syntax

```
POFXCALLBACKREQUESTCOMMON Pofxcallbackrequestcommon;

NTSTATUS Pofxcallbackrequestcommon(
  ULONG RequestId,
  PVOID Data
)
{...}
```

## Parameters

`RequestId`

A request ID that specifies the operation being requested.

`Data`

A pointer to a data structure that contains the input data and/or result data for the request specified by the <i>RequestId</i> parameter.


## Return Value

<b>RequestCommon</b> returns STATUS_SUCCESS if the request is successfully handled. Otherwise, it returns an appropriate error status code.

## Remarks

This routine is implemented by the <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) and is called by the platform extension plug-in (PEP). The <b>RequestCommon</b> member of the <a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to an <b>RequestCommon</b> routine.

A PEP can call this routine at IRQL &lt;= HIGH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10.  |
| **Target Platform** | Windows |
| **Header** | pep_x.h (include Pep_x.h) |
| **IRQL** | "<= HIGH_LEVEL" |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POFXCALLBACKREQUESTCOMMON routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
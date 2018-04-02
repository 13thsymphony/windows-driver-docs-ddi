---
UID: NF:wdfcore.WDF_REL_TIMEOUT_IN_SEC
title: WDF_REL_TIMEOUT_IN_SEC function
author: windows-driver-content
description: The WDF_REL_TIMEOUT_IN_SEC function converts a specified number of seconds to a relative time value.
old-location: wdf\wdf_rel_timeout_in_sec.htm
old-project: wdf
ms.assetid: 40d0f5bf-609e-4609-8785-261b087fa372
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFTimerObjectRef_2c5d8c96-3c4d-484d-9d60-656c4c4a7cc5.xml, WDF_REL_TIMEOUT_IN_SEC, WDF_REL_TIMEOUT_IN_SEC function, kmdf.wdf_rel_timeout_in_sec, wdf.wdf_rel_timeout_in_sec, wdfcore/WDF_REL_TIMEOUT_IN_SEC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcore.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: None
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	None
-	None.dll
api_name:
-	WDF_REL_TIMEOUT_IN_SEC
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---


# WDF_REL_TIMEOUT_IN_SEC function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REL_TIMEOUT_IN_SEC</b> function converts a specified number of seconds to a relative time value.

## Syntax

```
WDF_EXTERN_C_START LONGLONG WDF_REL_TIMEOUT_IN_SEC(
  ULONGLONG Time
);
```

## Parameters

`Time`

The number of seconds to convert.


## Return Value

<b>WDF_REL_TIMEOUT_IN_SEC</b> returns the relative time value, in system time units (100-nanosecond intervals), that represents the number of seconds that <i>Time</i> specifies.

## Remarks

A relative time is a time value that is relative to the current system time. For example, if a caller passes a relative time value of five seconds to a function that accepts a time-out value, the function will time out five seconds after it is called.


#### Examples

The following code example specifies a relative timeout value of 5 seconds for an I/O request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_REQUEST_SEND_OPTIONS  requestSendOptions;
...
requestSendOptions.Timeout = WDF_REL_TIMEOUT_IN_SEC(5);
...</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfcore.h (include Wdf.h) |
| **Library** | None |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551211">WDF_ABS_TIMEOUT_IN_SEC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a>
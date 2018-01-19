---
UID : NF:wdm.KdEnableDebugger
title : KdEnableDebugger function
author : windows-driver-content
description : The KdEnableDebugger routine re-enables the kernel debugger after a call to the KdDisableDebugger routine disables the kernel debugger.
old-location : devtest\kdenabledebugger.htm
old-project : devtest
ms.assetid : 90151c0d-24c9-4304-bdcf-30dc89397905
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : KdEnableDebugger
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h
req.target-type : Universal
req.target-min-winverclnt : Available in Microsoft Windows 2000 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KdEnableDebugger
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : Any level
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# KdEnableDebugger function
The <b>KdEnableDebugger</b> routine re-enables the kernel debugger after a call to the <a href="..\wdm\nf-wdm-kddisabledebugger.md">KdDisableDebugger</a> routine disables the kernel debugger.

## Syntax

````
NTSTATUS KdEnableDebugger(void);
````

## Parameters

This function has no parameters.

## Return Value

<b>KdEnableDebugger</b> returns STATUS_SUCCESS if the kernel debugger was successfully re-enabled. Otherwise, the return value can be one of the following error status codes:S

TATUS_ACCESS_DENIED

STATUS_DEBUGGER_INACTIVE

<b>KdEnableDebugger</b> returns STATUS_SUCCESS if the kernel debugger was successfully re-enabled. Otherwise, the return value can be one of the following error status codes:S

TATUS_ACCESS_DENIED

STATUS_DEBUGGER_INACTIVE

<b>KdEnableDebugger</b> returns STATUS_SUCCESS if the kernel debugger was successfully re-enabled. Otherwise, the return value can be one of the following error status codes:S

TATUS_ACCESS_DENIED

STATUS_DEBUGGER_INACTIVE

## Remarks

If the operating system was booted with no debug controls, <b>KdEnableDebugger</b> returns STATUS_DEBUGGER_INACTIVE.

If the kernel debugger is blocked (that is, the <b>KdBlockEnable</b> system variable is set to a value other than <b>FALSE</b>), <b>KdEnableDebugger</b> returns STATUS_ACCESS_DENIED.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-kddisabledebugger.md">KdDisableDebugger</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20KdEnableDebugger routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID: NF:rxce.RxCeInitiateVCDisconnect
title: RxCeInitiateVCDisconnect function
author: windows-driver-content
description: RxCeInitiateVCDisconnect initiates a disconnect on the virtual circuit.
old-location: ifsk\rxceinitiatevcdisconnect.htm
old-project: ifsk
ms.assetid: 978ddc02-9ff0-4798-879c-e4bc99081dcb
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxCeInitiateVCDisconnect, RxCeInitiateVCDisconnect function [Installable File System Drivers], ifsk.rxceinitiatevcdisconnect, rxce/RxCeInitiateVCDisconnect, rxref_1893aa5d-dda4-49f7-b4bb-dc9bdd75154a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxce.h
req.include-header: Rxce.h
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
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxce.h
api_name:
-	RxCeInitiateVCDisconnect
product: Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---


# RxCeInitiateVCDisconnect function
<b>RxCeInitiateVCDisconnect</b> initiates a disconnect on the virtual circuit.

## Syntax

```
NTSTATUS RxCeInitiateVCDisconnect(
  IN PRXCE_VC pVc
);
```

## Parameters

`pVc`

A pointer to the virtual circuit structure to be disconnected.


## Return Value

<b>RxCeInitiateVCDisconnect</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The allocation of nonpaged pool memory needed by this routine failed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>pVc</i> parameter passed to this routine was invalid. 

</td>
</tr>
</table>

## Remarks

<b>RxCeInitiateVCDisconnect</b> must be called in the context of a system worker thread.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | rxce.h (include Rxce.h) |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553439">RxCeBuildVC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554332">RxCeTearDownVC</a>
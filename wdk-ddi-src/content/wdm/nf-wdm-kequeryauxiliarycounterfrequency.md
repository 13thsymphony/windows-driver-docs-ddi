---
UID: NF:wdm.KeQueryAuxiliaryCounterFrequency
title: KeQueryAuxiliaryCounterFrequency function
author: windows-driver-content
description: The KeQueryAuxiliaryCounterFrequency routine returns frequency of the auxiliary counter in units of Hz.
old-location: kernel\kequeryauxiliarycounterfrequency.htm
old-project: kernel
ms.assetid: E7F9549D-F222-42BF-B82B-B0DA0F6BC60F
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeQueryAuxiliaryCounterFrequency
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeQueryAuxiliaryCounterFrequency
req.alt-loc: Hal.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: Hal.dll
req.irql: Any level
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeQueryAuxiliaryCounterFrequency function



## -description
The <b>KeQueryAuxiliaryCounterFrequency</b> routine returns frequency of the auxiliary counter in units of Hz.



## -syntax

````
NTSTATUS KeQueryAuxiliaryCounterFrequency(
  _Out_opt_ PULONG64 AuxiliaryCounterFrequency
);
````


## -parameters

### -param AuxiliaryCounterFrequency [out, optional]

A pointer to a variable to which <b>KeQueryAuxiliaryCounterFrequency</b> writes the auxiliary counter frequency, in ticks per second. This parameter can be NULL.


## -returns
<b>KeQueryAuxiliaryCounterFrequency</b> can return one of the following:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The query succeeded.
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>Auxiliary counter is not supported.

 


## -remarks
Call this routine to programmatically determine whether auxiliary counter is supported. In that call, if you do not need the frequency of the counter, pass NULL. If not supported, the routine returns STATUS_NOT_SUPPORTED.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 10.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Hal.dll</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-keconvertperformancecountertoauxiliarycounter.md">KeConvertPerformanceCounterToAuxiliaryCounter</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keconvertauxiliarycountertoperformancecounter.md">KeConvertAuxiliaryCounterToPerformanceCounter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryAuxiliaryCounterFrequency routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


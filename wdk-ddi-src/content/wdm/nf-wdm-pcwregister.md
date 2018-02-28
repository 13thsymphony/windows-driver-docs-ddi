---
UID: NF:wdm.PcwRegister
title: PcwRegister function
author: windows-driver-content
description: The PcwRegister function registers the caller as a provider of the specified counter set.
old-location: devtest\pcwregister.htm
old-project: devtest
ms.assetid: 40fdb77c-bd6b-4ecd-a9c8-fd5e5b2adc80
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PcwRegister, PcwRegister function [Driver Development Tools], devtest.pcwregister, km_pcw_5204b626-3251-4c63-bd89-be1470980960.xml, wdm/PcwRegister
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PcwRegister
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# PcwRegister function
The <b>PcwRegister</b> function registers the caller as a provider of the specified counter set.

## Syntax

````
NTSTATUS PcwRegister(
  _Out_ PPCW_REGISTRATION             *Registration,
  _In_  PPCW_REGISTRATION_INFORMATION Info
);
````

## Parameters

`Registration`

A pointer to a PCW_REGISTRATION structure. Receives the handle to the newly allocated registration. The pointer is referenced before the function returns. The caller is responsible to dereference the pointer.

`Info`

A pointer to a PCW_REGISTRATION_INFORMATION structure that contains the details about the counter set being registered.


## Return Value

This function returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The counter set is successfully registered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The <i>Version</i> specified by <i>Info</i> does not match the supported value for this version of Windows.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTEGER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The number of the counters exposed by this registration exceeds the space available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
There is not enough space available to allocate memory for the counters

</td>
</tr>
</table>

## Remarks

The provider calls this function to create a new registration. The registration is added to the counter set's registration list. All the input arguments are captured so that the caller does not have to keep a copy of them.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<=APC_LEVEL" |

## See Also

<a href="..\wdm\nf-wdm-pcwunregister.md">PcwUnregister</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20PcwRegister function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
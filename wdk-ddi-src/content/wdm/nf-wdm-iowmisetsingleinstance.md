---
UID: NF:wdm.IoWMISetSingleInstance
title: IoWMISetSingleInstance function
author: windows-driver-content
description: The IoWMISetSingleInstance routine sets the values for properties within the data block instance that matches the specified WMI class and instance name.
old-location: kernel\iowmisetsingleinstance.htm
old-project: kernel
ms.assetid: 043b51cd-816f-414d-85b2-2573c42393e4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoWMISetSingleInstance routine [Kernel-Mode Driver Architecture], kernel.iowmisetsingleinstance, k104_35479ad6-0f12-4d8b-b375-faa271cf65fd.xml, wdm/IoWMISetSingleInstance, IoWMISetSingleInstance
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating system.
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoWMISetSingleInstance
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoWMISetSingleInstance function
The <b>IoWMISetSingleInstance</b> routine sets the values for properties within the data block instance that matches the specified WMI class and instance name.

## Syntax

````
NTSTATUS IoWMISetSingleInstance(
  _In_ PVOID           DataBlockObject,
  _In_ PUNICODE_STRING InstanceName,
  _In_ ULONG           Version,
  _In_ ULONG           ValueBufferSize,
  _In_ PVOID           ValueBuffer
);
````

## Parameters

`DataBlockObject`

Pointer to a WMI data block object. The caller opens the data block object for the WMI class with the <a href="..\wdm\nf-wdm-iowmiopenblock.md">IoWMIOpenBlock</a> routine. The object must be opened with the WMIGUID_SET access right.

`InstanceName`

Specifies the name of the instance of the data block. This value corresponds to the value of the <b>InstanceName</b> property for the block.

`Version`

Reserved for future use. Callers must set this parameter to zero.

`ValueBufferSize`

Specifies the size, in bytes, of the buffer passed in the <i>ValueBuffer</i> parameter.

`ValueBuffer`

Pointer to the buffer that contains the new values for the properties within the data block.


## Return Value

The routine returns an NTSTATUS code. Possible return values include:

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
The operation succeeded. The values of the WMI data block instance properties are updated to the contents of the buffer pointed to by the <i>ValueBuffer</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WMI_GUID_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No drivers implement the WMI class.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WMI_INSTANCE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No driver implements an instance of the WMI class with <b>InstanceName</b> property equal to the value specified in the <i>InstanceName</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WMI_READ_ONLY</b></dt>
</dl>
</td>
<td width="60%">
All properties of the WMI class are read-only.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WMI_SET_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The driver that implements the WMI data block instance is unable to update the instance.

</td>
</tr>
</table>

## Remarks

<b>IoWMISetSingleInstance</b> determines which drivers might support the specified WMI class and instance name, and issues an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550831">IRP_MN_CHANGE_SINGLE_INSTANCE</a> request to each such driver. The driver that exports the data block instance with matching <b>InstanceName</b> property updates its data block instance. Note that a data block might have both read-only and read/write properties. In this case, only the read/write properties will be updated and STATUS_SUCCESS is returned.

Drivers can also use the <a href="..\wdm\nf-wdm-iowmisetsingleitem.md">IoWMISetSingleItem</a> routine to update a single property within the class instance.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of the Windows operating system. Available in Windows XP and later versions of the Windows operating system. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\wdm\nf-wdm-iowmiopenblock.md">IoWMIOpenBlock</a>



<a href="..\wdm\nf-wdm-iowmisetsingleitem.md">IoWMISetSingleItem</a>



<a href="..\wdm\nf-wdm-iowmiquerysingleinstance.md">IoWMIQuerySingleInstance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550831">IRP_MN_CHANGE_SINGLE_INSTANCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoWMISetSingleInstance routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
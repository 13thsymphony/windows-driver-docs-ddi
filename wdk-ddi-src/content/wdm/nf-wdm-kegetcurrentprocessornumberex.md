---
UID: NF:wdm.KeGetCurrentProcessorNumberEx
title: KeGetCurrentProcessorNumberEx function
author: windows-driver-content
description: The KeGetCurrentProcessorNumberEx routine gets the processor number of the logical processor that the caller is running on.
old-location: kernel\kegetcurrentprocessornumberex.htm
old-project: kernel
ms.assetid: eb66a17e-2e85-453c-8b39-091f0dc8c29b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeGetCurrentProcessorNumberEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeGetCurrentProcessorNumberEx
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeGetCurrentProcessorNumberEx function



## -description
The <b>KeGetCurrentProcessorNumberEx</b> routine gets the processor number of the logical processor that the caller is running on. 



## -syntax

````
ULONG KeGetCurrentProcessorNumberEx(
  _Out_opt_ PPROCESSOR_NUMBER ProcNumber
);
````


## -parameters

### -param ProcNumber [out, optional]

A pointer to a caller-allocated buffer into which the routine writes a <a href="..\miniport\ns-miniport-_processor_number.md">PROCESSOR_NUMBER</a> structure that identifies the current logical processor. This structure contains the group number and the group-relative processor number. You can set this parameter to <b>NULL</b> if you do not need this information. 


## -returns
<b>KeGetCurrentProcessorNumberEx</b> returns the systemwide processor index of the logical processor that the caller is running on. 


## -remarks
If <i>ProcNumber</i> is non-<b>NULL</b>, the buffer that is pointed to by <i>ProcNumber</i> must be large enough to contain a PROCESSOR_NUMBER structure. In contrast to this structure, which contains a group number and a group-relative processor number, the return value is a processor index that identifies the processor across the entire multiprocessor system.

For example, if a multiprocessor system contains two groups, and each group contains 64 logical processors, the processor numbers in each group range from 0 to 63, but the systemwide processor indexes range from 0 to 127.

A related routine, <a href="..\ntddk\nf-ntddk-kegetcurrentprocessornumber.md">KeGetCurrentProcessorNumber</a>, returns the current processor number, but this routine, unlike <b>KeGetCurrentProcessorNumberEx</b>, does not provide a group number for the processor. In Windows 7 and later versions of the Windows operating system, <b>KeGetCurrentProcessorNumber</b> returns the group-relative processor number if the caller is running on a processor in group 0, which is compatible with the behavior of this routine in earlier versions of Windows that do not support groups. However, if the caller is running on a processor in any group other than group 0, this routine returns a number that is less than the number of processors in group 0. This behavior ensures that the return value is less than the return value of the <a href="..\wdm\nf-wdm-kequeryactiveprocessorcount.md">KeQueryActiveProcessorCount</a> routine. Existing drivers that call <b>KeGetCurrentProcessorNumber</b> and that use no group-oriented features run correctly in multiprocessor systems that have two or more groups. However, drivers that use any group-oriented features in Windows 7 and later versions of the Windows operating system should call <b>KeGetCurrentProcessorNumberEx</b> instead of <b>KeGetCurrentProcessorNumber</b>. 


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
Available in Windows 7 and later versions of Windows. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Ntddk.h, Wdm.h, or Ntddk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
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
<a href="..\ntddk\nf-ntddk-kegetcurrentprocessornumber.md">KeGetCurrentProcessorNumber</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kequeryactiveprocessorcount.md">KeQueryActiveProcessorCount</a>
</dt>
<dt>
<a href="..\miniport\ns-miniport-_processor_number.md">PROCESSOR_NUMBER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeGetCurrentProcessorNumberEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


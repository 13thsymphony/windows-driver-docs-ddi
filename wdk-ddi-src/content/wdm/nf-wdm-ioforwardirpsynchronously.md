---
UID: NF.wdm.IoForwardIrpSynchronously
title: IoForwardIrpSynchronously function
author: windows-driver-content
description: The IoForwardIrpSynchronously routine sends an IRP to a specified driver and waits for that driver to complete the IRP.
old-location: kernel\ioforwardirpsynchronously.htm
old-project: kernel
ms.assetid: c3e7c79f-2a0d-4011-887d-0f01537cd6e6
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: IoForwardIrpSynchronously
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoForwardIrpSynchronously
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PnpIrpCompletion
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# IoForwardIrpSynchronously function



## -description
The <b>IoForwardIrpSynchronously</b> routine sends an IRP to a specified driver and waits for that driver to complete the IRP.



## -syntax

````
BOOLEAN IoForwardIrpSynchronously(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp
);
````


## -parameters

### -param DeviceObject [in]

Specifies the device object of the driver to which the IRP is sent. 


### -param Irp [in]

Specifies the IRP to send. 


## -returns
<b>IoForwardIrpSynchronously</b> returns <b>TRUE</b> if the IRP is sent successfully. Otherwise, it returns <b>FALSE</b>.


## -remarks
Use the <b>IoForwardIrpSynchronously</b> routine to synchronously forward the current IRP to the next driver in the stack. (To asynchronously forward the IRP, use the <a href="kernel.iocopycurrentirpstacklocationtonext">IoCopyCurrentIrpStackLocationToNext</a>, <a href="kernel.iocalldriver">IoCallDriver</a>, and <a href="kernel.iosetcompletionroutine">IoSetCompletionRoutine</a> routines.)

The <b>IoForwardIrpSynchronously</b> routine copies the current stack location to the next stack location. That stack location is then used as the current stack location by the driver specified in <i>DeviceObject</i>. If no next stack location is available, the routine returns <b>FALSE</b>. If the routine returns <b>TRUE</b>, then the IRP has been sent to the specified driver, and that driver has completed its processing of this IRP. 


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
Available in Windows XP and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
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
&lt;= APC_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.wdm_pnpirpcompletion">PnpIrpCompletion</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.iocopycurrentirpstacklocationtonext">IoCopyCurrentIrpStackLocationToNext</a>
</dt>
<dt>
<a href="kernel.iocalldriver">IoCallDriver</a>
</dt>
<dt>
<a href="kernel.iosetcompletionroutine">IoSetCompletionRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoForwardIrpSynchronously routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


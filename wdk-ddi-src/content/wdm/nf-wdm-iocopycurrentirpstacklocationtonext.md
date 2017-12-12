---
UID: NF.wdm.IoCopyCurrentIrpStackLocationToNext
title: IoCopyCurrentIrpStackLocationToNext function
author: windows-driver-content
description: The IoCopyCurrentIrpStackLocationToNext routine copies the IRP stack parameters from the current I/O stack location to the stack location of the next-lower driver.
old-location: kernel\iocopycurrentirpstacklocationtonext.htm
old-project: kernel
ms.assetid: f1940737-4543-4e48-8a4a-90430b16890a
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: IoCopyCurrentIrpStackLocationToNext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoCopyCurrentIrpStackLocationToNext
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# IoCopyCurrentIrpStackLocationToNext function



## -description
The <b>IoCopyCurrentIrpStackLocationToNext</b> routine copies the IRP stack parameters from the current I/O stack location to the stack location of the next-lower driver.



## -syntax

````
VOID IoCopyCurrentIrpStackLocationToNext(
  _Inout_ PIRP Irp
);
````


## -parameters

### -param Irp [in, out]

A pointer to the IRP.


## -returns
None


## -remarks
A driver calls <b>IoCopyCurrentIrpStackLocationToNext</b> to copy the IRP parameters from its stack location to the next-lower driver's stack location.

After calling this routine, a driver typically sets an I/O completion routine with <a href="kernel.iosetcompletionroutine">IoSetCompletionRoutine</a> before passing the IRP to the next-lower driver with <a href="kernel.iocalldriver">IoCallDriver</a>. Drivers that pass on their IRP parameters but do not set an I/O completion routine should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a> instead of this routine.

If your driver calls <b>IoSkipCurrentIrpStackLocation</b>, be careful not to modify the <a href="kernel.io_stack_location">IO_STACK_LOCATION</a> structure in a way that could unintentionally affect the lower driver or the system's behavior with respect to that driver. In particular, your driver should not modify the <b>IO_STACK_LOCATION</b> structure's <b>Parameters</b> union, and should not call the <a href="kernel.iomarkirppending">IoMarkIrpPending</a> routine.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 2000.

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
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.io_stack_location">IO_STACK_LOCATION</a>
</dt>
<dt>
<a href="kernel.iocalldriver">IoCallDriver</a>
</dt>
<dt>
<a href="kernel.iomarkirppending">IoMarkIrpPending</a>
</dt>
<dt>
<a href="kernel.iosetcompletionroutine">IoSetCompletionRoutine</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoCopyCurrentIrpStackLocationToNext routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


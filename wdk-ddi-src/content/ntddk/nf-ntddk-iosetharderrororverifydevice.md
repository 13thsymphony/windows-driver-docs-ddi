---
UID: NF:ntddk.IoSetHardErrorOrVerifyDevice
title: IoSetHardErrorOrVerifyDevice function
author: windows-driver-content
description: Lower-level drivers call the IoSetHardErrorOrVerifyDevice routine to identify a removable media device that has encountered an error, so that a file system driver can prompt the user to verify that the medium is valid.
old-location: kernel\iosetharderrororverifydevice.htm
old-project: kernel
ms.assetid: 67f41d3e-d306-400b-9970-88c62f0f7a7f
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoSetHardErrorOrVerifyDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoSetHardErrorOrVerifyDevice
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
req.irql: <=DISPATCH_LEVEL
req.typenames: *PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT
---

# IoSetHardErrorOrVerifyDevice function



## -description
Lower-level drivers call the <b>IoSetHardErrorOrVerifyDevice</b> routine to identify a removable media device that has encountered an error, so that a file system driver can prompt the user to verify that the medium is valid.



## -syntax

````
VOID IoSetHardErrorOrVerifyDevice(
  _In_ PIRP           Irp,
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters

### -param Irp [in]

Pointer to the IRP for which the driver encountered a user-induced error.


### -param DeviceObject [in]

Pointer to the target device to be verified for the I/O operation. 


## -returns
None


## -remarks
Lower-level drivers for removal media devices must call <b>IoSetHardErrorOrVerifyDevice</b> before completing an IRP, if a call to <a href="..\wdm\nf-wdm-ioiserroruserinduced.md">IoIsErrorUserInduced</a> returns <b>TRUE</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563916">Supporting Removable Media</a>.

Subsequently, a file system driver will use information supplied in the specified device object to send a dialog box to the user, who can correct the error and retry the operation or cancel it.

The IRP passed to <b>IoSetHardErrorOrVerifyDevice</b> must be associated with a thread. Therefore, before a driver calls <b>IoSetHardErrorOrVerifyDevice</b>, it must verify that <i>irp</i><b>-&gt;Tail.Overlay</b>.Thread is not <b>NULL</b>. If the value is <b>NULL</b>, <b>IoSetHardErrorOrVerifyDevice</b> must not be called using the current IRP. Instead, the driver should check all IRPs subsequently received and processed, until one is received for which <i>irp</i><b>-&gt;Tail.Overlay</b>.Thread is not <b>NULL</b>. At that point, <b>IoSetHardErrorOrVerifyDevice</b> can be called. 


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
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
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
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-ioiserroruserinduced.md">IoIsErrorUserInduced</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-ioraiseharderror.md">IoRaiseHardError</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-ioraiseinformationalharderror.md">IoRaiseInformationalHardError</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoSetHardErrorOrVerifyDevice routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


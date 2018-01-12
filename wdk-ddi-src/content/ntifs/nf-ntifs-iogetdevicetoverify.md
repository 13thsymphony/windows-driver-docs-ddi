---
UID: NF:ntifs.IoGetDeviceToVerify
title: IoGetDeviceToVerify function
author: windows-driver-content
description: The IoGetDeviceToVerify routine returns a pointer to the device object, representing a removable-media device, that is the target of the given thread's I/O request.
old-location: ifsk\iogetdevicetoverify.htm
old-project: ifsk
ms.assetid: 3dcd33ac-845a-4519-b697-5917687a9672
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IoGetDeviceToVerify
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoGetDeviceToVerify
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IrqlIoDispatch
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
req.typenames: TOKEN_TYPE
---

# IoGetDeviceToVerify function



## -description
The <b>IoGetDeviceToVerify</b> routine returns a pointer to the device object, representing a removable-media device, that is the target of the given thread's I/O request.



## -syntax

````
PDEVICE_OBJECT IoGetDeviceToVerify(
  _In_ PETHREAD Thread
);
````


## -parameters

### -param Thread [in]

Pointer to the thread for which a highest-level driver is attempting to verify the validity of the media on which the thread has opened a file.


## -returns
<b>IoGetDeviceToVerify</b> returns a pointer to the device object representing a device on which the media should be verified, or it returns <b>NULL</b>.


## -remarks
In general, highest-level drivers, particularly file systems, are most likely to call this routine.

An underlying removable-media device driver is responsible for notifying higher-level drivers, particularly the file system, when the media appears to have changed since the last access to the target device. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563916">Supporting Removable Media</a>.


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
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
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
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj157234">IrqlIoDispatch</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-ioiserroruserinduced.md">IoIsErrorUserInduced</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-iosetharderrororverifydevice.md">IoSetHardErrorOrVerifyDevice</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-psgetcurrentthread.md">PsGetCurrentThread</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-iosetdevicetoverify.md">IoSetDeviceToVerify</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoGetDeviceToVerify routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


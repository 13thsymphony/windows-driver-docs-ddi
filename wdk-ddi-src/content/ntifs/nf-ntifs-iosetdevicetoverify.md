---
UID: NF.ntifs.IoSetDeviceToVerify
title: IoSetDeviceToVerify
author: windows-driver-content
description: The IoSetDeviceToVerify routine specifies a device object to be verified. The specified device object represents a removable media device.
old-location: ifsk\iosetdevicetoverify.htm
old-project: ifsk
ms.assetid: 509eb91d-7f34-4ebb-bc37-56889c15a1b3
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IoSetDeviceToVerify
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoSetDeviceToVerify
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
req.iface: 
---

# IoSetDeviceToVerify function



## -description
<p>The <b>IoSetDeviceToVerify</b> routine specifies a device object to be verified. The specified device object represents a removable media device.</p>


## -syntax

````
VOID IoSetDeviceToVerify(
  _In_     PETHREAD       Thread,
  _In_opt_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters
<dl>

### -param Thread [in]

<dd>
<p>A pointer to the thread.</p>
</dd>

### -param DeviceObject [in, optional]

<dd>
<p>A pointer to the device object for a removable-media device. Can be <b>NULL</b>.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>A file system calls <b>IoSetDeviceToVerify</b> to indicate that a given device object, representing a removable-media device, needs to be verified.</p>

<p>A file system must verify a volume when it receives notification from an underlying removable-media device driver that the media appears to have changed since the last access to the target device. </p>

<p>Before using <b>IoSetDeviceToVerify</b> and <a href="..\ntifs\nf-ntifs-ioverifyvolume.md">IoVerifyVolume</a>, driver writers are strongly encouraged to study the way these routines are used in the FASTFAT sample.</p>

<p>For more information about removable-media devices, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563916">Supporting Removable Media</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.wdm_irqliodispatch">IrqlIoDispatch</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-iogetdevicetoverify.md">IoGetDeviceToVerify</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--irp.md">IRP</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-psgetcurrentthread.md">PsGetCurrentThread</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ioverifyvolume.md">IoVerifyVolume</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoSetDeviceToVerify routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

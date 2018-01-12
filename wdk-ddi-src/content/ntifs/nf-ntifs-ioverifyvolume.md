---
UID: NF:ntifs.IoVerifyVolume
title: IoVerifyVolume function
author: windows-driver-content
description: The IoVerifyVolume routine sends a volume verify request to the given removable-media device.
old-location: ifsk\ioverifyvolume.htm
old-project: ifsk
ms.assetid: 46e29607-ee09-4db4-a501-68a3bc678e16
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IoVerifyVolume
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
req.alt-api: IoVerifyVolume
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
req.irql: < DISPATCH_LEVEL
req.typenames: TOKEN_TYPE
---

# IoVerifyVolume function



## -description
The <b>IoVerifyVolume</b> routine sends a volume verify request to the given removable-media device. 



## -syntax

````
NTSTATUS IoVerifyVolume(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ BOOLEAN        AllowRawMount
);
````


## -parameters

### -param DeviceObject [in]

Pointer to the device object for the device on which the volume is to be verified. 


### -param AllowRawMount [in]

Set to <b>TRUE</b> if this verify request is being issued on behalf of a DASD open request and a raw mount should be performed if the verify request fails.


## -returns
<b>IoVerifyVolume</b> can return one of the following NTSTATUS values: 
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl><dl>
<dt><b>STATUS_WRONG_VOLUME</b></dt>
</dl> 


## -remarks
<b>IoVerifyVolume</b> sends a volume verify request to the given removable-media device. 

If the verify operation fails, the I/O Manager sends a volume mount request to the device. 

Before using <a href="..\ntifs\nf-ntifs-iosetdevicetoverify.md">IoSetDeviceToVerify</a> and <b>IoVerifyVolume</b>, driver writers are strongly encouraged to study the way these routines are used in the FASTFAT sample. 

For more information about removable-media devices, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563916">Supporting Removable Media</a>. 


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
&lt; DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-iogetdevicetoverify.md">IoGetDeviceToVerify</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-iosetdevicetoverify.md">IoSetDeviceToVerify</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoVerifyVolume routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlBalanceReads
title: FsRtlBalanceReads function
author: windows-driver-content
description: The FsRtlBalanceReads routine signals to a fault-tolerant disk driver that it is now safe to start balancing reads from a mirrored drive.
old-location: ifsk\fsrtlbalancereads.htm
old-project: ifsk
ms.assetid: 06d55d5d-1b2e-43f9-8d01-2f81489cc861
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlBalanceReads
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
req.alt-api: FsRtlBalanceReads
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
req.irql: PASSIVE_LEVEL
req.typenames: TOKEN_TYPE
---

# FsRtlBalanceReads function



## -description
The <b>FsRtlBalanceReads</b> routine signals to a fault-tolerant disk driver that it is now safe to start balancing reads from a mirrored drive. 



## -syntax

````
NTSTATUS FsRtlBalanceReads(
  _In_ PDEVICE_OBJECT TargetDevice
);
````


## -parameters

### -param TargetDevice [in]

A pointer to the device object from which the device starts the balanced read. 


## -returns
<b>FsRtlBalanceReads</b> returns STATUS_INVALID_DEVICE_REQUEST if the device is not a mirror. 


## -remarks
<b>FsRtlBalanceReads</b> signals to a fault-tolerant disk driver that it is safe to start balancing reads from a mirrored drive. A file system typically calls <b>FsRtlBalanceReads</b> for a newly mounted volume once it has determined that the volume is clean. 


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
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-ccistheredirtydata.md">CcIsThereDirtyData</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlBalanceReads routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE
title: IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE
author: windows-driver-content
description: This I/O control function deauthenticates the magnetic stripe reader (MSR).
old-location: pos\ioctl_point_of_service_msr_deauthenticate_device.htm
old-project: pos
ms.assetid: 796ee8e7-693f-41dd-ad09-cb3c21779ab9
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _PosPropertyId, PosPropertyId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE
req.alt-loc: pointofservicedriverinterface.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: PosPropertyId
---

# IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE IOCTL



## -description
This I/O control function deauthenticates the magnetic stripe reader (MSR).



## -ioctlparameters

### -input-buffer
Pointer to the input buffer, a <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_msr_deauthenticate_device.md">MSR_DEAUTHENTICATE_DEVICE</a> variable that contains the challenge token.


### -input-buffer-length
Size of the input buffer, in bytes. Set to <b>sizeof(MSR_DEAUTHENTICATE_DEVICE)</b>.


### -output-buffer
Not used with this operation; set to <b>NULL</b>.


### -output-buffer-length
Not used with this operation; set to <b>0</b> (zero).


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
Returns TRUE if successful; otherwise, returns FALSE.

To get extended error information, call <a href="http://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Pointofservicedriverinterface.h (include Pointofservicedriverinterface.h)</dt>
</dl>
</td>
</tr>
</table>
---
UID: NE.sffdisk.SFFDISK_DPCMD
title: SFFDISK_DPCMD
author: windows-driver-content
description: The SFFDISK_DPCMD enumeration lists the operations performed by an IOCTL_SFFDISK_DEVICE_PASSWORD request.
old-location: sd\sffdisk_dpcmd.htm
old-project: SD
ms.assetid: 55a034e7-68fa-4f4a-b7c6-da215405375a
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: SERCX_BUFFER_DESCRIPTOR,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: sffdisk.h
req.include-header: Sffdisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SFFDISK_DPCMD
req.alt-loc: sffdisk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level.
req.iface: 
req.product: Windows 10 or later.
---

# SFFDISK_DPCMD enumeration



## -description
<p>The SFFDISK_DPCMD enumeration lists the operations performed by an <a href="https://msdn.microsoft.com/library/windows/hardware/ff537273">IOCTL_SFFDISK_DEVICE_PASSWORD</a> request.</p>


## -syntax

````
typedef enum  { 
  SFFDISK_DP_IS_SUPPORTED           = 0,
  SFFDISK_DP_SET_PASSWORD           = 1,
  SFFDISK_DP_LOCK_DEVICE            = 2,
  SFFDISK_DP_UNLOCK_DEVICE          = 3,
  SFFDISK_DP_RESET_DEVICE_ALL_DATA  = 4
} SFFDISK_DPCMD;
````


## -enum-fields
<dl>

### -field SFFDISK_DP_IS_SUPPORTED

<dd>
<p>The operation requests verification from the card that it supports command class 7.</p>
</dd>

### -field SFFDISK_DP_SET_PASSWORD

<dd>
<p>The operation sets the password.</p>
</dd>

### -field SFFDISK_DP_LOCK_DEVICE

<dd>
<p>The operation locks the device.</p>
</dd>

### -field SFFDISK_DP_UNLOCK_DEVICE

<dd>
<p>The operation unlocks the device.</p>
</dd>

### -field SFFDISK_DP_RESET_DEVICE_ALL_DATA

<dd>
<p>The operation resets the device.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Sffdisk.h (include Sffdisk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/7ded516a-0369-4aa9-bb77-c17065b373fb">SFFDISK_DEVICE_PASSWORD_DATA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SD\buses]:%20SFFDISK_DPCMD enumeration%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

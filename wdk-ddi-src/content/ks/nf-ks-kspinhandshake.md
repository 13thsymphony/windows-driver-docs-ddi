---
UID: NF.ks.KsPinHandshake
title: KsPinHandshake function
author: windows-driver-content
description: The KsPinHandshake function attempts a protocol handshake with a connected pin.
old-location: stream\kspinhandshake.htm
old-project: stream
ms.assetid: 31855688-9221-4128-89c5-dbc4f3e6f794
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KsPinHandshake
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsPinHandshake
req.alt-loc: ks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# KsPinHandshake function



## -description
The<b> KsPinHandshake </b>function attempts a protocol handshake with a connected pin.



## -syntax

````
NTSTATUS KsPinHandshake(
  _In_  PKSPIN       Pin,
  _In_  PKSHANDSHAKE In,
  _Out_ PKSHANDSHAKE Out
);
````


## -parameters

### -param Pin [in]

A pointer to the <a href="stream.kspin">KSPIN</a> structure that is initiating the handshake. The handshake request is passed on to the pin connected to this object.


### -param In [in]

A pointer to the <a href="..\ks\ns-ks-kshandshake.md">KSHANDSHAKE</a> structure containing the handshake information to be passed to the connected pin.


### -param Out [out]

A pointer to a <a href="..\ks\ns-ks-kshandshake.md">KSHANDSHAKE</a> structure that is filled in with handshake information by the connected pin.


## -returns
<b>KsPinHandshake </b>returns STATUS_SUCCESS if the connected pin is accepting the negotiated connection. Otherwise, it returns an appropriate error code.


## -remarks
Protocol handshakes can be used to negotiate private interfaces between two pins that are both AVStream pins. 

Connections between AVStream pins are performed using this type of handshake.


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
Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
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
<a href="stream.kspingetconnectedpininterface">KsPinGetConnectedPinInterface</a>
</dt>
<dt>
<a href="..\ks\ni-ks-ioctl_ks_handshake.md">IOCTL_KS_HANDSHAKE</a>
</dt>
<dt>
<a href="..\ks\ns-ks-kshandshake.md">KSHANDSHAKE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinHandshake function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


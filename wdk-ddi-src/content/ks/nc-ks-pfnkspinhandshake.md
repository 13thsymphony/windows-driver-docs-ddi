---
UID: NC.ks.PFNKSPINHANDSHAKE
title: PFNKSPINHANDSHAKE
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniPinHandshake routine is called when AVStream receives a protocol handshake request that it does not handle.
old-location: stream\avstrminipinhandshake.htm
old-project: stream
ms.assetid: cebeceb1-f845-42cf-9a8b-3414e4a420b6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NpdBrokerUninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AVStrMiniPinHandshake
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
req.irql: 
---

# PFNKSPINHANDSHAKE callback



## -description
An AVStream minidriver's <i>AVStrMiniPinHandshake</i> routine is called when AVStream receives a protocol handshake request that it does not handle.



## -prototype

````
PFNKSPINHANDSHAKE AVStrMiniPinHandshake;

NTSTATUS AVStrMiniPinHandshake(
  _In_ PKSPIN       Irp,
  _In_ PKSHANDSHAKE Request,
  _In_ PKSHANDSHAKE Data
)
{ ... }
````


## -parameters

### -param Irp [in]

Pointer to the IRP containing the handshake request.


### -param Request [in]

Pointer to a <a href="..\ks\ns-ks-ksidentifier.md">KSIDENTIFIER</a> structure that contains a GUID identifying the requested protocol.


### -param Data [in]

Pointer to a caller-allocated buffer. If the pin supports the requested protocol, <i>AVStrMiniPinHandshake</i> should fill in this parameter with a pointer to a <a href="..\ks\ns-ks-kshandshake.md">KSHANDSHAKE</a> structure.


## -returns
Returns STATUS_SUCCESS if the pin supports the requested protocol. Otherwise, it should return STATUS_INVALID_DEVICE_REQUEST.


## -remarks
The minidriver specifies this routine's address in the <i>Handshake</i> parameter of a call to <a href="stream.kspinregisterhandshakecallback">KsPinRegisterHandshakeCallback</a>.


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
</table>

## -see-also
<dl>
<dt>
<a href="stream.kspinregisterhandshakecallback">KsPinRegisterHandshakeCallback</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksidentifier.md">KSIDENTIFIER</a>
</dt>
<dt>
<a href="..\ks\ns-ks-kshandshake.md">KSHANDSHAKE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVStrMiniPinHandshake routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


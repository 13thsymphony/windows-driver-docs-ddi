---
UID: NF:ks.KsPinHandshake
title: KsPinHandshake function
author: windows-driver-content
description: The KsPinHandshake function attempts a protocol handshake with a connected pin.
old-location: stream\kspinhandshake.htm
old-project: stream
ms.assetid: 31855688-9221-4128-89c5-dbc4f3e6f794
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsPinHandshake, KsPinHandshake function [Streaming Media Devices], avfunc_a7b6afa8-acb0-4847-9e86-136100c4dd48.xml, ks/KsPinHandshake, stream.kspinhandshake
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsPinHandshake
product: Windows
targetos: Windows
req.typenames: 
---


# KsPinHandshake function
The<b> KsPinHandshake </b>function attempts a protocol handshake with a connected pin.

## Syntax

````
NTSTATUS KsPinHandshake(
  _In_  PKSPIN       Pin,
  _In_  PKSHANDSHAKE In,
  _Out_ PKSHANDSHAKE Out
);
````

## Parameters

`Pin`

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure that is initiating the handshake. The handshake request is passed on to the pin connected to this object.

`In`

A pointer to the <a href="..\ks\ns-ks-kshandshake.md">KSHANDSHAKE</a> structure containing the handshake information to be passed to the connected pin.

`Out`

A pointer to a <a href="..\ks\ns-ks-kshandshake.md">KSHANDSHAKE</a> structure that is filled in with handshake information by the connected pin.


## Return Value

<b>KsPinHandshake </b>returns STATUS_SUCCESS if the connected pin is accepting the negotiated connection. Otherwise, it returns an appropriate error code.

## Remarks

Protocol handshakes can be used to negotiate private interfaces between two pins that are both AVStream pins. 

Connections between AVStream pins are performed using this type of handshake.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ks\ni-ks-ioctl_ks_handshake.md">IOCTL_KS_HANDSHAKE</a>



<a href="..\ks\ns-ks-kshandshake.md">KSHANDSHAKE</a>



<a href="..\ks\nf-ks-kspingetconnectedpininterface.md">KsPinGetConnectedPinInterface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinHandshake function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
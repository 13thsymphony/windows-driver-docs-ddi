---
UID: NF.ufxclient.UfxEndpointNotifySetup
title: UfxEndpointNotifySetup function
author: windows-driver-content
description: Notifies UFX when the client driver receives a setup packet from the host.
old-location: buses\ufxendpointnotifysetup.htm
old-project: usbref
ms.assetid: 147CE46A-315D-4B75-B345-A7C0B01B2078
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: UfxEndpointNotifySetup
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UfxEndpointNotifySetup
req.alt-loc: ufxclient.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# UfxEndpointNotifySetup function



## -description
Notifies UFX when the client driver receives a setup packet from the host.



## -syntax

````
VOID UfxEndpointNotifySetup(
  [in] UFXDEVICE                      UfxDevice,
  [in] PUSB_DEFAULT_PIPE_SETUP_PACKET SetupInfo
);
````


## -parameters

### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="buses.ufxdevicecreate">UfxDeviceCreate</a>.


### -param SetupInfo [in]

A pointer to a USB setup packet described in a <b>USB_DEFAULT_PIPE_SETUP_PACKET</b> structure (defined in Usbspec.h).


## -returns
This method does not return a value.


## -remarks
The following example shows how to handle setup packet completion.


## -requirements
<table>
<tr>
<th width="30%">
Minimum support

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ufxclient.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
DISPATCH_LEVEL

</td>
</tr>
</table>
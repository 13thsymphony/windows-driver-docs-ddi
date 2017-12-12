---
UID: NS.KS._KSDEVICE_DISPATCH~R1
title: _KSDEVICE_DISPATCH
author: windows-driver-content
description: The KSDEVICE_DISPATCH structure describes the callbacks that a client can provide to receive notification of device creation and PnP events.
old-location: stream\ksdevice_dispatch.htm
old-project: stream
ms.assetid: 1ae7af1d-5e1c-4728-82c5-efc8d60b5df6
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _KSDEVICE_DISPATCH, KSDEVICE_DISPATCH, *PKSDEVICE_DISPATCH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSDEVICE_DISPATCH
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

# _KSDEVICE_DISPATCH structure



## -description
The KSDEVICE_DISPATCH structure describes the callbacks that a client can provide to receive notification of device creation and PnP events.



## -syntax

````
typedef struct _KSDEVICE_DISPATCH {
  PFNKSDEVICECREATE            Add;
  PFNKSDEVICEPNPSTART          Start;
  PFNKSDEVICE                  PostStart;
  PFNKSDEVICEIRP               QueryStop;
  PFNKSDEVICEIRPVOID           CancelStop;
  PFNKSDEVICEIRPVOID           Stop;
  PFNKSDEVICEIRP               QueryRemove;
  PFNKSDEVICEIRPVOID           CancelRemove;
  PFNKSDEVICEIRPVOID           Remove;
  PFNKSDEVICEQUERYCAPABILITIES QueryCapabilities;
  PFNKSDEVICEIRPVOID           SurpriseRemoval;
  PFNKSDEVICEQUERYPOWER        QueryPower;
  PFNKSDEVICESETPOWER          SetPower;
  PFNKSDEVICEIRP               QueryInterface;
} KSDEVICE_DISPATCH, *PKSDEVICE_DISPATCH;
````


## -struct-fields

### -field Add

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="stream.avstrminideviceadd">AVStrMiniDeviceAdd</a> callback routine.


### -field Start

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="stream.avstrminidevicestart">AVStrMiniDeviceStart</a> callback routine.


### -field PostStart

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="stream.avstrminidevicepoststart">AVStrMiniDevicePostStart</a> callback routine.


### -field QueryStop

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="stream.avstrminidevicequerystop">AVStrMiniDeviceQueryStop</a> callback routine.


### -field CancelStop

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="stream.avstrminidevicecancelstop">AVStrMiniDeviceCancelStop</a> callback routine.


### -field Stop

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="stream.avstrminidevicestop">AVStrMiniDeviceStop</a> callback routine.


### -field QueryRemove

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="stream.avstrminidevicequeryremove">AVStrMiniDeviceQueryRemove</a> callback routine.


### -field CancelRemove

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="stream.avstrminidevicecancelremove">AVStrMiniDeviceCancelRemove</a> callback routine.


### -field Remove

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="stream.avstrminideviceremove">AVStrMiniDeviceRemove</a> callback routine.


### -field QueryCapabilities

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="stream.avstrminidevicequerycapabilities">AVStrMiniDeviceQueryCapabilities</a> callback routine.


### -field SurpriseRemoval

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="stream.avstrminidevicesurpriseremoval">AVStrMiniDeviceSurpriseRemoval</a> callback routine.


### -field QueryPower

Optional. can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="stream.avstrminidevicequerypower">AVStrMiniDeviceQueryPower</a> callback routine.


### -field SetPower

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="stream.avstrminidevicesetpower">AVStrMiniDeviceSetPower</a> callback routine.


### -field QueryInterface

Optional. Can be <b>NULL</b>. A pointer to a minidriver-supplied <a href="stream.avstrminidevicequeryinterface">AVStrMiniDeviceQueryInterface</a> callback routine.


## -remarks
In describing a device with the <a href="stream.ksdevice_descriptor">KSDEVICE_DESCRIPTOR</a> structure, clients include a pointer to a dispatch table defined by this structure. Any member of this structure may be <b>NULL</b> indicating that the minidriver receives no notification for that particular message.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.

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
<a href="stream.ksdevice_descriptor">KSDEVICE_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSDEVICE_DISPATCH structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


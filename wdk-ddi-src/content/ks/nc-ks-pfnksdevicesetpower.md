---
UID: NC.ks.PFNKSDEVICESETPOWER
title: PFNKSDEVICESETPOWER
author: windows-driver-content
description: AVStream calls a minidriver's AVStrMiniDeviceSetPower routine when it receives an IRP_MN_SET_POWER.
old-location: stream\avstrminidevicesetpower.htm
old-project: stream
ms.assetid: 40d5eb14-b7bd-42b6-a3f5-fe9e8c5c806e
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
req.alt-api: AVStrMiniDeviceSetPower
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

# PFNKSDEVICESETPOWER callback



## -description
AVStream calls a minidriver's <i>AVStrMiniDeviceSetPower</i> routine when it receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>.



## -prototype

````
PFNKSDEVICESETPOWER AVStrMiniDeviceSetPower;

void AVStrMiniDeviceSetPower(
  _In_ PKSDEVICE          Device,
  _In_ PIRP               Irp,
  _In_ DEVICE_POWER_STATE To,
  _In_ DEVICE_POWER_STATE From
)
{ ... }
````


## -parameters

### -param Device [in]

Pointer to the <a href="stream.ksdevice">KSDEVICE</a> structure that received the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>.


### -param Irp [in]

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> issued by <i>Device</i>.


### -param To [in]

The target device power state.


### -param From [in]

The current device power state.


## -returns
None


## -remarks
If a driver has registered its device for idle detection, the power manager sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> to change the power state of an idle device.

The minidriver specifies this routine's address in the <b>SetPower</b> member of its <a href="stream.ksdevice_dispatch">KSDEVICE_DISPATCH</a> structure.

This routine is optional.


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
<a href="stream.ksdevice_dispatch">KSDEVICE_DISPATCH</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVStrMiniDeviceSetPower routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


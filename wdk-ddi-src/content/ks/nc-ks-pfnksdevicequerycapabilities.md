---
UID: NC.ks.PFNKSDEVICEQUERYCAPABILITIES
title: PFNKSDEVICEQUERYCAPABILITIES
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniDeviceQueryCapabilities routine is called when an IRP_MN_QUERY_CAPABILITIES is dispatched by the device.
old-location: stream\avstrminidevicequerycapabilities.htm
old-project: stream
ms.assetid: 12084f07-5b6a-44d4-8ab3-325309e69372
ms.author: windowsdriverdev
ms.date: 12/6/2017
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
req.alt-api: AVStrMiniDeviceQueryCapabilities
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
req.irql: PASSIVE_LEVEL (See Remarks section)
---

# PFNKSDEVICEQUERYCAPABILITIES callback



## -description
An AVStream minidriver's <i>AVStrMiniDeviceQueryCapabilities</i> routine is called when an <a href="kernel.irp_mn_query_capabilities">IRP_MN_QUERY_CAPABILITIES</a> is dispatched by the device.



## -prototype

````
PFNKSDEVICEQUERYCAPABILITIES AVStrMiniDeviceQueryCapabilities;

NTSTATUS AVStrMiniDeviceQueryCapabilities(
  _In_    PKSDEVICE            Device,
  _In_    PIRP                 Irp,
  _Inout_ PDEVICE_CAPABILITIES Capabilities
)
{ ... }
````


## -parameters

### -param Device [in]

Pointer to the <a href="stream.ksdevice">KSDEVICE</a> that dispatched the <a href="kernel.irp_mn_query_capabilities">IRP_MN_QUERY_CAPABILITIES</a>.


### -param Irp [in]

The <a href="kernel.irp_mn_query_capabilities">IRP_MN_QUERY_CAPABILITIES</a> issued by <i>Device</i>.


### -param Capabilities [in, out]

Pointer to the DEVICE_CAPABILITIES structure that describes PnP and Power capabilities of <i>Device</i>.


## -returns
Should return STATUS_SUCCESS or the error code that was returned from the attempt to perform the operation. Return success if providing query capabilities. If not, return an appropriate error code. Do not return STATUS_PENDING.


## -remarks
The minidriver specifies this routine's address in the <b>QueryCapabilities</b> member of its <a href="stream.ksdevice_dispatch">KSDEVICE_DISPATCH</a> structure.

This routine is called when an <a href="kernel.irp_mn_query_capabilities">IRP_MN_QUERY_CAPABILITIES</a> is dispatched by the device. It will usually be provided by minidrivers that need to supply information regarding power management capabilities. This routine is optional.


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
PASSIVE_LEVEL (See Remarks section)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksdevice_dispatch">KSDEVICE_DISPATCH</a>
</dt>
<dt>
<a href="stream.ksdevice">KSDEVICE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVStrMiniDeviceQueryCapabilities routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NF.ks.KsRecalculateStackDepth
title: KsRecalculateStackDepth function
author: windows-driver-content
description: The KsRecalculateStackDepth function recalculates the maximum stack depth required by the underlying device object based on all of the objects that have set a target device (they have added themselves to the object list on the underlying device object using the KsSetTargetDeviceObject function). If the PnP device object has been set on the underlying device header using KsSetDevicePnpAndBaseObject, that device is also taken into account when calculating the maximum stack depth.
old-location: stream\ksrecalculatestackdepth.htm
old-project: stream
ms.assetid: 0b8f23a5-af8a-4b99-8f17-092076523914
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsRecalculateStackDepth
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsRecalculateStackDepth
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
---

# KsRecalculateStackDepth function



## -description
The <b>KsRecalculateStackDepth</b> function recalculates the maximum stack depth required by the underlying device object based on all of the objects that have set a target device (they have added themselves to the object list on the underlying device object using the <b>KsSetTargetDeviceObject</b> function). If the PnP device object has been set on the underlying device header using <b>KsSetDevicePnpAndBaseObject</b>, that device is also taken into account when calculating the maximum stack depth.



## -syntax

````
VOID KsRecalculateStackDepth(
  _In_ KSDEVICE_HEADER Header ,
  _In_ BOOLEAN         ReuseStackLocation 
);
````


## -parameters

### -param Header  [in]

Points to a header previously allocated by <b>KsAllocateDeviceHeader</b>.


### -param ReuseStackLocation  [in]

If this is set to <b>TRUE</b>, the current stack location is reused when any IRP is forwarded. This means that this object does not require its own stack location when forwarding IRPs and an extra location is not added to the maximum stack size. If set to <b>FALSE</b>, the calculated stack size is incremented by one. If the Pnp object stack is set, the reuse parameter also applies to that stack. Note that <b>KsDefaultDispatchPnp</b> always reuses the current stack location. The minimum stack depth is 1.


## -returns
None


## -remarks
The <b>KsRecalculateStackDepth</b> function assumes that <b>KsSetDevicePnpAndBaseObject</b> has been called on this device header and has assigned a base object whose stack depth is to be recalculated.

This function allows IRPs to be forwarded through an object by ensuring that any IRP allocated on this device will have sufficient stack locations to allow it to be forwarded. Stack depth must be recalculated on a streaming device when the device transitions out of a Stop state. It can also be recalculated when an object is freed in order to conserve resources.


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
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.kssettargetdeviceobject">KsSetTargetDeviceObject</a>
</dt>
<dt>
<a href="stream.ksallocatedeviceheader">KsAllocateDeviceHeader</a>
</dt>
<dt>
<a href="stream.kssetdevicepnpandbaseobject">KsSetDevicePnpAndBaseObject</a>
</dt>
<dt>
<a href="stream.ksdefaultdispatchpnp">KsDefaultDispatchPnp</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsRecalculateStackDepth  function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


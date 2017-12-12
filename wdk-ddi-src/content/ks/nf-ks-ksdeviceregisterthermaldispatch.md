---
UID: NF.ks.KsDeviceRegisterThermalDispatch
title: KsDeviceRegisterThermalDispatch function
author: windows-driver-content
description: This function is used by the Avstream miniport driver to register callbacks for thermal notifications with the KS port driver.
old-location: stream\ksdeviceregisterthermaldispatch.htm
old-project: stream
ms.assetid: 7998B753-8E43-471F-9BDE-729D0E38E022
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsDeviceRegisterThermalDispatch
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsDeviceRegisterThermalDispatch
req.alt-loc: ks.lib,ks.dll
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

# KsDeviceRegisterThermalDispatch function



## -description
This function is used by the Avstream miniport driver to register callbacks for thermal notifications with the KS port driver.



## -syntax

````
void KSDDKAPI NTSTATUS NTAPI KsDeviceRegisterThermalDispatch(
  _In_ PKSDEVICE                  KsDevice,
  _In_ PKSDEVICE_THERMAL_DISPATCH KsDeviceThermalDispatch
);
````


## -parameters

### -param KsDevice [in]

A KS device object representing the device managed by KS. For more information, see <a href="stream.ksdevice">KSDEVICE</a>.


### -param KsDeviceThermalDispatch [in]

A structure containing the Avstream driver active and passive thermal callback notifications.


## -returns
Returns NTSTATUS  STATUS_SUCCESS for success conditions or STATUS_INVALID_DEVICE_REQUEST if both the parameters are NULL.


## -remarks
<b>KsDeviceRegisterThermalDispatch</b> takes two arguments:<ul>
<li>A KS device object that represents the hardware device managed by the KS port driver (a camera in this case).</li>
<li>Thermal dispatch callback functions.</li>
</ul>


For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh698236">Device-Level Thermal Management</a>.


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
<dt>Ks.h</dt>
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
<a href="stream.ksdevice">KSDEVICE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDeviceRegisterThermalDispatch function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


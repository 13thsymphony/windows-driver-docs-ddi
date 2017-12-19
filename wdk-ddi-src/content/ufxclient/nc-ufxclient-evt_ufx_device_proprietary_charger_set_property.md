---
UID: NC.ufxclient.EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY
title: EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY
author: windows-driver-content
description: The client driver's implementation to set charger information that it uses to enable charging over USB.
old-location: buses\evt_ufx_device_proprietary_charger_set_property.htm
old-project: UsbRef
ms.assetid: 7ED9D607-2F7A-4835-9D1E-FC33EF594974
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _UFX_HARDWARE_FAILURE_CONTEXT, PUFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: PFN_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY
req.alt-loc: Ufxclient.h
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
req.product: Windows 10 or later.
---

# EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY callback



## -description
The client driver's implementation to set charger information that it uses to enable charging over USB.



## -prototype

````
EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY EvtUfxDeviceProprietaryChargerSetProperty
;

void EvtUfxDeviceProprietaryChargerSetProperty
(
  _In_ UFXDEVICE  UfxDevice,
  _In_ WDFREQUEST WdfRequest
)
{ ... }

typedef EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY PFN_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY;
````


## -parameters

### -param UfxDevice [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="buses.ufxdevicecreate">UfxDeviceCreate</a>.


### -param WdfRequest [in]

The handle framework request object that for an <a href="..\charging\ni-charging-ioctl_internal_configure_charger_property.md">IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY</a> request from the battery minidriver. 


## -returns
This callback function does not return a value.


## -remarks
<i>EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY</i> is an optional event callback.

<i>WdfRequest</i> is contains a request for <a href="..\charging\ni-charging-ioctl_internal_configure_charger_property.md">IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY</a>, which specifies a charger ID that is known by the client driver and battery miniclass driver, and a voltage value in millivolts.  The client driver can use this information to enable charging over the USB port at an appropriate current/voltage level.


## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

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
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.ufxdevicecreate">UfxDeviceCreate</a>
</dt>
<dt>
<a href="buses.ufxdeviceproprietarychargerdetectcomplete">UfxDeviceProprietaryChargerDetectComplete</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


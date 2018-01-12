---
UID: NE:wudfddi_types._WDF_EVENT_TYPE
title: _WDF_EVENT_TYPE
author: windows-driver-content
description: The WDF_EVENT_TYPE enumeration specifies.
old-location: wdf\wdf_event_type.htm
old-project: wdf
ms.assetid: DC6353BB-98C0-4647-9180-F099CD95348E
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _WDF_EVENT_TYPE, WDF_EVENT_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: WDF_EVENT_TYPE
req.alt-loc: wdfdevice.h,wudfddi_types.h
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
req.typenames: WDF_EVENT_TYPE
req.product: Windows 10 or later.
---

# _WDF_EVENT_TYPE enumeration



## -description
<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_EVENT_TYPE</b> enumeration specifies  types of events about which a driver can notify a registered application.



## -syntax

````
typedef enum _WDF_EVENT_TYPE { 
  WdfEventReserved   = 0,
  WdfEventBroadcast  = 1,
  WdfEventMaximum    = 2
} WDF_EVENT_TYPE;
````


## -enum-fields

### -field WdfEventReserved

Reserved for system use.


### -field WdfEventBroadcast

In the current version of UMDF, the driver must specify <b>WdfEventBroadcast</b>. For more information, see <a href="..\wdfdevice\nf-wdfdevice-wdfdevicepostevent.md">WdfDevicePostEvent</a>.


### -field WdfEventMaximum

Reserved for system use.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum support

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.11

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h); </dt>
<dt>Wudfddi_types.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicepostevent.md">WdfDevicePostEvent</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558835">IWDFDevice::PostEvent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_EVENT_TYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


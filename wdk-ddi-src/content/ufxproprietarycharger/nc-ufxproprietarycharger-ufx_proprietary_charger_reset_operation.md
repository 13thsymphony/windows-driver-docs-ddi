---
UID: NC.ufxproprietarycharger.UFX_PROPRIETARY_CHARGER_RESET_OPERATION
title: UFX_PROPRIETARY_CHARGER_RESET_OPERATION
author: windows-driver-content
description: The filter driver's implementation to reset a charger operation.
old-location: buses\ufx_proprietary_charger_reset_operation.htm
old-project: usbref
ms.assetid: F307A139-B55A-4C29-BE2F-14C243115F8C
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _UFX_ENDPOINT_CALLBACKS, UFX_ENDPOINT_CALLBACKS, *PUFX_ENDPOINT_CALLBACKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ufxproprietarycharger.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: PFN_UFX_PROPRIETARY_CHARGER_RESET_OPERATION
req.alt-loc: ufxproprietarycharger.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# UFX_PROPRIETARY_CHARGER_RESET_OPERATION callback



## -description
The filter driver's implementation to reset a charger operation.


## -prototype

````
UFX_PROPRIETARY_CHARGER_RESET_OPERATION UfxProprietaryChargerReset;

NTSTATUS UfxProprietaryChargerReset(
  _In_ PVOID Context
)
{ ... }

typedef UFX_PROPRIETARY_CHARGER_RESET_OPERATION PFN_UFX_PROPRIETARY_CHARGER_RESET_OPERATION;
````


## -parameters

### -param Context [in]

    A pointer to a driver-defined context.

## -returns
If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## -remarks
To support handling of proprietary chargers, the USB lower filter driver must publish support. During the publishing process, the driver also registers its implementation of this  callback function. For more information, see <a href="buses.usb_filter_driver_for_proprietary_charging">USB filter driver for supporting proprietary chargers</a>.

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
<dt>Ufxproprietarycharger.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;=DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.usb_filter_driver_for_proprietary_charging">USB filter driver for supporting proprietary chargers</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UFX_PROPRIETARY_CHARGER_RESET_OPERATION callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

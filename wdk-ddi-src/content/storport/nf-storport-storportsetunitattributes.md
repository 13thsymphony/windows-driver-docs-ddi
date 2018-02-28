---
UID: NF:storport.StorPortSetUnitAttributes
title: StorPortSetUnitAttributes function
author: windows-driver-content
description: The StorPortSetUnitAttributes routine registers the power attributes of a storage unit device with the Storport driver.
old-location: storage\storportsetunitattributes.htm
old-project: storage
ms.assetid: 0E05233D-79B0-4FC7-B13C-91B6B1F57E89
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: StorPortSetUnitAttributes, StorPortSetUnitAttributes routine [Storage Devices], storage.storportsetunitattributes, storport/StorPortSetUnitAttributes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Storport.h
api_name:
-	StorPortSetUnitAttributes
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortSetUnitAttributes function
The <b>StorPortSetUnitAttributes</b> routine registers the power attributes of a storage unit device with the Storport driver.

## Syntax

````
ULONG StorPortSetUnitAttributes(
  _In_ PVOID                HwDeviceExtension,
  _In_ PSTOR_ADDRESS        Address,
  _In_ STOR_UNIT_ATTRIBUTES Attributes
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA).

`Address`

The storage unit device address. This parameter must not be NULL.

`Attributes`

A set of bitfields indicating the attributes supported for the unit device.


## Return Value

<b>StorPortSetUnitAttributes</b> returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the routine set the unit attributes successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>HwDeviceExtension</i> pointer is <b>NULL</b>.

-or-

One or more reserved bits in <i>Attributes</i> are set.

-or-

The unit address in <i>Address</i> is formatted incorrectly.

-or-

A unit device is not found for the address given in <i>Address</i>.

</td>
</tr>
</table>

## Remarks

A miniport driver will call this routine to register the unit attributes with Storport during completion of an SRB containing a SCSIOP_INQUIRY command request.  The bitfields in <i>attributes</i> are set based on the data returned from the adapter for the inquiry command. Storport will issue an inquiry for the unit at <i>Address</i> during a bus enumeration.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.  |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | Any |

## See Also

<a href="..\storport\ns-storport-_stor_unit_attributes.md">STOR_UNIT_ATTRIBUTES</a>



<a href="..\storport\ns-storport-_stor_address.md">STOR_ADDRESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortSetUnitAttributes routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
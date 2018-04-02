---
UID: NC:usbbusif.PUSB_BUSIFFN_QUERY_BUS_INFORMATION
title: PUSB_BUSIFFN_QUERY_BUS_INFORMATION
author: windows-driver-content
description: The QueryBusInformation routine gets information about the bus.
old-location: buses\querybusinformation.htm
old-project: usbref
ms.assetid: cc03ae88-89ba-44ff-bfe7-6255f2a2ec5c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PUSB_BUSIFFN_QUERY_BUS_INFORMATION, QueryBusInformation, QueryBusInformation callback function [Buses], USB_BUSIFFN_QUERY_BUS_INFORMATION, buses.querybusinformation, usbbusif/QueryBusInformation, usbinterKR_91d1f7ee-5cd2-4f87-bc4c-16972039f5e3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: usbbusif.h
req.include-header: Usbbusif.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: "< = DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	usbbusif.h
api_name:
-	QueryBusInformation
product:
- Windows
targetos: Windows
req.typenames: USBD_VERSION_INFORMATION, *PUSBD_VERSION_INFORMATION
req.product: Windows 10 or later.
---


# PUSB_BUSIFFN_QUERY_BUS_INFORMATION callback function
The <b>QueryBusInformation</b> routine gets information about the bus.

## Syntax

```
PUSB_BUSIFFN_QUERY_BUS_INFORMATION PusbBusiffnQueryBusInformation;

NTSTATUS PusbBusiffnQueryBusInformation(
  PVOID ,
  ULONG ,
  PVOID ,
  PULONG ,
  PULONG 
)
{...}
```

## Parameters

`Arg1`



`Arg1`



`Arg1`



`Arg1`



`Arg1`




## Return Value

<b>QueryBusInformation</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The call completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer was too small. This error code is returned in two cases:

Whenever <i>Level</i> = 0, this error code is returned if the size of the buffer pointed to by <i>BusInformationBuffer</i> is less than the size of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539201">USB_BUS_INFORMATION_LEVEL_0</a> structure.

Whenever Level = 1, this error code is returned if the size of the buffer pointed to by <i>BusInformationBuffer</i> less than the size of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539205">USB_BUS_INFORMATION_LEVEL_1</a> structure. 

</td>
</tr>
</table>

## Remarks

The exact information returned by this routine depends on the value of the <i>Level</i> parameter. This routine replaces the <b>USBD_QueryBusInformation</b> library function provided by usbd.sys. 

The function definition that is provided on this reference page is an example routine whose parameters are just placeholder names. The actual prototype of the function is declared in usbbusif.h as follows:

<pre class="syntax" xml:space="preserve"><code>typedef NTSTATUS
  (USB_BUSIFFN *PUSB_BUSIFFN_QUERY_BUS_INFORMATION) (
    IN PVOID,
    IN ULONG,
    IN OUT PVOID,
    IN OUT PULONG,
    OUT PULONG
  );</code></pre>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbbusif.h (include Usbbusif.h) |
| **IRQL** | "< = DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539201">USB_BUS_INFORMATION_LEVEL_0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539205">USB_BUS_INFORMATION_LEVEL_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539210">USB_BUS_INTERFACE_USBDI_V0</a>
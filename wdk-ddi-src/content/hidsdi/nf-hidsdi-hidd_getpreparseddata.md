---
UID : NF:hidsdi.HidD_GetPreparsedData
title : HidD_GetPreparsedData function
author : windows-driver-content
description : The HidD_GetPreparsedData routine returns a top-level collection's preparsed data.
old-location : hid\hidd_getpreparseddata.htm
old-project : hid
ms.assetid : e5c550f0-a466-4d0b-ac6f-bcdce600245f
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : HidD_GetPreparsedData
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : hidsdi.h
req.include-header : Hidsdi.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : HidD_GetPreparsedData
req.alt-loc : Hid.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Hid.lib
req.dll : Hid.dll
req.irql : 
req.typenames : HID_MINIDRIVER_REGISTRATION, *PHID_MINIDRIVER_REGISTRATION
---


# HidD_GetPreparsedData function
The <b>HidD_GetPreparsedData</b> routine returns a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.

## Syntax

````
BOOLEAN __stdcall HidD_GetPreparsedData(
  _In_  HANDLE               HidDeviceObject,
  _Out_ PHIDP_PREPARSED_DATA *PreparsedData
);
````

## Parameters

`HidDeviceObject`

Specifies an open handle to a top-level collection.

`PreparsedData`

Pointer to the address of a routine-allocated buffer that contains a collection's preparsed data in a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a> structure.


## Return Value

<b>HidD_GetPreparsedData</b> returns <b>TRUE</b> if it succeeds; otherwise, it returns <b>FALSE</b>.

## Remarks

Only user-mode applications can call <b>HidD_GetPreparsedData</b>. Kernel-mode drivers can use an <a href="..\hidclass\ni-hidclass-ioctl_hid_get_collection_descriptor.md">IOCTL_HID_GET_COLLECTION_DESCRIPTOR</a> request.

When an application no longer requires the preparsed data, it should call <a href="..\hidsdi\nf-hidsdi-hidd_freepreparseddata.md">HidD_FreePreparsedData</a> to free the preparsed data buffer.

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hidsdi.h (include Hidsdi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff539679">_HIDP_PREPARSED_DATA</a>
</dt>
<dt>
<a href="..\hidsdi\nf-hidsdi-hidd_freepreparseddata.md">HidD_FreePreparsedData</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_collection_descriptor.md">IOCTL_HID_GET_COLLECTION_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidD_GetPreparsedData routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
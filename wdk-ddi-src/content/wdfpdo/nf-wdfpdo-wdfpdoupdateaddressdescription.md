---
UID : NF:wdfpdo.WdfPdoUpdateAddressDescription
title : WdfPdoUpdateAddressDescription function
author : windows-driver-content
description : The WdfPdoUpdateAddressDescription method updates the address description that is associated with a specified framework device object.
old-location : wdf\wdfpdoupdateaddressdescription.htm
old-project : wdf
ms.assetid : f41e4b81-48e0-448f-b32a-6ecadbc2e45c
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : kmdf.wdfpdoupdateaddressdescription, PFN_WDFPDOUPDATEADDRESSDESCRIPTION, WdfPdoUpdateAddressDescription, DFDeviceObjectFdoPdoRef_be344160-571e-4c5b-971d-a7ab78f6c292.xml, wdfpdo/WdfPdoUpdateAddressDescription, WdfPdoUpdateAddressDescription method, wdf.wdfpdoupdateaddressdescription
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfpdo.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDF_OBJECT_CONTEXT_TYPE_INFO, WDF_OBJECT_CONTEXT_TYPE_INFO"
req.product : Windows 10 or later.
---


# WdfPdoUpdateAddressDescription function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoUpdateAddressDescription</b> method updates the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">address description</a> that is associated with a specified framework device object.

## Syntax

````
NTSTATUS WdfPdoUpdateAddressDescription(
  _In_    WDFDEVICE                             Device,
  _Inout_ PWDF_CHILD_ADDRESS_DESCRIPTION_HEADER AddressDescription
);
````

## Parameters

`Device`

A handle to a framework device object that represents a device's physical device object (PDO).

`AddressDescription`

A pointer to a caller-allocated buffer that contains an address description. The address description must contain a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_address_description_header.md">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure.


## Return Value

If the operation succeeds, the function returns STATUS_SUCCESS. Additional return values include:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>Device</i> handle does not represent a PDO. 


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The <i>Device</i> handle does not represent a device that was <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">dynamically enumerated</a>,or if the <b>Size</b> member of the specified <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_address_description_header.md">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure does not match the size of the device's existing address description.

</td>
</tr>
</table> 

The method might also return other<a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505"> NTSTATUS values</a>.

A system bug check occurs if the driver supplies an invalid object handle.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfpdo.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfpdo\nf-wdfpdo-wdfpdoretrieveaddressdescription.md">WdfPdoRetrieveAddressDescription</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPdoUpdateAddressDescription method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID: NS:wdfchildlist._WDF_CHILD_RETRIEVE_INFO
title: "_WDF_CHILD_RETRIEVE_INFO"
author: windows-driver-content
description: The WDF_CHILD_RETRIEVE_INFO structure contains information about a child device that is obtained by calling WdfChildListRetrieveNextDevice or WdfChildListRetrievePdo.
old-location: wdf\wdf_child_retrieve_info.htm
old-project: wdf
ms.assetid: 0c48e7cd-e9aa-4ae7-bd44-fe16e1b0d619
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_CHILD_RETRIEVE_INFO, DFDeviceObjectChildListRef_f2075d85-7f9e-4b9c-b702-c2ef2be65987.xml, PWDF_CHILD_RETRIEVE_INFO, PWDF_CHILD_RETRIEVE_INFO structure pointer, WDF_CHILD_RETRIEVE_INFO, WDF_CHILD_RETRIEVE_INFO structure, _WDF_CHILD_RETRIEVE_INFO, kmdf.wdf_child_retrieve_info, wdf.wdf_child_retrieve_info, wdfchildlist/PWDF_CHILD_RETRIEVE_INFO, wdfchildlist/WDF_CHILD_RETRIEVE_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfchildlist.h
api_name:
-	WDF_CHILD_RETRIEVE_INFO
product: Windows
targetos: Windows
req.typenames: WDF_CHILD_RETRIEVE_INFO, *PWDF_CHILD_RETRIEVE_INFO
req.product: Windows 10 or later.
---

# _WDF_CHILD_RETRIEVE_INFO structure
<p class="CCE_Message">[Applies to KMDF only]

The WDF_CHILD_RETRIEVE_INFO structure contains information about a child device that is obtained by calling <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a> or <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievepdo.md">WdfChildListRetrievePdo</a>.

## Syntax
````
typedef struct _WDF_CHILD_RETRIEVE_INFO {
  ULONG                                                 Size;
  PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER          IdentificationDescription;
  PWDF_CHILD_ADDRESS_DESCRIPTION_HEADER                 AddressDescription;
  WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS                 Status;
  PFN_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE EvtChildListIdentificationDescriptionCompare;
} WDF_CHILD_RETRIEVE_INFO, *PWDF_CHILD_RETRIEVE_INFO;
````

## Members


`Size`

The size, in bytes, of this structure.

`IdentificationDescription`

A pointer to a driver-allocated <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure. The driver must supply a value for this structure's <b>IdentificationDescriptionSize</b> member. 

If the driver is calling <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a> and supplying an <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_compare.md">EvtChildListIdentificationDescriptionCompare</a> callback function, the driver must also provide an <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a> that the callback function can use to compare with an entry in a child list.

If the driver is calling <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievepdo.md">WdfChildListRetrievePdo</a>, the driver must fill in the entire identification description.

`AddressDescription`

A pointer to a driver-allocated <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_address_description_header.md">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure. The driver must supply a value for this structure's <b>AddressDescriptionSize</b> member. The framework fills in the rest of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">address description</a> when it retrieves a child from the child list. If the value of <b>AddressDescriptionSize</b> is <b>NULL</b>, address description information is not retrieved.

`Status`

A <a href="..\wdfchildlist\ne-wdfchildlist-_wdf_child_list_retrieve_device_status.md">WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS</a>-typed value that the framework provides.

`EvtChildListIdentificationDescriptionCompare`

A driver-supplied pointer to an <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_compare.md">EvtChildListIdentificationDescriptionCompare</a> callback function. 

If the driver is calling <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a>, this pointer is optional and can be <b>NULL</b>. 

If the driver is calling <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievepdo.md">WdfChildListRetrievePdo</a>, this pointer is not used.

## Remarks
The WDF_CHILD_RETRIEVE_INFO structure is passed to the <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a> and <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievepdo.md">WdfChildListRetrievePdo</a> methods. 

To initialize a WDF_CHILD_RETRIEVE_INFO structure, the driver must call <a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_retrieve_info_init.md">WDF_CHILD_RETRIEVE_INFO_INIT</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfchildlist.h (include Wdf.h) |

## See Also

<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="..\wdfchildlist\ne-wdfchildlist-_wdf_child_list_retrieve_device_status.md">WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS</a>



<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_compare.md">EvtChildListIdentificationDescriptionCompare</a>



<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_address_description_header.md">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievepdo.md">WdfChildListRetrievePdo</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a>
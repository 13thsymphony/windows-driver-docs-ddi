---
UID : NC:wdfchildlist.EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_DUPLICATE
title : EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_DUPLICATE
author : windows-driver-content
description : A driver's EvtChildListIdentificationDescriptionDuplicate event callback function duplicates a child identification description.
old-location : wdf\evtchildlistidentificationdescriptionduplicate.htm
old-project : wdf
ms.assetid : 5c2ec27c-2d88-4e0c-8f11-4f58d720df46
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.evtchildlistidentificationdescriptionduplicate, EvtChildListIdentificationDescriptionDuplicate callback function, EvtChildListIdentificationDescriptionDuplicate, EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_DUPLICATE, EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_DUPLICATE, wdfchildlist/EvtChildListIdentificationDescriptionDuplicate, DFDeviceObjectChildListRef_3ee2ef4e-8131-454a-b821-19eb5de4c8f9.xml, kmdf.evtchildlistidentificationdescriptionduplicate
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdfchildlist.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWDBGEXTS_THREAD_OS_INFO, WDBGEXTS_THREAD_OS_INFO"
req.product : Windows 10 or later.
---


# EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_DUPLICATE function
<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtChildListIdentificationDescriptionDuplicate</i> event callback function duplicates a child identification description.

## Syntax

```
EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_DUPLICATE EvtWdfChildListIdentificationDescriptionDuplicate;

NTSTATUS EvtWdfChildListIdentificationDescriptionDuplicate(
  WDFCHILDLIST ChildList,
  PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER SourceIdentificationDescription,
  PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER DestinationIdentificationDescription
)
{...}
```

## Parameters

`ChildList`

A handle to a framework child-list object.

`SourceIdentificationDescription`

A pointer to a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies the source location of the child identification description.

`DestinationIdentificationDescription`

A pointer to a WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure that identifies the destination location of the duplicate child identification description.


## Return Value

The <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function must return STATUS_SUCCESS, or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>, if the operation succeeds. Otherwise, this callback function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.

## Remarks

If a bus driver is using <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function by calling <a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a> or <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistcreate.md">WdfChildListCreate</a>.

The framework duplicates driver-supplied identification descriptions so that it can have internal copies of the descriptions.

The <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function must create a duplicate copy of an identification description. A driver must supply this callback function if the framework cannot call <a href="..\wdm\nf-wdm-rtlcopymemory.md">RtlCopyMemory</a> to duplicate the identification description. (The framework cannot call <b>RtlCopyMemory</b> if the description contains pointers to additional memory.)

If your driver does not provide an <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function, the framework duplicates identification descriptions by calling <a href="..\wdm\nf-wdm-rtlcopymemory.md">RtlCopyMemory</a>.

The following steps describe a typical scenario:
<ol>
<li>
The driver determines that a child device exists.

</li>
<li>
The driver creates an identification description by filling in a driver-defined structure that contains a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure and possibly by dynamically allocating addition memory to store identification information that has a device-specific size. 

</li>
<li>
The driver calls <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent.md">WdfChildListAddOrUpdateChildDescriptionAsPresent</a> to report a child device, supplying a pointer to the identification description. 

</li>
<li>
The framework calls the <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function (if it exists) or <a href="..\wdm\nf-wdm-rtlcopymemory.md">RtlCopyMemory</a> to duplicate the identification description so that it can have an internal copy of the description.

</li>
</ol>The framework can use <a href="..\wdm\nf-wdm-rtlcopymemory.md">RtlCopyMemory</a> to duplicate an identification description, if the description consists of a single structure with a predetermined size that is specified by the <b>IdentificationDescriptionSize</b> member of the WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure. However, sometimes the description must also contain additional information that is stored in dynamically allocated memory. In this case, you will typically define a description structure so that a member points to the dynamically allocated memory, and your driver must provide an <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function. The callback function must do the following:
<ol>
<li>
Allocate additional memory, typically by calling <a href="..\wdm\nf-wdm-exallocatepool.md">ExAllocatePool</a>.

</li>
<li>
Store the allocated memory's address in the driver-defined address description structure (that is, the callback function's <i>DestinationIdentificationDescription</i> structure).

</li>
<li>
Copy other structure members from the callback function's <i>SourceIdentificationDescription</i> structure to the callback function's <i>DestinationIdentificationDescription</i> structure.

</li>
</ol>The only <a href="https://msdn.microsoft.com/BFD91F00-5D35-4AF8-A6B6-F27DF64605D8">framework child-list object method</a> that a driver's <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function can call is <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistgetdevice.md">WdfChildListGetDevice</a>.

The framework acquires an internal child-list object lock before calling the <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function. This callback function must only perform operations that are related to the uplication operation, such as calling framework memory object methods and accessing object context space. It must not call methods that access other drivers.

If your driver supplies an <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function, it might also need <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_copy.md">EvtChildListIdentificationDescriptionCopy</a>, <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_compare.md">EvtChildListIdentificationDescriptionCompare</a>, and <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_cleanup.md">EvtChildListIdentificationDescriptionCleanup</a> callback functions.

For more information about dynamic enumeration, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfchildlist.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_copy.md">EvtChildListIdentificationDescriptionCopy</a>

<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_cleanup.md">EvtChildListIdentificationDescriptionCleanup</a>

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistgetdevice.md">WdfChildListGetDevice</a>

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistcreate.md">WdfChildListCreate</a>

<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>

<a href="..\wdm\nf-wdm-rtlcopymemory.md">RtlCopyMemory</a>

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent.md">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>

<a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a>

<a href="..\wdm\nf-wdm-exallocatepool.md">ExAllocatePool</a>

<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_compare.md">EvtChildListIdentificationDescriptionCompare</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_DUPLICATE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
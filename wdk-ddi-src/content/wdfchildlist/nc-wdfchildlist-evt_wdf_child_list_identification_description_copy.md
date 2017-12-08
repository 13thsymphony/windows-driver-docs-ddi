---
UID: NC.wdfchildlist.EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY
title: EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY
author: windows-driver-content
description: A driver's EvtChildListIdentificationDescriptionCopy event callback function copies a child identification description from one specified location to another.
old-location: wdf\evtchildlistidentificationdescriptioncopy.htm
old-project: wdf
ms.assetid: c44d6a2f-c7ef-486d-973e-aada068ddc06
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _WDBGEXTS_THREAD_OS_INFO, *PWDBGEXTS_THREAD_OS_INFO, WDBGEXTS_THREAD_OS_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: EvtChildListIdentificationDescriptionCopy
req.alt-loc: WdfChildlist.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY callback



## -description
<p class="CCE_Message">[Applies to KMDF only]
A driver's <i>EvtChildListIdentificationDescriptionCopy</i> event callback function copies a child identification description from one specified location to another.


## -prototype

````
EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY EvtChildListIdentificationDescriptionCopy;

VOID EvtChildListIdentificationDescriptionCopy(
  _In_  WDFCHILDLIST                                 ChildList,
  _In_  PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER SourceIdentificationDescription,
  _Out_ PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER DestinationIdentificationDescription
)
{ ... }
````


## -parameters

### -param ChildList [in]

A handle to a framework child-list object.

### -param SourceIdentificationDescription [in]

A pointer to a <a href="wdf.wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies the source location of the child identification description.

### -param DestinationIdentificationDescription [out]

A pointer to a <a href="wdf.wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies the destination location of the child identification description.

## -returns
None

## -remarks
If a bus driver is using <a href="wdf.dynamic_enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListIdentificationDescriptionCopy</i> callback function by calling <a href="wdf.wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a> or <a href="wdf.wdfchildlistcreate">WdfChildListCreate</a>.

The framework copies information from one driver-supplied identification description to another when it needs to update an existing description with new information, or when it needs to pass the contents of an identification description to the driver.

The <i>EvtChildListIdentificationDescriptionCopy</i> callback function must copy the contents of a source description to a destination description. A driver must supply this callback function if the framework cannot call <a href="kernel.rtlcopymemory">RtlCopyMemory</a> to copy the identification description. (The framework cannot call <b>RtlCopyMemory</b> if the description contains pointers to additional memory.)

If your driver does not provide an <i>EvtChildListIdentificationDescriptionCopy</i> callback function, the framework copies identification descriptions by calling <a href="kernel.rtlcopymemory">RtlCopyMemory</a>.

The following steps describe a possible scenario:

The driver that is traversing a child list calls <a href="wdf.wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a>. The driver supplies a <a href="wdf.wdf_child_retrieve_info">WDF_CHILD_RETRIEVE_INFO</a> structure so that it can receive the child device's identification description.

The framework calls the <i>EvtChildListIdentificationDescriptionCopy</i> callback function (if it exists) or <a href="kernel.rtlcopymemory">RtlCopyMemory</a> to copy the device's identification description. The source of the copy operation is the framework's internal copy of the description. The destination is memory that the driver allocated and identified in its WDF_CHILD_RETRIEVE_INFO structure.

The framework can use <a href="kernel.rtlcopymemory">RtlCopyMemory</a> to copy an identification description, if the description consists of a single structure with a predetermined size that is specified by the <b>IdentificationDescriptionSize</b> member of the <a href="wdf.wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure. However, sometimes the description must also contain additional information that is stored in dynamically allocated memory. In this case, you will typically define a description structure so that a member points to the dynamically allocated memory, and your driver must provide an <i>EvtChildListIdentificationDescriptionCopy</i> callback function. The callback function must do the following:

In the callback function's <i>SourceIdentificationDescription</i> and <i>DestinationIdentificationDescription</i> structures, find the pointers to dynamically allocated memory.

Copy the dynamically allocated memory from the source to the destination, using the pointers.

Copy other structure members from the callback function's <i>SourceIdentificationDescription</i> structure to the callback function's <i>DestinationIdentificationDescription</i> structure.

The only <a href="wdf.wdf_child-list_object_reference">framework child-list object method</a> that a driver's <i>EvtChildListIdentificationDescriptionCopy</i> callback function can call is <a href="wdf.wdfchildlistgetdevice">WdfChildListGetDevice</a>.

The framework acquires an internal child-list object lock before calling the <i>EvtChildListIdentificationDescriptionCopy</i> callback function. The callback function must only perform operations that are related to the copy operation, such as calling framework memory object methods and accessing object context space. It must not call methods that access other drivers.

If your driver supplies an <i>EvtChildListIdentificationDescriptionCopy</i> callback function, it might also need <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_duplicate.md">EvtChildListIdentificationDescriptionDuplicate</a>, <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_compare.md">EvtChildListIdentificationDescriptionCompare</a>, and <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_cleanup.md">EvtChildListIdentificationDescriptionCleanup</a> callback functions.

For more information about dynamic enumeration, see <a href="wdf.enumerating_the_devices_on_a_bus">Enumerating the Devices on a Bus</a>.

To define an <i>EvtChildListIdentificationDescriptionCopy</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtChildListIdentificationDescriptionCopy</i> callback function that is named <i>MyChildListIdentificationDescriptionCopy</i>, use the <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION</b> type as shown in this code example:

To define an <i>EvtChildListIdentificationDescriptionCopy</i> callback function that is named <b>MyChildListIdentificationDescriptionCopy</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:

Then, implement your callback function as follows:

The <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION</b> function type is defined in the WdfChildlist.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.

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
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>WdfChildlist.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_cleanup.md">EvtChildListIdentificationDescriptionCleanup</a>
</dt>
<dt>
<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_compare.md">EvtChildListIdentificationDescriptionCompare</a>
</dt>
<dt>
<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_duplicate.md">EvtChildListIdentificationDescriptionDuplicate</a>
</dt>
<dt>
<a href="wdf.wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>
</dt>
<dt>
<a href="wdf.wdfchildlistcreate">WdfChildListCreate</a>
</dt>
<dt>
<a href="wdf.wdfchildlistgetdevice">WdfChildListGetDevice</a>
</dt>
<dt>
<a href="wdf.wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

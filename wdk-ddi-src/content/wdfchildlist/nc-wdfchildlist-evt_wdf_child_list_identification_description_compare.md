---
UID: NC.wdfchildlist.EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE
title: EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE
author: windows-driver-content
description: A driver's EvtChildListIdentificationDescriptionCompare event callback function compares one child identification description with another.
old-location: wdf\evtchildlistidentificationdescriptioncompare.htm
old-project: wdf
ms.assetid: b807f9f8-588f-4303-be97-a9fd4cff2bbd
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _WDBGEXTS_THREAD_OS_INFO, WDBGEXTS_THREAD_OS_INFO, *PWDBGEXTS_THREAD_OS_INFO
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
req.alt-api: EvtChildListIdentificationDescriptionCompare
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

# EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE callback



## -description
<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtChildListIdentificationDescriptionCompare</i> event callback function compares one child identification description with another.



## -prototype

````
EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE EvtChildListIdentificationDescriptionCompare;

BOOLEAN EvtChildListIdentificationDescriptionCompare(
  _In_ WDFCHILDLIST                                 ChildList,
  _In_ PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER FirstIdentificationDescription,
  _In_ PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER SecondIdentificationDescription
)
{ ... }
````


## -parameters

### -param ChildList [in]

A handle to a framework child-list object.


### -param FirstIdentificationDescription [in]

A pointer to a <a href="wdf.wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies the one child identification description.


### -param SecondIdentificationDescription [in]

A pointer to a WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure that identifies another child identification description.


## -returns
The <i>EvtChildListIdentificationDescriptionCompare</i> callback function must return <b>TRUE</b> if the two child identification descriptions match. Otherwise, this function must return <b>FALSE</b>.


## -remarks
If a bus driver is using <a href="wdf.dynamic_enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListIdentificationDescriptionCompare</i> callback function by calling <a href="wdf.wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a> or <a href="wdf.wdfchildlistcreate">WdfChildListCreate</a>. The driver can also register a second, special-case <i>EvtChildListIdentificationDescriptionCompare</i> callback function when it calls <a href="wdf.wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a>.

The framework compares two identification descriptions when it must determine if both descriptions identify the same device.

The <i>EvtChildListIdentificationDescriptionCompare</i> callback function must compare the contents of two identification descriptions and return <b>TRUE</b> if they match. A driver must supply this callback function if the framework cannot call <a href="kernel.rtlcomparememory">RtlCompareMemory</a> to compare the identification descriptions. (The framework cannot call <b>RtlCompareMemory</b> if the descriptions contain pointers to additional memory.)

If your driver does not provide an <i>EvtChildListIdentificationDescriptionCompare</i> callback function, the framework compares identification descriptions by calling <a href="kernel.rtlcomparememory">RtlCompareMemory</a>.

The following steps describe a possible scenario:

The driver calls <a href="wdf.wdfchildlistretrieveaddressdescription">WdfChildListRetrieveAddressDescription</a> to obtain the address description that is associated with the framework's copy of an identification description, which is stored in a child list.

The framework traverses the child list. To determine if a child's identification description matches the one that the driver specified when it called <a href="wdf.wdfchildlistretrieveaddressdescription">WdfChildListRetrieveAddressDescription</a>, the framework calls either the <i>EvtChildListIdentificationDescriptionCompare</i> callback function (if it exists) or <a href="kernel.rtlcomparememory">RtlCompareMemory</a>.

If the two identification descriptions match (and the comparison returns <b>TRUE</b>), the framework stops traversing the list.

The framework copies the address description into memory that the driver supplied when it called <a href="wdf.wdfchildlistretrieveaddressdescription">WdfChildListRetrieveAddressDescription</a>.

The framework can use <a href="kernel.rtlcomparememory">RtlCompareMemory</a> to compare identification descriptions, if each description consists of a single structure with a predetermined size that is specified by the <b>IdentificationDescriptionSize</b> member of the <a href="wdf.wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure. However, sometimes the description must also contain additional information that is stored in dynamically allocated memory. In this case, you will typically define a description structure so that a member points to the dynamically allocated memory, and your driver must provide an <i>EvtChildListIdentificationDescriptionCompare</i> callback function. 

This callback function determines if two identification descriptions represent the same device. The callback function might not have to compare all of the structure members to make that determination. For example, suppose that an identification description contains a serial number and a set of hardware identifiers, as follows:

In this case, the <i>EvtChildListIdentificationDescriptionCompare</i> callback function probably has to compare only the <b>DeviceSerialNumber</b> members to determine if two descriptions represent the same device.

If your driver calls <a href="wdf.wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a> to traverse a device list, you can provide an additional <i>EvtChildListIdentificationDescriptionCompare</i> callback function that the framework uses when looking for the next description to retrieve. The framework looks for child devices that match driver-supplied <a href="wdf.wdf_retrieve_child_flags">WDF_RETRIEVE_CHILD_FLAGS</a>-typed flags. If a driver provides a special <i>EvtChildListIdentificationDescriptionCompare</i> callback function, the framework uses the callback function to refine the search. If the driver does not supply a special <i>EvtChildListIdentificationDescriptionCompare</i> callback function, the framework does <i>not</i> call <a href="kernel.rtlcomparememory">RtlCompareMemory</a>--it simply returns each child device that matches the specified flags. 

The only <a href="wdf.wdf_child-list_object_reference">framework child-list object method</a> that a driver's <i>EvtChildListIdentificationDescriptionCompare</i> callback function can call is <a href="wdf.wdfchildlistgetdevice">WdfChildListGetDevice</a>.

The framework acquires an internal child-list object lock before calling the <i>EvtChildListIdentificationDescriptionCompare</i><i>EvtChildListIdentificationDescriptionCompare</i> callback function. The callback function must only perform operations that are related to the compare operation, such as calling framework memory object methods and accessing object context space. It must not call methods that access other drivers.

For more information about dynamic enumeration, see <a href="wdf.enumerating_the_devices_on_a_bus">Enumerating the Devices on a Bus</a>.

To define an <i>EvtChildListIdentificationDescriptionCompare</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtChildListIdentificationDescriptionCompare</i> callback function that is named <i>MyChildListIdentificationDescriptionCompare</i>, use the <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE</b> type as shown in this code example:

Then, implement your callback function as follows:

The <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE</b> function type is defined in the WdfChildlist.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.


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
<a href="kernel.rtlcomparememory">RtlCompareMemory</a>
</dt>
<dt>
<a href="wdf.wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>
</dt>
<dt>
<a href="wdf.wdf_retrieve_child_flags">WDF_RETRIEVE_CHILD_FLAGS</a>
</dt>
<dt>
<a href="wdf.wdfchildlistcreate">WdfChildListCreate</a>
</dt>
<dt>
<a href="wdf.wdfchildlistgetdevice">WdfChildListGetDevice</a>
</dt>
<dt>
<a href="wdf.wdfchildlistretrieveaddressdescription">WdfChildListRetrieveAddressDescription</a>
</dt>
<dt>
<a href="wdf.wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a>
</dt>
<dt>
<a href="wdf.wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE callback function%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


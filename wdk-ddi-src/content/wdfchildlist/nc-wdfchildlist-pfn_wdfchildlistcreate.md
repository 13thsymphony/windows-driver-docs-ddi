---
UID: NC:wdfchildlist.PFN_WDFCHILDLISTCREATE
title: PFN_WDFCHILDLISTCREATE function
author: windows-driver-content
description: The WdfChildListCreate method creates a child list for a specified parent device.
old-location: wdf\wdfchildlistcreate.htm
old-project: wdf
ms.assetid: 88af6933-09f0-4248-9003-62f486d38645
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PFN_WDFCHILDLISTCREATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfChildListCreate
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: WDBGEXTS_THREAD_OS_INFO, *PWDBGEXTS_THREAD_OS_INFO
req.product: Windows 10 or later.
---

# PFN_WDFCHILDLISTCREATE function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListCreate</b> method creates a child list for a specified parent device.



## -syntax

````
NTSTATUS WdfChildListCreate(
  _In_     WDFDEVICE              Device,
  _In_     PWDF_CHILD_LIST_CONFIG Config,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES ChildListAttributes,
  _Out_    WDFCHILDLIST           *ChildList
);
````


## -parameters

### -param Device [in]

A handle to a framework device object that represents the parent device.


### -param Config [in]

A pointer to a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_config.md">WDF_CHILD_LIST_CONFIG</a> structure that contains driver-supplied configuration information for the child list.


### -param ChildListAttributes [in, optional]

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied object attributes for the framework child-list object. (The structure's <b>ParentObject</b> member must be <b>NULL</b>.) 


### -param ChildList [out]

A pointer to a caller-allocated location that receives a handle to a framework child-list object.


## -returns
<b>WdfChildListCreate</b> returns STATUS_SUCCESS, or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS(status)</a> equals <b>TRUE</b>, if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An input parameter was invalid.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>An object could not be allocated.

 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.



A system bug check occurs if the driver supplies an invalid object handle.



## -remarks
The framework creates a default child list for each framework device object that represents a functional device object (FDO). To use the default child list, the driver calls <a href="..\wdffdo\nf-wdffdo-wdffdogetdefaultchildlist.md">WdfFdoGetDefaultChildList</a>. If your driver requires additional child lists, it can call <b>WdfChildListCreate</b> to create them.

The parent of each child-list object is the device's framework device object. The driver cannot change this parent, and the <b>ParentObject</b> member or the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure must be <b>NULL</b>.

Your driver cannot delete the child-list object that <b>WdfChildListCreate</b> creates. The framework deletes the object at the proper time.

For more information about child lists, see <a href="https://msdn.microsoft.com/6e46b456-7d2d-4c6e-8692-7f310366387d">Dynamic Enumeration</a>.

The following code example initializes a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_config.md">WDF_CHILD_LIST_CONFIG</a> structure and then calls <b>WdfChildListCreate</b>.


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
<dt>Wdfchildlist.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="https://msdn.microsoft.com/51db6f3c-45cb-46a7-9dd4-2bab67893fea">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_config.md">WDF_CHILD_LIST_CONFIG</a>
</dt>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_list_config_init.md">WDF_CHILD_LIST_CONFIG_INIT</a>
</dt>
<dt>
<a href="..\wdffdo\nf-wdffdo-wdffdogetdefaultchildlist.md">WdfFdoGetDefaultChildList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfChildListCreate method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


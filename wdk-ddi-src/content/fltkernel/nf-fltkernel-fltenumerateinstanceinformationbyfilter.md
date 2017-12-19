---
UID: NF.fltkernel.FltEnumerateInstanceInformationByFilter
title: FltEnumerateInstanceInformationByFilter function
author: windows-driver-content
description: The FltEnumerateInstanceInformationByFilter routine provides information about instances of a given minifilter driver.
old-location: ifsk\fltenumerateinstanceinformationbyfilter.htm
old-project: ifsk
ms.assetid: c5590897-45cf-4712-b980-b99aaacfba88
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FltEnumerateInstanceInformationByFilter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltEnumerateInstanceInformationByFilter
req.alt-loc: FltMgr.lib,FltMgr.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: 
req.irql: <= APC_LEVEL
---

# FltEnumerateInstanceInformationByFilter function



## -description
The <b>FltEnumerateInstanceInformationByFilter</b> routine provides information about instances of a given minifilter driver.



## -syntax

````
NTSTATUS FltEnumerateInstanceInformationByFilter(
  _In_  PFLT_FILTER                Filter,
  _In_  ULONG                      Index,
  _In_  INSTANCE_INFORMATION_CLASS InformationClass,
  _Out_ PVOID                      Buffer,
  _In_  ULONG                      BufferSize,
  _Out_ PULONG                     BytesReturned
);
````


## -parameters

### -param Filter [in]

Opaque filter pointer for the caller. 


### -param Index [in]

Zero-based index of the instance for which the information is requested. 


### -param InformationClass [in]

Type of information requested. This parameter can have one of the following values. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>InstanceBasicInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="ifsk.instance_basic_information">INSTANCE_BASIC_INFORMATION</a> structure for the instance. 

</td>
</tr>
<tr>
<td>
<b>InstanceFullInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="ifsk.instance_full_information">INSTANCE_FULL_INFORMATION</a> structure for the instance. 

</td>
</tr>
<tr>
<td>
<b>InstancePartialInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="ifsk.instance_partial_information">INSTANCE_PARTIAL_INFORMATION</a> structure for the instance. 

</td>
</tr>
<tr>
<td>
<b>InstanceAggregateStandardInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="ifsk.instance_aggregate_standard_information">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a> structure for the instance.  The <i>LegacyFilter</i> portion of the structure is not utilized. This structure is available starting with Windows Vista.

</td>
</tr>
</table>
 


### -param Buffer [out]

Pointer to a caller-allocated buffer that receives the requested information. The type of the information returned in the buffer is defined by the <i>InformationClass</i> parameter. 


### -param BufferSize [in]

Size, in bytes, of the buffer that the <i>Buffer</i> parameter points to. The caller should set this parameter according to the given <i>InformationClass</i> value. 


### -param BytesReturned [out]

Pointer to a caller-allocated variable that receives the number of bytes returned in the buffer that <i>Buffer </i>points to. If the input value of <i>BufferSize</i> is too small, <b>FltEnumerateInstanceInformationByFilter</b> returns STATUS_BUFFER_TOO_SMALL and sets this variable to the number of bytes required to store the requested information. This parameter is required and cannot be <b>NULL</b>. 


## -returns
<b>FltEnumerateInstanceInformationByFilter</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The buffer that the <i>Buffer</i> parameter points to is not large enough to store the requested information. This is an error code. 
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>A matching instance was found, but it is being torn down. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid value was specified for the <i>InformationClass</i> parameter. For example, if <b>FilterAggregateStandardInformation</b> is specified on an operating system prior to Windows Vista, the routine will return STATUS_INVALID_PARAMETER.  This is an error code.
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>There are no more entries in the minifilter driver's instance list. This is a warning code. 

 


## -remarks
The <i>Index</i> parameter is simply a way for <b>FltEnumerateInstanceInformationByFilter </b>to select among instances in the instance list for the minifilter driver specified by <i>Filter</i>.  Because the minifilter driver instances in the instance list can change at any time, two calls to <b>FltEnumerateInstanceInformationByFilter </b>with the same <i>Index</i> and <i>Filter</i> values are not guaranteed to return the same result. 

To enumerate all registered minifilter drivers, call <a href="ifsk.fltenumeratefilters">FltEnumerateFilters</a>. 

To list filter information for all registered minifilter drivers, call <a href="ifsk.fltenumeratefilterinformation">FltEnumerateFilterInformation</a>. 

To get filter information for a given minifilter driver, call <a href="ifsk.fltgetfilterinformation">FltGetFilterInformation</a>. 

To enumerate all minifilter driver instances on a given volume, call <a href="ifsk.fltenumerateinstanceinformationbyvolume">FltEnumerateInstanceInformationByVolume</a>. 

To enumerate instances of all minifilter drivers on all volumes, call <a href="ifsk.fltenumerateinstances">FltEnumerateInstances</a>. 

To enumerate all volumes that are known to the Filter Manager, call <a href="ifsk.fltenumeratevolumes">FltEnumerateVolumes</a>. 

.


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
Header

</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include FltKernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fltenumeratefilterinformation">FltEnumerateFilterInformation</a>
</dt>
<dt>
<a href="ifsk.fltenumeratefilters">FltEnumerateFilters</a>
</dt>
<dt>
<a href="ifsk.fltenumerateinstanceinformationbyvolume">FltEnumerateInstanceInformationByVolume</a>
</dt>
<dt>
<a href="ifsk.fltenumeratevolumes">FltEnumerateVolumes</a>
</dt>
<dt>
<a href="ifsk.fltgetfilterinformation">FltGetFilterInformation</a>
</dt>
<dt>
<a href="ifsk.instance_aggregate_standard_information">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.instance_basic_information">INSTANCE_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.instance_full_information">INSTANCE_FULL_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.instance_partial_information">INSTANCE_PARTIAL_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltEnumerateInstanceInformationByFilter routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


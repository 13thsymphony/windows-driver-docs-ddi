---
UID: NF.fltkernel.FltEnumerateFilters
title: FltEnumerateFilters function
author: windows-driver-content
description: The FltEnumerateFilters routine enumerates all registered minifilter drivers in the system.
old-location: ifsk\fltenumeratefilters.htm
old-project: ifsk
ms.assetid: f39ff534-7b51-49b5-bb1f-7cb0e18b3cfc
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltEnumerateFilters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltEnumerateFilters
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

# FltEnumerateFilters function



## -description
The <b>FltEnumerateFilters</b> routine enumerates all registered minifilter drivers in the system. 



## -syntax

````
NTSTATUS FltEnumerateFilters(
  _Out_ PFLT_FILTER *FilterList,
  _In_  ULONG       FilterListSize,
  _Out_ PULONG      NumberFiltersReturned
);
````


## -parameters

### -param FilterList [out]

Pointer to a caller-allocated buffer that receives an array of opaque filter pointers. This parameter is optional and can be <b>NULL</b> if the value of <i>FilterListSize</i> parameter is zero. If <i>FilterListSize</i> is zero on input and <i>FilterList</i> is <b>NULL</b>, the <i>NumberFiltersReturned</i> parameter receives the number of minifilter drivers found. 


### -param FilterListSize [in]

Number of opaque filter pointers that the buffer that the <i>FilterList</i> parameter points to can hold. This parameter is optional and can be zero. If <i>FilterListSize</i> is zero on input and <i>FilterList</i> is <b>NULL</b>, the <i>NumberFiltersReturned</i> parameter receives the number of minifilter drivers found. 


### -param NumberFiltersReturned [out]

Pointer to a caller-allocated variable that receives the number of opaque filter pointers returned in the array that the <i>FilterList </i>parameter points to. If the <i>FilterListSize</i> parameter value is too small and <i>FilterList</i> is non-<b>NULL</b> on input, <b>FltEnumerateFilters</b> returns STATUS_BUFFER_TOO_SMALL and sets <i>NumberFiltersReturned</i> to point to the number of minifilter drivers found. This parameter is required and cannot be <b>NULL</b>. 


## -returns
<b>FltEnumerateFilters</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The buffer that the <i>FilterList</i> parameter points to is not large enough to store the requested information. This is an error code. 

 


## -remarks
Because filters can register at any time, two calls to <b>FltEnumerateFilters</b> are not guaranteed to return the same result. 

<b>FltEnumerateFilters</b> adds a rundown reference to each of the opaque filter pointers returned in the array that the <i>FilterList </i>parameter points to. When these pointers are no longer needed, the caller must release them by calling <a href="ifsk.fltobjectdereference">FltObjectDereference</a> on each one. Thus every successful call to <b>FltEnumerateFilters</b> must be matched by a subsequent call to <b>FltObjectDereference</b> for each returned filter pointer. 

To list filter information for all registered minifilter drivers, call <a href="ifsk.fltenumeratefilterinformation">FltEnumerateFilterInformation</a>. 

To enumerate instances of all minifilter drivers on all volumes, call <a href="ifsk.fltenumerateinstances">FltEnumerateInstances</a>. 

To enumerate all volumes that are known to the Filter Manager, call <a href="ifsk.fltenumeratevolumes">FltEnumerateVolumes</a>. 


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
<dt>Fltkernel.h (include Fltkernel.h)</dt>
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
<a href="ifsk.fltenumerateinstances">FltEnumerateInstances</a>
</dt>
<dt>
<a href="ifsk.fltenumeratevolumes">FltEnumerateVolumes</a>
</dt>
<dt>
<a href="ifsk.fltgetfilterinformation">FltGetFilterInformation</a>
</dt>
<dt>
<a href="ifsk.fltobjectdereference">FltObjectDereference</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltEnumerateFilters routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


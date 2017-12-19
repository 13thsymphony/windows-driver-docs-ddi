---
UID: NC.fltkernel.PFLT_FILTER_UNLOAD_CALLBACK
title: PFLT_FILTER_UNLOAD_CALLBACK
author: windows-driver-content
description: A minifilter driver can register a routine of type PFLT_FILTER_UNLOAD_CALLBACK as the minifilter driver's FilterUnloadCallback routine.
old-location: ifsk\pflt_filter_unload_callback.htm
old-project: ifsk
ms.assetid: 746f13f5-c92d-4dae-8fd7-4c9fdfa9e044
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IXpsPartIterator, IXpsPartIterator::Reset, Reset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FilterUnloadCallback
req.alt-loc: fltkernel.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# PFLT_FILTER_UNLOAD_CALLBACK callback



## -description
A minifilter driver can register a routine of type PFLT_FILTER_UNLOAD_CALLBACK as the minifilter driver's <i>FilterUnloadCallback</i> routine. 



## -prototype

````
PFLT_FILTER_UNLOAD_CALLBACK FilterUnloadCallback;

NTSTATUS FilterUnloadCallback(
   FLT_FILTER_UNLOAD_FLAGS Flags
)
{ ... }
````


## -parameters

### -param Flags 

Bitmask of flags describing the unload request. This parameter can be <b>NULL</b> or the following: 

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLTFL_FILTER_UNLOAD_MANDATORY

</td>
<td>
The filter manager sets this flag to indicate that the unload operation is mandatory. 

</td>
</tr>
</table>
 


## -returns
This callback routine returns STATUS_SUCCESS or an NTSTATUS value such as the following: 
<dl>
<dt><b>STATUS_FLT_DO_NOT_DETACH</b></dt>
</dl>If the unload operation is not mandatory, returning this status value prevents the minifilter driver from being unloaded. This is an error code. 

 


## -remarks
When a minifilter driver registers itself by calling <a href="ifsk.fltregisterfilter">FltRegisterFilter</a>, it can register a <i>FilterUnloadCallback</i> routine. To register this callback routine, the minifilter driver stores the address of a routine of type PFLT_FILTER_UNLOAD_CALLBACK in the <b>FilterUnloadCallback</b> field of the <a href="ifsk.flt_registration">FLT_REGISTRATION</a> structure that the minifilter driver passes as a parameter to <b>FltRegisterFilter</b>. 

Minifilter drivers are not required to register a <i>FilterUnloadCallback</i> routine. However, registering an unload routine is strongly recommended. If a minifilter driver does not register a <i>FilterUnloadCallback</i> routine, it cannot be unloaded. 

The filter manager calls the minifilter driver's <i>FilterUnloadCallback</i> routine to notify the minifilter driver that the filter manager is about to unload the minifilter driver. 

If the unload operation is not mandatory, and the <i>FilterUnloadCallback</i> routine returns an error or warning NTSTATUS code, such as STATUS_FLT_DO_NOT_DETACH, the minifilter driver is not unloaded. Otherwise, the minifilter driver is unloaded. 

If the FLTFL_FILTER_UNLOAD_MANDATORY flag is set in the <i>Flags</i> parameter, the unload operation is mandatory, and the minifilter driver cannot prevent itself from being unloaded. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
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
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.flt_registration">FLT_REGISTRATION</a>
</dt>
<dt>
<a href="ifsk.fltregisterfilter">FltRegisterFilter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PFLT_FILTER_UNLOAD_CALLBACK routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NC.fltkernel.PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK
title: PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK
author: windows-driver-content
description: A minifilter driver can register a routine of type PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK as the minifilter driver's InstanceQueryTeardownCallback routine.
old-location: ifsk\pflt_instance_query_teardown_callback.htm
old-project: ifsk
ms.assetid: 5aa41472-cb1d-49ba-a546-ec42bb859552
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: DrvPopulateFilterServices
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
req.alt-api: InstanceQueryTeardownCallback
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

# PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK callback



## -description
A minifilter driver can register a routine of type <i>PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</i> as the minifilter driver's <i>InstanceQueryTeardownCallback</i> routine. 



## -prototype

````
PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK InstanceQueryTeardownCallback;

NTSTATUS InstanceQueryTeardownCallback(
  _In_ PCFLT_RELATED_OBJECTS             FltObjects,
  _In_ FLT_INSTANCE_QUERY_TEARDOWN_FLAGS Flags
)
{ ... }
````


## -parameters

### -param FltObjects [in]

Pointer to an <a href="ifsk.flt_related_objects">FLT_RELATED_OBJECTS</a> structure that contains opaque pointers for the objects related to the current operation. 


### -param Flags [in]

Bitmask of flags that describe why the given instance query teardown callback routine was called. No flags are currently defined. 


## -returns
This callback routine returns <b>STATUS_SUCCESS</b> or an <b>NTSTATUS</b> value such as one of the following: 
<dl>
<dt><b>STATUS_FLT_DO_NOT_DETACH</b></dt>
</dl>Returning this status value prevents the minifilter driver instance from being detached. This is an error code. 

 


## -remarks
When a minifilter driver registers itself by calling <a href="ifsk.fltregisterfilter">FltRegisterFilter</a> from its <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine, it can register a routine of type <i>PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</i> as the minifilter driver's <i>InstanceQueryTeardownCallback</i> routine. 

To register the <i>InstanceQueryTeardownCallback</i> routine, the minifilter driver stores the address of a routine of type <i>PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</i> in the <i>InstanceQueryTeardownCallback</i> member of the <a href="ifsk.flt_registration">FLT_REGISTRATION</a> structure that the minifilter driver passes as the <i>Registration</i> parameter of <a href="ifsk.fltregisterfilter">FltRegisterFilter</a>. 

The filter manager calls this routine to allow the minifilter driver to respond to a manual detach request. Such a request is received when a user-mode application calls <a href="ifsk.filterdetach">FilterDetach</a> or a kernel-mode component calls <a href="ifsk.fltdetachvolume">FltDetachVolume</a>. 

This routine is not called for automatic or mandatory detach requests, for example, when the minifilter driver is unloaded or a volume is dismounted. 

If this routine returns an error or warning <b>NTSTATUS</b> code, such as <b>STATUS_FLT_DO_NOT_DETACH</b>, the minifilter driver instance is not detached from the volume. Otherwise, the instance is detached. 

If a minifilter driver does not define an <i>InstanceQueryTeardownCallback</i> routine, its instances cannot be detached manually by calling <a href="ifsk.filterdetach">FilterDetach</a> or <a href="ifsk.fltdetachvolume">FltDetachVolume</a>. 


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
<a href="ifsk.filterdetach">FilterDetach</a>
</dt>
<dt>
<a href="ifsk.flt_registration">FLT_REGISTRATION</a>
</dt>
<dt>
<a href="ifsk.flt_related_objects">FLT_RELATED_OBJECTS</a>
</dt>
<dt>
<a href="ifsk.fltdetachvolume">FltDetachVolume</a>
</dt>
<dt>
<a href="ifsk.fltregisterfilter">FltRegisterFilter</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_instance_setup_callback.md">PFLT_INSTANCE_SETUP_CALLBACK</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_instance_teardown_callback.md">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


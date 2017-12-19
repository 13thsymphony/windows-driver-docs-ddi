---
UID: NF.fltkernel.FltDetachVolume
title: FltDetachVolume function
author: windows-driver-content
description: FltDetachVolume detaches a minifilter driver instance from a volume.
old-location: ifsk\fltdetachvolume.htm
old-project: ifsk
ms.assetid: 889750fc-69a9-4fe6-8905-6a7edc5c04fb
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FltDetachVolume
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
req.alt-api: FltDetachVolume
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

# FltDetachVolume function



## -description
<b>FltDetachVolume</b> detaches a minifilter driver instance from a volume. 



## -syntax

````
NTSTATUS FltDetachVolume(
  _Inout_  PFLT_FILTER      Filter,
  _Inout_  PFLT_VOLUME      Volume,
  _In_opt_ PCUNICODE_STRING InstanceName
);
````


## -parameters

### -param Filter [in, out]

Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param Volume [in, out]

Opaque volume pointer for the volume where the instance is attached. This parameter is required and cannot be <b>NULL</b>. 


### -param InstanceName [in, optional]

Pointer to a <a href="kernel.unicode_string">UNICODE_STRING</a> structure containing the instance name for the instance to be removed. This parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, the highest matching instance is removed. 


## -returns
<b>FltDetachVolume</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl><b>FltDetachVolume</b> found a matching instance, but the instance is being torn down. This is an error code. 
<dl>
<dt><b>STATUS_FLT_INSTANCE_NOT_FOUND</b></dt>
</dl>No matching instance was found. This is an error code. 

 


## -remarks
<b>FltDetachVolume</b> detaches a minifilter driver instance from a volume and tears down the instance. 

To attach a minifilter driver instance to a volume, call <a href="ifsk.fltattachvolume">FltAttachVolume</a> or <a href="ifsk.fltattachvolumeataltitude">FltAttachVolumeAtAltitude</a>. 

To compare the altitudes of two minifilter driver instances attached to the same volume, call <a href="ifsk.fltcompareinstancealtitudes">FltCompareInstanceAltitudes</a>. 


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
<a href="ifsk.fltattachvolume">FltAttachVolume</a>
</dt>
<dt>
<a href="ifsk.fltattachvolumeataltitude">FltAttachVolumeAtAltitude</a>
</dt>
<dt>
<a href="ifsk.fltcompareinstancealtitudes">FltCompareInstanceAltitudes</a>
</dt>
<dt>
<a href="ifsk.fltgetvolumeinstancefromname">FltGetVolumeInstanceFromName</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltDetachVolume function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


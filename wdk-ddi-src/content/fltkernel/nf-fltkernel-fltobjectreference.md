---
UID: NF.fltkernel.FltObjectReference
title: FltObjectReference function
author: windows-driver-content
description: The FltObjectReference routine adds a rundown reference to an opaque filter, instance, or volume pointer.
old-location: ifsk\fltobjectreference.htm
old-project: ifsk
ms.assetid: ad6317bf-92fc-4e77-9993-37b7aa123a3d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FltObjectReference
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
req.alt-api: FltObjectReference
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= DISPATCH_LEVEL
---

# FltObjectReference function



## -description
The <b>FltObjectReference</b> routine adds a rundown reference to an opaque filter, instance, or volume pointer. 



## -syntax

````
NTSTATUS FltObjectReference(
  _Inout_ PVOID FltObject
);
````


## -parameters

### -param FltObject [in, out]

Opaque filter pointer (PFLT_FILTER), instance pointer (PFLT_INSTANCE), or volume pointer (PFLT_VOLUME). 


## -returns
<b>FltObjectReference</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>The minifilter driver, instance, or volume is being torn down. This is an error code. 

 


## -remarks
Adding a rundown reference to an opaque filter, instance, or volume object pointer prevents the object from being freed. 

To remove a rundown reference from an opaque filter, instance, or volume pointer, call <a href="ifsk.fltobjectdereference">FltObjectDereference</a>. 


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
DLL

</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
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
<a href="ifsk.fltobjectdereference">FltObjectDereference</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltObjectReference routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


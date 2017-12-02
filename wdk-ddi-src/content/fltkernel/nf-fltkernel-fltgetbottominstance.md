---
UID: NF.fltkernel.FltGetBottomInstance
title: FltGetBottomInstance
author: windows-driver-content
description: FltGetBottomInstance returns an opaque instance pointer for the minifilter driver instance, if there is one, that is attached at the bottom of the instance stack for a given volume.
old-location: ifsk\fltgetbottominstance.htm
old-project: ifsk
ms.assetid: a5e7379a-6501-4245-92ce-0474baa33e2c
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltGetBottomInstance
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
req.alt-api: FltGetBottomInstance
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
req.irql: <= APC_LEVEL
req.iface: 
---

# FltGetBottomInstance function



## -description
<p><b>FltGetBottomInstance</b> returns an opaque instance pointer for the minifilter driver instance, if there is one, that is attached at the bottom of the instance stack for a given volume. </p>


## -syntax

````
NTSTATUS FltGetBottomInstance(
  _In_  PFLT_VOLUME   Volume,
  _Out_ PFLT_INSTANCE *Instance
);
````


## -parameters
<dl>

### -param Volume [in]

<dd>
<p>Opaque pointer for the volume. </p>
</dd>

### -param Instance [out]

<dd>
<p>Pointer to a caller-allocated variable that receives an opaque instance pointer for the bottom instance for this volume. This parameter is required and cannot be <b>NULL</b>. </p>
</dd>
</dl>

## -returns
<p><b>FltGetBottomInstance</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: </p><dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl><p>No matching instance was found. This is a warning code. </p>

<p> </p>

## -remarks
<p>An instance is said to be at the <i>bottom</i> of the minifilter driver instance stack if its altitude is lower than that of all other instances attached to the same volume. The term "altitude" refers to the position that an instance occupies in the minifilter driver instance stack for a volume. The higher the altitude, the farther the instance is from the base file system in the stack. Only one instance can be attached at a given altitude on a given volume. </p>

<p>Altitude is specified by an <i>altitude string</i>, which is a counted Unicode string consisting of one or more decimal digits from 0 through 9, and it can include a single decimal point. For example, "100.123456" and "03333" are valid altitude strings. </p>

<p>The string "03333" represents a higher altitude than "100.123456". (Leading and trailing zeros are ignored.) In other words, an instance whose altitude is "03333" is farther from the base file system than an instance whose altitude is "100.123456". However, this comparison is only meaningful if both instances are attached to the same volume. </p>

<p><b>FltGetBottomInstance</b> adds a rundown reference to the opaque instance pointer returned in *<i>Instance</i>. When this pointer is no longer needed, the caller must release it by calling <a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>. Thus every successful call to <b>FltGetBottomInstance</b> must be matched by a subsequent call to <b>FltObjectDereference</b>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltattachvolume.md">FltAttachVolume</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltattachvolumeataltitude.md">FltAttachVolumeAtAltitude</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcompareinstancealtitudes.md">FltCompareInstanceAltitudes</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetlowerinstance.md">FltGetLowerInstance</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgettopinstance.md">FltGetTopInstance</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetupperinstance.md">FltGetUpperInstance</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetBottomInstance function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

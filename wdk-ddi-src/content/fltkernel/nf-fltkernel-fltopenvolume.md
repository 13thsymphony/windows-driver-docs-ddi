---
UID: NF.fltkernel.FltOpenVolume
title: FltOpenVolume function
author: windows-driver-content
description: The FltOpenVolume routine returns a handle and a file object pointer for the file system volume that a given minifilter driver instance is attached to.
old-location: ifsk\fltopenvolume.htm
old-project: ifsk
ms.assetid: 99cfa1eb-3d0f-4e27-9884-f5789ee328c3
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltOpenVolume
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP3, Windows Server 2003 SP1, and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltOpenVolume
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
req.irql: PASSIVE_LEVEL
---

# FltOpenVolume function



## -description
The <b>FltOpenVolume</b> routine returns a handle and a file object pointer for the file system volume that a given minifilter driver instance is attached to. 


## -syntax

````
NTSTATUS FltOpenVolume(
  _In_  PFLT_INSTANCE Instance,
  _Out_ PHANDLE       VolumeHandle,
  _Out_ PFILE_OBJECT  *VolumeFileObject
);
````


## -parameters

### -param Instance [in]

Opaque instance pointer for the instance. This instance must be attached to a local volume. 

### -param VolumeHandle [out]

Handle for the file system volume. 

### -param VolumeFileObject [out]

Pointer to a caller-allocated variable that receives a file object pointer for the root directory of the volume. This parameter is optional and can be <b>NULL</b>. 

## -returns
<b>FltOpenVolume</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>The instance or volume is being torn down. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The instance is attached to a network volume. This is an error code. 

 

## -remarks
When the handle returned in the <i>VolumeHandle</i> parameter is no longer needed, the caller must release it by calling <a href="ifsk.fltclose">FltClose</a>. Thus every successful call to <b>FltOpenVolume</b> must be matched by a subsequent call to <b>FltClose</b>. 

If a file object pointer is returned in the <i>VolumeFileObject</i> parameter, the caller must release it when it is no longer needed by calling <a href="kernel.obdereferenceobject">ObDereferenceObject</a>. 

The instance specified by the <i>Instance</i> parameter must be attached to a local volume. If it is attached to a network volume, <b>FltOpenVolume</b> returns STATUS_INVALID_PARAMETER. 

To get a pointer to the device object for a given volume, call <a href="ifsk.fltgetdeviceobject">FltGetDeviceObject</a>. 

To get detailed information about the volume that a given instance is attached to, call <a href="ifsk.fltqueryvolumeinformation">FltQueryVolumeInformation</a>. 

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
Version
</th>
<td width="70%">
Available in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP3, Windows Server 2003 SP1, and later versions of the Windows operating system.
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
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fltclose">FltClose</a>
</dt>
<dt>
<a href="ifsk.fltgetdeviceobject">FltGetDeviceObject</a>
</dt>
<dt>
<a href="ifsk.fltgetfilterfrominstance">FltGetFilterFromInstance</a>
</dt>
<dt>
<a href="ifsk.fltobjectdereference">FltObjectDereference</a>
</dt>
<dt>
<a href="ifsk.fltqueryvolumeinformation">FltQueryVolumeInformation</a>
</dt>
<dt>
<a href="kernel.obdereferenceobject">ObDereferenceObject</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltOpenVolume routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

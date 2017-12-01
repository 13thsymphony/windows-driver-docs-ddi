---
UID: NS.d3dkmthk._D3DKMT_CREATESYNCHRONIZATIONOBJECT
title: D3DKMT_CREATESYNCHRONIZATIONOBJECT
author: windows-driver-content
description: The D3DKMT_CREATESYNCHRONIZATIONOBJECT structure describes a synchronization object that the D3DKMTCreateSynchronizationObject function creates.
old-location: display\d3dkmt_createsynchronizationobject.htm
old-project: display
ms.assetid: 2e4e1fd7-9a36-4c35-8d9d-932a0d2e60a2
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_CREATESYNCHRONIZATIONOBJECT, D3DKMT_CREATESYNCHRONIZATIONOBJECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_CREATESYNCHRONIZATIONOBJECT
req.alt-loc: d3dkmthk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
---

# D3DKMT_CREATESYNCHRONIZATIONOBJECT structure



## -description
<p>The D3DKMT_CREATESYNCHRONIZATIONOBJECT structure describes a synchronization object that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatesynchronizationobject.md">D3DKMTCreateSynchronizationObject</a> function creates.</p>


## -syntax

````
typedef struct _D3DKMT_CREATESYNCHRONIZATIONOBJECT {
  D3DKMT_HANDLE                    hDevice;
  D3DDDI_SYNCHRONIZATIONOBJECTINFO Info;
  D3DKMT_HANDLE                    hSyncObject;
} D3DKMT_CREATESYNCHRONIZATIONOBJECT;
````


## -struct-fields
<dl>

### -field <b>hDevice</b>

<dd>
<p>[in] A handle to the device that the synchronization object is associated with.</p>
</dd>

### -field <b>Info</b>

<dd>
<p>[in] A <a href="..\d3dukmdt\ns-d3dukmdt--d3dddi-synchronizationobjectinfo.md">D3DDDI_SYNCHRONIZATIONOBJECTINFO</a> structure that describes information about the kernel-mode synchronization object.</p>
</dd>

### -field <b>hSyncObject</b>

<dd>
<p>[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the kernel-mode synchronization object. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt--d3dddi-synchronizationobjectinfo.md">D3DDDI_SYNCHRONIZATIONOBJECTINFO</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatesynchronizationobject.md">D3DKMTCreateSynchronizationObject</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CREATESYNCHRONIZATIONOBJECT structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

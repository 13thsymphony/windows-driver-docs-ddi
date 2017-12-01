---
UID: NF.d3dkmthk.D3DKMTCreatePagingQueue
title: D3DKMTCreatePagingQueue
author: windows-driver-content
description: D3DKMTCreatePagingQueue is used to create a device paging queue that can be used to synchronize with video memory management operations for the device, such as making the device resource resident.
old-location: display\d3dkmtcreatepagingqueue.htm
old-project: display
ms.assetid: B95ADBC5-35CC-486D-A5C7-0950ABF4B70A
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMTCreatePagingQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTCreatePagingQueue
req.alt-loc: GDI32.dll,API-MS-Win-DX-D3DKMT-L1-1-1.dll,GDI32.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: GDI32.lib
req.dll: GDI32.dll
req.irql: 
req.iface: 
---

# D3DKMTCreatePagingQueue function



## -description
<p><b>D3DKMTCreatePagingQueue</b> is used to create a device paging queue that can be used to synchronize with video memory management operations for the device, such as making the device resource resident.</p>


## -syntax

````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTCreatePagingQueue(
  _Inout_ D3DKMT_CREATEPAGINGQUEUE *pData
);
````


## -parameters
<dl>

### -param <i>pData</i> [in, out]

<dd>
<p>A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk--d3dkmt-createpagingqueue.md">D3DKMT_CREATEPAGINGQUEUE</a> structure that describes the operation.</p>
</dd>
</dl>

## -returns
<p>Returns one of the following values:</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The operation was performed successfully.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl><p>
         Parameters were validated and determined to be incorrect.</p>

<p> </p>

<p>This function might also return other <b>NTSTATUS</b> values.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
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
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>GDI32.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>GDI32.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk--d3dkmt-createpagingqueue.md">D3DKMT_CREATEPAGINGQUEUE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTCreatePagingQueue function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

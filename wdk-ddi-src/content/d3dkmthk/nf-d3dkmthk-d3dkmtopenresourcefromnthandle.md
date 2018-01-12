---
UID: NF:d3dkmthk.D3DKMTOpenResourceFromNtHandle
title: D3DKMTOpenResourceFromNtHandle function
author: windows-driver-content
description: Opens a shared resource from an NT handle.
old-location: display\d3dkmtopenresourcefromnthandle.htm
old-project: display
ms.assetid: d5a66102-782a-482e-8119-48015820d0c7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTOpenResourceFromNtHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTOpenResourceFromNtHandle
req.alt-loc: Gdi32.dll,API-MS-Win-dx-d3dkmt-l1-1-0.dll,API-MS-Win-dx-d3dkmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTOpenResourceFromNtHandle function



## -description
Opens a shared resource from an NT handle.



## -syntax

````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTOpenResourceFromNtHandle(
  _Inout_ D3DKMT_OPENRESOURCEFROMNTHANDLE *pData
);
````


## -parameters

### -param pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openresourcefromnthandle.md">D3DKMT_OPENRESOURCEFROMNTHANDLE</a> structure that describes information required to open a shared resource.


## -returns
Returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function completed successfully.
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>
         Parameters were validated and determined to be incorrect.

 

This function might also return other NTSTATUS values.


## -remarks
 The NT handle to the process, which is used as the <b>hNtHandle</b> member of the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openresourcefromnthandle.md">D3DKMT_OPENRESOURCEFROMNTHANDLE</a> structure, is typically acquired by calling the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtshareobjects.md">D3DKMTShareObjects</a> or <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopennthandlefromname.md">D3DKMTOpenNtHandleFromName</a>  functions.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
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
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Gdi32.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Gdi32.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openresourcefromnthandle.md">D3DKMT_OPENRESOURCEFROMNTHANDLE</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopennthandlefromname.md">D3DKMTOpenNtHandleFromName</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtshareobjects.md">D3DKMTShareObjects</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTOpenResourceFromNtHandle function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


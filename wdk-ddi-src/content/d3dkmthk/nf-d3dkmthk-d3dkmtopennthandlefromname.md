---
UID: NF.d3dkmthk.D3DKMTOpenNtHandleFromName
title: D3DKMTOpenNtHandleFromName function
author: windows-driver-content
description: From a given graphics adapter name, opens an NT handle to the process.
old-location: display\d3dkmtopennthandlefromname.htm
old-project: display
ms.assetid: bcd33f64-7ad0-4e26-af73-e4f2b1b6e5fb
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3DKMTOpenNtHandleFromName
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
req.alt-api: D3DKMTOpenNtHandleFromName
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
---

# D3DKMTOpenNtHandleFromName function



## -description
From a given graphics adapter name, opens an NT handle to the process.



## -syntax

````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTOpenNtHandleFromName(
  _Inout_ D3DKMT_OPENNTHANDLEFROMNAME *pData
);
````


## -parameters

### -param pData [in, out]

A pointer to a <a href="display.d3dkmt_opennthandlefromname">D3DKMT_OPENNTHANDLEFROMNAME</a> structure that describes information required to open an NT handle.


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
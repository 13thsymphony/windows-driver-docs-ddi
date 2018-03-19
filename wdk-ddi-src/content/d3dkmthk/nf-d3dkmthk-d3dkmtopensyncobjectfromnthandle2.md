---
UID: NF:d3dkmthk.D3DKMTOpenSyncObjectFromNtHandle2
title: D3DKMTOpenSyncObjectFromNtHandle2 function
author: windows-driver-content
description: D3DKMTOpenSyncObjectFromNtHandle2 opens a monitored fence object from an NT handle previously created by D3DKMTShareObjects.
old-location: display\d3dkmtopensyncobjectfromnthandle2.htm
old-project: display
ms.assetid: E3295F4F-AB51-4EBB-8B9F-E47BBA52AF47
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTOpenSyncObjectFromNtHandle2, D3DKMTOpenSyncObjectFromNtHandle2 function [Display Devices], d3dkmthk/D3DKMTOpenSyncObjectFromNtHandle2, display.d3dkmtopensyncobjectfromnthandle2
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTOpenSyncObjectFromNtHandle2
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTOpenSyncObjectFromNtHandle2 function
<b>D3DKMTOpenSyncObjectFromNtHandle2</b> opens a monitored fence object from an NT handle previously created by <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtshareobjects.md">D3DKMTShareObjects</a>.

## Syntax

````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTOpenSyncObjectFromNtHandle2(
  _Inout_ D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *pData
);
````

## Parameters

This function has no parameters.

## Return Value

Returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation was performed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>
</td>
<td width="60%">

         Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** | GDI32.lib |
| **DLL** | GDI32.dll |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtshareobjects.md">D3DKMTShareObjects</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_opensyncobjectfromnthandle2.md">D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2</a>
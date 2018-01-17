---
UID: NF:d3dkmthk.D3DKMTCreateDCFromMemory
title: D3DKMTCreateDCFromMemory function
author: windows-driver-content
description: The D3DKMTCreateDCFromMemory function creates a display context from a specified block of memory.
old-location: display\d3dkmtcreatedcfrommemory.htm
old-project: display
ms.assetid: c02f53d9-7cf2-4420-9aea-4dba916be786
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTCreateDCFromMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTCreateDCFromMemory
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

# D3DKMTCreateDCFromMemory function



## -description
The <b>D3DKMTCreateDCFromMemory</b> function creates a display context from a specified block of memory.



## -syntax

````
NTSTATUS D3DKMTCreateDCFromMemory(
  _Inout_ D3DKMT_CREATEDCFROMMEMORY *pData
);
````


## -parameters

### -param pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createdcfrommemory.md">D3DKMT_CREATEDCFROMMEMORY</a> structure that describes parameters for creating a display context.


## -returns
<b>D3DKMTCreateDCFromMemory</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The display context was successfully created.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other <b>NTSTATUS</b> values.


## -remarks
The kernel controls the memory referenced by the display context created by the <b>D3DKMTCreateDCFromMemory</b> function. You must call the  <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtdestroydcfrommemory.md">D3DKMTDestoryDCFromMemory</a> function to free the memory referenced by the display context. Any  other approach  to free this memory will fail. 

During the execution of the <b>D3DKMTCreateDCFromMemory</b> function, the kernel locks and probes the referenced memory by performing a non-thread safe write to each page in the memory. No other threads in your process should be trying to access any part of this memory for the duration of the <b>D3DKMTCreateDCFromMemory</b> call; otherwise, the results will be undefined.


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createdcfrommemory.md">D3DKMT_CREATEDCFROMMEMORY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTCreateDCFromMemory function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


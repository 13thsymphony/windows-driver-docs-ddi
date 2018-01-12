---
UID: NS:d3dkmthk._D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2
title: _D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2
author: windows-driver-content
description: The D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 structure contains information about the synchronization events that the D3DKMTWaitForSynchronizationObject2 function waits for to occur.
old-location: display\d3dkmt_waitforsynchronizationobject2.htm
old-project: display
ms.assetid: 934bfe32-b54b-477c-a5f8-714caa97f233
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2, D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2
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
req.typenames: D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2
---

# _D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 structure



## -description
The D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 structure contains information about the synchronization events that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtwaitforsynchronizationobject2.md">D3DKMTWaitForSynchronizationObject2</a> function waits for to occur. 



## -syntax

````
typedef struct _D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 {
  D3DKMT_HANDLE hContext;
  UINT          ObjectCount;
  D3DKMT_HANDLE ObjectHandleArray[D3DDDI_MAX_OBJECT_WAITED_ON];
  union {
    struct {
      UINT64 FenceValue;
    } Fence;
    UINT64 Reserved[8];
  };
} D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2;
````


## -struct-fields

### -field hContext

[in] A kernel-mode handle to the context stream in which a wait for the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies is inserted.


### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array. 


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events that the context that is specified by the <b>hContext</b> member waits for. The D3DDDI_MAX_OBJECT_WAITED_ON constant, which is defined as 32, indicates the maximum number of synchronization events that the context can wait for.


### -field Fence

A structure that contains information about a fence. The union in D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 can hold a Fence structure, which contains the following member:


### -field FenceValue

A 64-bit value that specifies the fence value to wait for. 

</dd>
</dl>

### -field Reserved

An array of 64-bit values that are reserved for future use. The union in D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 can hold this array. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 is supported beginning with the Windows 7 operating system. 

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
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtwaitforsynchronizationobject2.md">D3DKMTWaitForSynchronizationObject2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


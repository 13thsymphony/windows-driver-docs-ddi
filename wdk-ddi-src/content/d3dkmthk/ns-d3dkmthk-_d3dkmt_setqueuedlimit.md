---
UID: NS:d3dkmthk._D3DKMT_SETQUEUEDLIMIT
title: _D3DKMT_SETQUEUEDLIMIT
author: windows-driver-content
description: The D3DKMT_SETQUEUEDLIMIT structure describes parameters for setting or retrieving the limit for the number of operations of the given type that can be queued for the given device.
old-location: display\d3dkmt_setqueuedlimit.htm
old-project: display
ms.assetid: 4fe525b1-9c06-4e2c-9e57-041164905efe
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_SETQUEUEDLIMIT, D3DKMT_SETQUEUEDLIMIT
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
req.alt-api: D3DKMT_SETQUEUEDLIMIT
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
req.typenames: D3DKMT_SETQUEUEDLIMIT
---

# _D3DKMT_SETQUEUEDLIMIT structure



## -description
The D3DKMT_SETQUEUEDLIMIT structure describes parameters for setting or retrieving the limit for the number of operations of the given type that can be queued for the given device. 



## -syntax

````
typedef struct _D3DKMT_SETQUEUEDLIMIT {
  D3DKMT_HANDLE           hDevice;
  D3DKMT_QUEUEDLIMIT_TYPE Type;
  union {
    UINT   QueuedPresentLimit;
    struct {
      D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
      UINT                           QueuedPendingFlipLimit;
    };
  };
} D3DKMT_SETQUEUEDLIMIT;
````


## -struct-fields

### -field hDevice

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the device to set or retrieve the limit of queued operations for.


### -field Type

[in] A <a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_queuedlimit_type.md">D3DKMT_QUEUEDLIMIT_TYPE</a>-typed value that indicates the type of operations to set or retrieve the queued limit for. 


### -field QueuedPresentLimit

[in/out] The limit for the number of present operations that can be queued for the device that is specified by <b>hDevice</b>. If the OpenGL installable client driver (ICD) sets <b>QueuedPresentLimit</b> to 0, the limit for the device is reset to the graphics adapter's default value, which is currently 3. The union that is contained in D3DKMT_SETQUEUEDLIMIT contains the limiting number if the <b>Type</b> member is D3DKMT_SET_QUEUEDLIMIT_PRESENT and retrieves the number if <b>Type</b> is D3DKMT_GET_QUEUEDLIMIT_PRESENT. 


### -field VidPnSourceId

[in] An integer that identifies a video present source that is in the path of a video present network (VidPN) topology. The union that is contained in D3DKMT_SETQUEUEDLIMIT contains the integer if the present operations are flips. 


### -field QueuedPendingFlipLimit

[in/out] The limit for the number of flip operations that can be queued for the device that is specified by <b>hDevice</b>. If the OpenGL ICD sets <b>QueuedPendingFlipLimit</b> to 0, the limit for the device is reset to the graphics adapter's default value, which is currently 1. The union that is contained in D3DKMT_SETQUEUEDLIMIT contains the limiting number if the present operations are flips. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

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
<a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_queuedlimit_type.md">D3DKMT_QUEUEDLIMIT_TYPE</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetqueuedlimit.md">D3DKMTSetQueuedLimit</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SETQUEUEDLIMIT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


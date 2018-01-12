---
UID: NS:video._STATUS_BLOCK
title: _STATUS_BLOCK
author: windows-driver-content
description: The STATUS_BLOCK structure is a substructure within the VIDEO_REQUEST_PACKET structure. A miniport driver's HwVidStartIO function must set the status block of each VRP that it gets.
old-location: display\status_block.htm
old-project: display
ms.assetid: 8e3126df-d081-4545-a5db-8637ee27f15b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _STATUS_BLOCK, STATUS_BLOCK, *PSTATUS_BLOCK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STATUS_BLOCK
req.alt-loc: video.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
req.typenames: STATUS_BLOCK, *PSTATUS_BLOCK
req.product: Windows 10 or later.
---

# _STATUS_BLOCK structure



## -description
The STATUS_BLOCK structure is a substructure within the VIDEO_REQUEST_PACKET structure. A miniport driver's <a href="..\video\nc-video-pvideo_hw_start_io.md">HwVidStartIO</a> function must set the status block of each <a href="wdkgloss.v#wdkgloss.video_request_packet__vrp_#wdkgloss.video_request_packet__vrp_"><i>VRP</i></a> that it gets.



## -syntax

````
typedef struct _STATUS_BLOCK {
  union {
    VP_STATUS Status;
    PVOID     Pointer;
  };
  ULONG_PTR Information;
} STATUS_BLOCK, *PSTATUS_BLOCK;
````


## -struct-fields

### -field Status

Indicates the result of the requested operation. This member might be one of the following status codes:




### -field ERROR_INSUFFICIENT_BUFFER

Either the VRP <b>InputBuffer</b> is too small to provide the data required to process the given request or the <b>OutputBuffer</b> is too small to return the requested data.

</dd>
</dl>



### -field ERROR_INVALID_FUNCTION

The miniport driver does not handle this request.

</dd>
</dl>



### -field ERROR_INVALID_PARAMETER

A parameter in the VRP is invalid.

</dd>
</dl>



### -field ERROR_IO_PENDING

An operation has not yet completed.

</dd>
</dl>



### -field ERROR_MORE_DATA

The driver has additional data to be returned but has already filled the given VRP <b>OutputBuffer</b>.

</dd>
</dl>



### -field ERROR_NOT_ENOUGH_MEMORY

There is insufficient memory to process the request.

</dd>
</dl>



### -field NO_ERROR

The requested operation has been carried out and completed successfully.

</dd>
</dl>

### -field Pointer

Should be ignored by the miniport driver. This member of the union exists to guarantee field alignment across 32- and 64-bit systems.


### -field Information

Supplies additional information about the completed operation. The meaning of the value varies according to VRP. Generally, this member is used to return the minimum size required for the input buffer if the VRP passes data in the <b>InputBuffer</b>. Alternatively, it contains the number of bytes of data transferred if the requested operation returns data in the VRP <b>OutputBuffer</b>.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\video\nc-video-pvideo_hw_start_io.md">HwVidStartIO</a>
</dt>
<dt>
<a href="..\video\ns-video-_video_request_packet.md">VIDEO_REQUEST_PACKET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20STATUS_BLOCK structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


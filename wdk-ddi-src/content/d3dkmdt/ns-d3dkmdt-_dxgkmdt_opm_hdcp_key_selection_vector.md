---
UID: NS.D3DKMDT._DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR
title: _DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR
author: windows-driver-content
description: The DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR structure contains a key-selection vector (KSV) for a High-bandwidth Digital Content Protection (HDCP) protected output.
old-location: display\dxgkmdt_opm_hdcp_key_selection_vector.htm
old-project: display
ms.assetid: a69eae04-a7e0-4d0c-a3e0-d49905096c8e
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR, DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR
req.alt-loc: d3dkmdt.h
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
---

# _DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR structure



## -description
The DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR structure contains a key-selection vector (KSV) for a High-bandwidth Digital Content Protection (HDCP) protected output.



## -syntax

````
typedef struct _DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR {
  BYTE abKeySelectionVector[DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR_SIZE];
} DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR;
````


## -struct-fields

### -field abKeySelectionVector

A 5-byte array that comprises the HDCP KSV. Byte 0 is the least significant byte and byte 4 is the most significant byte. 


## -remarks
For more information about the HDCP KSV, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=38728">HDCP Specification Revision 1.1</a>. 


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
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgkmdt_opm_connected_hdcp_device_information">DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


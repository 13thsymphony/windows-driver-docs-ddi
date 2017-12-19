---
UID: NE.dispmprt._DXGK_CHILD_STATUS_TYPE
title: _DXGK_CHILD_STATUS_TYPE
author: windows-driver-content
description: The DXGK_CHILD_STATUS_TYPE enumeration indicates the type of status being requested or reported for a child device of the display adapter.
old-location: display\dxgk_child_status_type.htm
old-project: display
ms.assetid: 5fa4b7e2-8215-49d8-9d70-b45c972b39b4
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGK_CHILD_STATUS_TYPE, *PDXGK_CHILD_STATUS_TYPE, PDXGK_CHILD_STATUS_TYPE, DXGK_CHILD_STATUS_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_CHILD_STATUS_TYPE
req.alt-loc: dispmprt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _DXGK_CHILD_STATUS_TYPE enumeration



## -description
The DXGK_CHILD_STATUS_TYPE enumeration indicates the type of status being requested or reported for a child device of the display adapter.



## -syntax

````
typedef enum _DXGK_CHILD_STATUS_TYPE { 
  StatusUninitialized,
  StatusConnection,
  StatusRotation,
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
  StatusMiracast

#endif } DXGK_CHILD_STATUS_TYPE, *PDXGK_CHILD_STATUS_TYPE;
````


## -enum-fields

### -field StatusUninitialized

Indicates that a variable of type DXGK_CHILD_STATUS_TYPE has not yet been assigned a meaningful value.


### -field StatusConnection

Indicates that the request or report pertains to whether the child device has a monitor (or other display device) connected to it.


### -field StatusRotation

Indicates that the request or report pertains to the rotation angle of the monitor (or other display device) that is connected to the child device.


### -field StatusMiracast

Indicates that the request or report pertains to a monitor (or other display device) that is connected wirelessly to the child device through a Miracast connected session.

Supported by WDDM 1.3 and later drivers running on Windows 8.1 and later.


## -remarks
The <b>Type</b> member of a <a href="display.dxgk_child_status">DXGK_CHILD_STATUS</a> structure is a member of the <b>DXGK_CHILD_STATUS_TYPE</b> enumeration.


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
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_status.md">DxgkDdiQueryChildStatus</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkcb_indicate_child_status.md">DxgkCbIndicateChildStatus</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_CHILD_STATUS_TYPE enumeration%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


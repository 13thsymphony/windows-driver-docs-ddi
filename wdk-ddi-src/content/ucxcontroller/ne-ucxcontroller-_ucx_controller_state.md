---
UID: NE.ucxcontroller._UCX_CONTROLLER_STATE
title: _UCX_CONTROLLER_STATE
author: windows-driver-content
description: This enumeration provides values to specify the UCX controller state after a reset.
old-location: buses\ucx_controller_state.htm
old-project: usbref
ms.assetid: 717BE2D2-2CF3-4A8C-B7DC-41E45C56B02B
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _UCX_CONTROLLER_STATE, UCX_CONTROLLER_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UCX_CONTROLLER_STATE
req.alt-loc: Ucxcontroller.h
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
req.product: Windows 10 or later.
---

# _UCX_CONTROLLER_STATE enumeration



## -description
This enumeration provides values to specify the UCX controller state after a  reset.


## -syntax

````
typedef enum _UCX_CONTROLLER_STATE { 
  UcxControllerStateLost,
  UcxControllerStatePreserved
} UCX_CONTROLLER_STATE;
````


## -enum-fields

### -field UcxControllerStateLost

Indicates the controller state was lost after reset.

### -field UcxControllerStatePreserved

Indicates the controller state was preserved after reset.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ucxcontroller.h (include Ucxclass.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses._ucx_controller_reset_complete_info">UCX_CONTROLLER_RESET_COMPLETE_INFO</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCX_CONTROLLER_STATE enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

---
UID : NE:poscx._POS_CX_EVENT_ATTRIBUTES
title : "_POS_CX_EVENT_ATTRIBUTES"
author : windows-driver-content
description : The POS_CX_EVENT_ATTRIBUTES describes the priority and access rights for the POS events coming from the device. The values are a combination of the values defined in POS_CX_EVENT_DEST and POS_CX_EVENT_PRIORITY.
old-location : pos\pos_cx_event_attributes.htm
old-project : pos
ms.assetid : 5B8B38B6-ACF3-44F9-BC83-71F0A2FC4DDD
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : poscx/POS_CX_EVENT_ATTR_CONTROL, poscx/POS_CX_EVENT_ATTR_DATA, poscx/POS_CX_EVENT_ATTR_BCAST_CONTROL, _POS_CX_EVENT_ATTRIBUTES, POS_CX_EVENT_ATTRIBUTES enumeration, POS_CX_EVENT_ATTR_CONTROL, POS_CX_EVENT_ATTRIBUTES, poscx/POS_CX_EVENT_ATTRIBUTES, POS_CX_EVENT_ATTR_BCAST_CONTROL, pos.pos_cx_event_attributes, POS_CX_EVENT_ATTR_DATA
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : poscx.h
req.include-header : Poscx.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : POS_CX_EVENT_ATTRIBUTES
req.product : Windows 10 or later.
---

# _POS_CX_EVENT_ATTRIBUTES Enumeration
The POS_CX_EVENT_ATTRIBUTES describes the priority and access rights for the POS events coming from the device. The values are a combination of the values defined in <a href="..\poscx\ne-poscx-_pos_cx_event_dest.md">POS_CX_EVENT_DEST</a> and <a href="..\poscx\ne-poscx-_pos_cx_event_priority.md">POS_CX_EVENT_PRIORITY</a>.

## Syntax
````
typedef enum _POS_CX_EVENT_ATTRIBUTES { 
  POS_CX_EVENT_ATTR_DATA           = ((POS_CX_EVENT_DEST_DEVICE_OWNER << 8) | POS_CX_EVENT_PRIORITY_DATA),
  POS_CX_EVENT_ATTR_CONTROL        = ((POS_CX_EVENT_DEST_DEVICE_OWNER << 8) | POS_CX_EVENT_PRIORITY_CONTROL),
  POS_CX_EVENT_ATTR_BCAST_CONTROL  = ((POS_CX_EVENT_DEST_ALL << 8) | POS_CX_EVENT_PRIORITY_CONTROL)
} POS_CX_EVENT_ATTRIBUTES;
````

## Constants

<table>

<tr>
<td>POS_CX_EVENT_ATTR_BCAST_CONTROL</td>
<td>Control level priority delivered in FIFO to ALL open handles on the driver.</td>
</tr>

<tr>
<td>POS_CX_EVENT_ATTR_CONTROL</td>
<td>Control level priority delivered in FIFO to the claim owner handle.</td>
</tr>

<tr>
<td>POS_CX_EVENT_ATTR_DATA</td>
<td>Data level priority delivered in FIFO to the claim owner handle.</td>
</tr>
</table>

## Remarks

<div class="alert"><b>Note</b>  PosCx will deliver all Control level events before Data level events.</div><div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | poscx.h (include Poscx.h) |

## See Also

<a href="..\poscx\ne-poscx-_pos_cx_event_dest.md">POS_CX_EVENT_DEST</a>

<a href="..\poscx\ne-poscx-_pos_cx_event_priority.md">POS_CX_EVENT_PRIORITY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [pos\pos]:%20POS_CX_EVENT_ATTRIBUTES enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID: NS:hbaapi.HBA_EventInfo
title: HBA_EventInfo
author: windows-driver-content
description: The HBA_EventInfo structure contains information about an event of the indicated type.
old-location: storage\hba_eventinfo.htm
old-project: storage
ms.assetid: fc6b73ac-f86c-4978-9d71-9bd8398c116b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PHBA_EVENTINFO, HBA_EventInfo structure [Storage Devices], *PHBA_EVENTINFO, structs-Fibre_6885fdc8-d2ce-40b3-ba2a-2e423f287780.xml, hbaapi/HBA_EventInfo, hbaapi/PHBA_EVENTINFO, PHBA_EVENTINFO structure pointer [Storage Devices], HBA_EventInfo, storage.hba_eventinfo, HBA_EVENTINFO, HBA_EVENTINFO structure [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbaapi.h
apiname:
-	HBA_EVENTINFO
product: Windows
targetos: Windows
req.typenames: HBA_EVENTINFO, *PHBA_EVENTINFO
---

# HBA_EventInfo structure
The HBA_EventInfo structure contains information about an event of the indicated type.

## Syntax
````
typedef struct HBA_EventInfo {
  HBA_UINT32 EventCode;
  union {
    HBA_LINK_EVENTINFO Link_EventInfo;
    HBA_RSCN_EVENTINFO RSCN_EventInfo;
    HBA_PTY_EVENTINFO  Pty_EventInfo;
  } Event;
} HBA_EVENTINFO, *PHBA_EVENTINFO;
````

## Members


`Event`



`EventCode`

Contains a code indicating the type of event. The following table lists the values that this member can have:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
HBA_EVENT_LIP_OCCURRED

</td>
<td>
A loop initialization primitive event occurred.

</td>
</tr>
<tr>
<td>
HBA_EVENT_LINK_UP

</td>
<td>
A link up event occurred. 

</td>
</tr>
<tr>
<td>
HBA_EVENT_LINK_DOWN

</td>
<td>
A link down event occurred. 

</td>
</tr>
<tr>
<td>
HBA_EVENT_LIP_RESET_OCCURRED

</td>
<td>
A loop initialization primitive resest event occurred.

</td>
</tr>
<tr>
<td>
HBA_EVENT_RSCN

</td>
<td>
An RSCN event occurred.

</td>
</tr>
<tr>
<td>
HBA_EVENT_PROPRIETARY

</td>
<td>
A proprietary event occurred. 

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbaapi.h (include Hbaapi.h) |

## See Also

<a href="..\hbaapi\ns-hbaapi-hba_pty_eventinfo.md">HBA_Pty_EventInfo</a>



<a href="..\hbaapi\ns-hbaapi-hba_rscn_eventinfo.md">HBA_RSCN_EventInfo</a>



<a href="..\hbaapi\ns-hbaapi-hba_link_eventinfo.md">HBA_Link_EventInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_EventInfo structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
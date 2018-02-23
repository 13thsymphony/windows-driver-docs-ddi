---
UID: NE:ntddrilapitypes.RILNOTIFICATIONFILTERMASK
title: RILNOTIFICATIONFILTERMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnotificationfiltermask.htm
old-project: netvista
ms.assetid: 5dc72657-00ae-4fde-b9a7-a63616d934c0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddrilapitypes/RILNOTIFICATIONFILTERMASK, ntddrilapitypes/RIL_NFS_REGSTATUS_RATKIND, RILNOTIFICATIONFILTERMASK, RIL_NFS_REGSTATUS_RATKIND, RILNOTIFICATIONFILTERMASK enumeration [Network Drivers Starting with Windows Vista], RIL_NFS_LOCATIONUPDATE, RIL_NFS_ALL, RIL_NFS_SIGNALQUALITY, ntddrilapitypes/RIL_NFS_LOCATIONUPDATE, netvista.rilnotificationfiltermask, ntddrilapitypes/RIL_NFS_SIGNALQUALITY, ntddrilapitypes/RIL_NFS_ALL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
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
-	ntddrilapitypes.h
apiname:
-	RILNOTIFICATIONFILTERMASK
product: Windows
targetos: Windows
req.typenames: RILNOTIFICATIONFILTERMASK
---

# RILNOTIFICATIONFILTERMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILNOTIFICATIONFILTERMASK { 
  RIL_NFS_SIGNALQUALITY,
  RIL_NFS_REGSTATUS_RATKIND,
  RIL_NFS_LOCATIONUPDATE,
  RIL_NFS_ALL
} RILNOTIFICATIONFILTERMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_NFS_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_NFS_LOCATIONUPDATE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_NFS_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_NFS_REGSTATUS_RATKIND</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_NFS_SIGNALQUALITY</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |
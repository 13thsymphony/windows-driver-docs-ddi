---
UID: NE:rilapitypes.RILMESSAGEFLAGS
title: RILMESSAGEFLAGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessageflags_2.htm
old-project: netvista
ms.assetid: 49f8bd1b-5c8a-47d3-a5d5-817216562559
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_MSGFLAG_HEADER, rilapitypes/RILMESSAGEFLAGS, RIL_MSGFLAG_MORETOSEND, RILMESSAGEFLAGS enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_MSGFLAG_REJECTDUPS, rilapitypes/RIL_MSGFLAG_STATUSREPORTRETURNED, RIL_MSGFLAG_ALL, RILMESSAGEFLAGS, rilapitypes/RIL_MSGFLAG_CAUSEDBYCOMMAND, RIL_MSGFLAG_STATUSREPORTRETURNED, RIL_MSGFLAG_STATUSREPORTREQUESTED, RIL_MSGFLAG_CAUSEDBYCOMMAND, RIL_MSGFLAG_REPLYPATH, rilapitypes/RIL_MSGFLAG_HEADER, netvista.rilmessageflags_2, rilapitypes/RIL_MSGFLAG_REPLYPATH, rilapitypes/RIL_MSGFLAG_STATUSREPORTREQUESTED, rilapitypes/RIL_MSGFLAG_MORETOSEND, RIL_MSGFLAG_REJECTDUPS, rilapitypes/RIL_MSGFLAG_ALL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILMESSAGEFLAGS
product: Windows
targetos: Windows
req.typenames: RILMESSAGEFLAGS
req.product: Windows 10 or later.
---

# RILMESSAGEFLAGS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMESSAGEFLAGS { 
  RIL_MSGFLAG_MORETOSEND,
  RIL_MSGFLAG_REPLYPATH,
  RIL_MSGFLAG_HEADER,
  RIL_MSGFLAG_REJECTDUPS,
  RIL_MSGFLAG_STATUSREPORTRETURNED,
  RIL_MSGFLAG_STATUSREPORTREQUESTED,
  RIL_MSGFLAG_CAUSEDBYCOMMAND,
  RIL_MSGFLAG_ALL
} RILMESSAGEFLAGS;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_MSGFLAG_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGFLAG_CAUSEDBYCOMMAND</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGFLAG_HEADER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGFLAG_MORETOSEND</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGFLAG_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGFLAG_REJECTDUPS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGFLAG_REPLYPATH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGFLAG_STATUSREPORTREQUESTED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGFLAG_STATUSREPORTRETURNED</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |
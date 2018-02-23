---
UID: NE:prcomoem.tagOEMPTOPTS
title: tagOEMPTOPTS
author: windows-driver-content
description: "."
old-location: print\oemptopts.htm
old-project: print
ms.assetid: A63C115D-7215-422A-B4F9-C88820FC8168
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: OEMPTOPTS, tagOEMPTOPTS, *POEMPTOPTS, POEMPTOPTS enumeration pointer [Print Devices], OEMPT_NOSHAPSHOT, POEMPTOPTS, print.oemptopts, OEMPT_DEFAULT, OEMPTOPTS enumeration [Print Devices], prcomoem/POEMPTOPTS, prcomoem/OEMPT_DEFAULT, prcomoem/OEMPTOPTS, prcomoem/OEMPT_NOSHAPSHOT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: prcomoem.h
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
-	Prcomoem.h
apiname:
-	OEMPTOPTS
product: Windows
targetos: Windows
req.typenames: "*POEMPTOPTS, OEMPTOPTS"
req.product: Windows 10 or later.
---

# tagOEMPTOPTS Enumeration


## Syntax
````
typedef enum tagOEMPTOPTS { 
  OEMPT_DEFAULT     = 0,
  OEMPT_NOSHAPSHOT  = 0x1
} OEMPTOPTS, *POEMPTOPTS;
````

## Constants

<table>
            
                <tr>
                    <td>OEMPT_DEFAULT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>OEMPT_NOSNAPSHOT</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | prcomoem.h |
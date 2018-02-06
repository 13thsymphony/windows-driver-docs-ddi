---
UID: NE:rilapitypes.RILCALLBARRINGSTATUSPARAMSTYPE
title: RILCALLBARRINGSTATUSPARAMSTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallbarringstatusparamstype_2.htm
old-project: netvista
ms.assetid: ed54bc8d-0cf2-4d6a-935c-b5b2a539eea0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_BARRTYPE_ALLINCOMINGBARRING, rilapitypes/RIL_BARRTYPE_INCOMINGNOTINUICC, RILCALLBARRINGSTATUSPARAMSTYPE, netvista.rilcallbarringstatusparamstype_2, RIL_BARRTYPE_OUTGOINGINT, rilapitypes/RIL_BARRTYPE_ALLBARRING, RILCALLBARRINGSTATUSPARAMSTYPE enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_BARRTYPE_ALL, rilapitypes/RIL_BARRTYPE_INCOMINGROAMING, RIL_BARRTYPE_ALLINCOMINGBARRING, RIL_BARRTYPE_ALLOUTGOINGBARRING, RIL_BARRTYPE_OUTGOINGINTEXTOHOME, RIL_BARRTYPE_ALLINCOMING, RIL_BARRTYPE_INCOMINGNOTINUICC, rilapitypes/RIL_BARRTYPE_ALLINCOMING, RIL_BARRTYPE_INCOMINGROAMING, rilapitypes/RIL_BARRTYPE_ALLOUTGOINGBARRING, rilapitypes/RIL_BARRTYPE_OUTGOINGINT, rilapitypes/RILCALLBARRINGSTATUSPARAMSTYPE, rilapitypes/RIL_BARRTYPE_OUTGOINGINTEXTOHOME, RIL_BARRTYPE_ALL, RIL_BARRTYPE_ALLBARRING
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
-	RILCALLBARRINGSTATUSPARAMSTYPE
product: Windows
targetos: Windows
req.typenames: RILCALLBARRINGSTATUSPARAMSTYPE
req.product: Windows 10 or later.
---

# RILCALLBARRINGSTATUSPARAMSTYPE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLBARRINGSTATUSPARAMSTYPE { 
  RIL_BARRTYPE_OUTGOINGINT,
  RIL_BARRTYPE_OUTGOINGINTEXTOHOME,
  RIL_BARRTYPE_ALLINCOMING,
  RIL_BARRTYPE_INCOMINGROAMING,
  RIL_BARRTYPE_INCOMINGNOTINUICC,
  RIL_BARRTYPE_ALLBARRING,
  RIL_BARRTYPE_ALLOUTGOINGBARRING,
  RIL_BARRTYPE_ALLINCOMINGBARRING,
  RIL_BARRTYPE_ALL
} RILCALLBARRINGSTATUSPARAMSTYPE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_BARRTYPE_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_BARRTYPE_ALLBARRING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_BARRTYPE_ALLINCOMING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_BARRTYPE_ALLINCOMINGBARRING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_BARRTYPE_ALLOUTGOING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_BARRTYPE_ALLOUTGOINGBARRING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_BARRTYPE_INCOMINGNOTINUICC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_BARRTYPE_INCOMINGROAMING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_BARRTYPE_OUTGOINGINT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_BARRTYPE_OUTGOINGINTEXTOHOME</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |
---
UID: NS:winsplp._MONITORINIT
title: "_MONITORINIT"
author: windows-driver-content
description: The MONITORINIT structure is used as an input parameter to a print monitor's InitializePrintMonitor2 function.
old-location: print\monitorinit.htm
old-project: print
ms.assetid: 3445997f-a607-4071-b05e-c1a8d01892b2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMONITORINIT, MONITORINIT, MONITORINIT structure [Print Devices], PMONITORINIT, PMONITORINIT structure pointer [Print Devices], _MONITORINIT, print.monitorinit, spoolfnc_321f67a1-b279-4909-af99-d3e564bf3555.xml, winsplp/MONITORINIT, winsplp/PMONITORINIT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: Winsplp.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winsplp.h
api_name:
-	MONITORINIT
product: Windows
targetos: Windows
req.typenames: MONITORINIT, *PMONITORINIT
req.product: Windows 10 or later.
---

# _MONITORINIT structure
The MONITORINIT structure is used as an input parameter to a print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff551605">InitializePrintMonitor2</a> function.

## Syntax
```
typedef struct _MONITORINIT {
  DWORD       cbSize;
  HANDLE      hSpooler;
  HKEYMONITOR hckRegistryRoot;
  PMONITORREG pMonitorReg;
  BOOL        bLocal;
  LPCWSTR     pszServerName;
} *PMONITORINIT, MONITORINIT;
```

## Members


`cbSize`

Size, in bytes, of the MONITORINIT structure.

`hSpooler`

Spooler handle, for use as input to functions identified by the MONITORREG structure.

`hckRegistryRoot`

Registry handle, for use as input to functions identified by the MONITORREG structure.

`pMonitorReg`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557537">MONITORREG</a> structure.

`bLocal`

<b>TRUE</b> if the monitor is being called by a local node spooler. <b>FALSE</b> if the monitor is being called by a cluster spooler. (Monitors can usually ignore this member.)

`pszServerName`

Caller-supplied pointer to a string representing a server name.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | winsplp.h (include Winsplp.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551605">InitializePrintMonitor2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557537">MONITORREG</a>
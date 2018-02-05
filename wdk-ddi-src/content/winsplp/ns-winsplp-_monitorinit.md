---
UID : NS:winsplp._MONITORINIT
title : "_MONITORINIT"
author : windows-driver-content
description : The MONITORINIT structure is used as an input parameter to a print monitor's InitializePrintMonitor2 function.
old-location : print\monitorinit.htm
old-project : print
ms.assetid : 3445997f-a607-4071-b05e-c1a8d01892b2
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : PMONITORINIT, MONITORINIT, winsplp/PMONITORINIT, *PMONITORINIT, print.monitorinit, MONITORINIT structure [Print Devices], spoolfnc_321f67a1-b279-4909-af99-d3e564bf3555.xml, _MONITORINIT, PMONITORINIT structure pointer [Print Devices], winsplp/MONITORINIT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : winsplp.h
req.include-header : Winsplp.h
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
req.typenames : MONITORINIT, *PMONITORINIT
req.product : Windows 10 or later.
---

# _MONITORINIT structure
The MONITORINIT structure is used as an input parameter to a print monitor's <a href="..\winsplp\nf-winsplp-initializeprintmonitor2.md">InitializePrintMonitor2</a> function.

## Syntax
````
typedef struct _MONITORINIT {
  DWORD       cbSize;
  HANDLE      hSpooler;
  HKEYMONITOR hckRegistryRoot;
  PMONITORREG pMonitorReg;
  BOOL        bLocal;
  LPCWSTR     pszServerName;
} MONITORINIT, *PMONITORINIT;
````

## Members


`bLocal`

<b>TRUE</b> if the monitor is being called by a local node spooler. <b>FALSE</b> if the monitor is being called by a cluster spooler. (Monitors can usually ignore this member.)

`cbSize`

Size, in bytes, of the MONITORINIT structure.

`hckRegistryRoot`

Registry handle, for use as input to functions identified by the MONITORREG structure.

`hSpooler`

Spooler handle, for use as input to functions identified by the MONITORREG structure.

`pMonitorReg`

Pointer to a <a href="..\winsplp\ns-winsplp-_monitorreg.md">MONITORREG</a> structure.

`pszServerName`

Caller-supplied pointer to a string representing a server name.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | winsplp.h (include Winsplp.h) |

## See Also

<a href="..\winsplp\nf-winsplp-initializeprintmonitor2.md">InitializePrintMonitor2</a>

<a href="..\winsplp\ns-winsplp-_monitorreg.md">MONITORREG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20MONITORINIT structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
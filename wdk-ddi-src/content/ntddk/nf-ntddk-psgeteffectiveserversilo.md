---
UID: NF:ntddk.PsGetEffectiveServerSilo
title: PsGetEffectiveServerSilo function
author: windows-driver-content
description: This routine traverses the parent chain of the Silo until finding the effective server silo or host silo.
old-location: kernel\psgeteffectiveserversilo.htm
old-project: kernel
ms.assetid: 60FCFF5B-4040-423F-A9B6-2DFE7DDD9DD0
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: PsGetEffectiveServerSilo, PsGetEffectiveServerSilo routine [Kernel-Mode Driver Architecture], kernel.psgeteffectiveserversilo, ntddk/PsGetEffectiveServerSilo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
-	ntddk.h
api_name:
-	PsGetEffectiveServerSilo
product:
- Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PsGetEffectiveServerSilo function
This routine traverses the parent chain of the <i>Silo</i> until finding the effective server silo or host silo.

## Syntax

```
NTKERNELAPI PESILO PsGetEffectiveServerSilo(
  PESILO Silo
);
```

## Parameters

`Silo`

A pointer to a silo.


## Return Value

The effective server silo. If a server silo is not found, the host silo is returned. In that case, <code>PsIsHostSilo(ReturnValue)</code> would return <b>TRUE</b>.

## Remarks

This routine does not fail because it always returns a silo: the server silo or the host silo.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | ntddk.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt735076">PsIsHostSilo</a>
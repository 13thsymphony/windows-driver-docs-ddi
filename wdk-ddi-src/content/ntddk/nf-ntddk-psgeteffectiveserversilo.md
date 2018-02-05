---
UID : NF:ntddk.PsGetEffectiveServerSilo
title : PsGetEffectiveServerSilo function
author : windows-driver-content
description : This routine traverses the parent chain of the Silo until finding the effective server silo or host silo.
old-location : kernel\psgeteffectiveserversilo.htm
old-project : kernel
ms.assetid : 60FCFF5B-4040-423F-A9B6-2DFE7DDD9DD0
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : PsGetEffectiveServerSilo routine [Kernel-Mode Driver Architecture], ntddk/PsGetEffectiveServerSilo, PsGetEffectiveServerSilo, kernel.psgeteffectiveserversilo
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1607
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PsGetEffectiveServerSilo function
This routine traverses the parent chain of the <i>Silo</i> until finding the effective server silo or host silo.

## Syntax

````
PESILO PsGetEffectiveServerSilo(
  _In_ PESILO Silo
);
````

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
| **Windows version** | Windows 10, version 1607 Windows 10, version 1607 |
| **Target Platform** | Windows |
| **Header** | ntddk.h |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\ntddk\nf-ntddk-psishostsilo.md">PsIsHostSilo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsGetEffectiveServerSilo routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
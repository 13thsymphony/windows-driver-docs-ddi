---
UID : NE:rilapitypes.RILCALLINFODIRECTION
title : RILCALLINFODIRECTION
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilcallinfodirection_2.htm
old-project : netvista
ms.assetid : 55db88f4-14a5-4d37-b4e8-be88369f33b7
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : rilapitypes/RIL_CALLDIR_MAX, RILCALLINFODIRECTION, rilapitypes/RILCALLINFODIRECTION, RIL_CALLDIR_OUTGOING, RILCALLINFODIRECTION enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_CALLDIR_OUTGOING, RIL_CALLDIR_MAX, netvista.rilcallinfodirection_2
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : rilapitypes.h
req.include-header : 
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : RILCALLINFODIRECTION
req.product : Windows 10 or later.
---

# RILCALLINFODIRECTION Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLINFODIRECTION { 
  RIL_CALLDIR_OUTGOING,
  RIL_CALLDIR_MAX
} RILCALLINFODIRECTION;
````

## Constants

<table>

<tr>
<td>RIL_CALLDIR_INCOMING</td>
<td></td>
</tr>

<tr>
<td>RIL_CALLDIR_MAX</td>
<td></td>
</tr>

<tr>
<td>RIL_CALLDIR_OUTGOING</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |
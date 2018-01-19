---
UID : NN:portcls.IPinName
title : IPinName
author : windows-driver-content
description : In Windows 7 and later operating systems, the IPinName interface is used by miniport drivers to report and update the names of audio endpoints.
old-location : audio\ipinname.htm
old-project : audio
ms.assetid : 3ed209f5-d4ea-44e5-a16c-59fa39053465
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : PcUnregisterIoTimeout
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : interface
req.header : portcls.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IPinName
req.alt-loc : portcls.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Portcls.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPinName interface

In Windows 7 and later operating systems, the <code>IPinName</code> interface is used by miniport drivers to report and update the names of audio endpoints.

## Methods

<p>The <b>IPinName</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [portcls.IPinName.GetPinName](nf-portcls-ipinname-getpinname.md) | The GetPinName method retrieves the friendly name of an audio endpoint. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum UMDF version** |  |
| **Header** | portcls.h |
| **DLL** |  |
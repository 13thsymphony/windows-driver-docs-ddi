---
UID: NF:portcls.PcRegisterAdapterPowerManagement
title: PcRegisterAdapterPowerManagement function
author: windows-driver-content
description: The PcRegisterAdapterPowerManagement function registers the adapter's power-management interface with the PortCls system driver.
old-location: audio\pcregisteradapterpowermanagement.htm
old-project: audio
ms.assetid: a9e2537d-4d67-4495-b391-55f885b7041a
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: PcRegisterAdapterPowerManagement, PcRegisterAdapterPowerManagement function [Audio Devices], audio.pcregisteradapterpowermanagement, audpc-routines_524bed01-a6ba-492c-9e18-7495de15be46.xml, portcls/PcRegisterAdapterPowerManagement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available starting in Windows 2000.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcRegisterAdapterPowerManagement
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# PcRegisterAdapterPowerManagement function
The <b>PcRegisterAdapterPowerManagement</b> function registers the adapter's power-management interface with the PortCls system driver.

## Syntax

```
PORTCLASSAPI NTSTATUS PcRegisterAdapterPowerManagement(
  PUNKNOWN Unknown,
  PVOID    pvContext1
);
```

## Parameters

`Unknown`

TBD

`pvContext1`

Pointer to the adapter's <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">functional device object (FDO)</a>. This parameter is a pointer to a system structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> but is cast to type PVOID.


## Return Value

<b>PcRegisterAdapterPowerManagement</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting in Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | Portcls.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536485">IAdapterPowerManagement</a>
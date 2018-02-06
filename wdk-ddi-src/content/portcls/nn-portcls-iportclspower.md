---
UID: NN:portcls.IPortClsPower
title: IPortClsPower
author: windows-driver-content
description: The IPortClsPower interface is supported in Windows Vista and later versions of Windows. IPortClsPower is the power management interface that the port class driver (PortCls) exposes to the adapter.
old-location: audio\iportclspower.htm
old-project: audio
ms.assetid: bebd704b-2824-4bea-aae8-d77c66830715
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.iportclspower, IPortClsPower interface [Audio Devices], IPortClsPower interface [Audio Devices], described, IPortClsPower, portcls/IPortClsPower, audmp-routines_d6815c8f-a34f-423a-a58d-e45a1292d22d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IPortClsPower
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IPortClsPower interface

The <code>IPortClsPower</code> interface is supported in Windows Vista and later versions of Windows. <code>IPortClsPower</code> is the power management interface that the port class driver (PortCls) exposes to the adapter.

## Methods

<p>The <b>IPortClsPower</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [portcls.IPortClsPower.RegisterAdapterPowerManagement](nf-portcls-iportclspower-registeradapterpowermanagement.md) | The RegisterAdapterPowerManagement method registers the power management interface of the adapter with PortCls. |
| [portcls.IPortClsPower.SetIdlePowerManagement](nf-portcls-iportclspower-setidlepowermanagement.md) | The SetIdlePowerManagement method provides a way for the adapter driver to opt in or opt out of idle state detection. |
| [portcls.IPortClsPower.UnregisterAdapterPowerManagement](nf-portcls-iportclspower-unregisteradapterpowermanagement.md) | The UnregisterAdapterPowerManagement method unregisters the adapter's power management interface with PortCls. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | portcls.h |
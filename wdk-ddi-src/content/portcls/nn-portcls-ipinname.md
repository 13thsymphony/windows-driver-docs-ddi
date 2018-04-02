---
UID: NN:portcls.IPinName
title: IPinName
author: windows-driver-content
description: In Windows 7 and later operating systems, the IPinName interface is used by miniport drivers to report and update the names of audio endpoints.
old-location: audio\ipinname.htm
old-project: audio
ms.assetid: 3ed209f5-d4ea-44e5-a16c-59fa39053465
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IPinName, IPinName interface [Audio Devices], IPinName interface [Audio Devices], described, audio.ipinname, audmp-routines_27ed00c6-3e56-400f-9bed-2c2c84091e74.xml, portcls/IPinName
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPinName
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPinName interface

In Windows 7 and later operating systems, the <code>IPinName</code> interface is used by miniport drivers to report and update the names of audio endpoints.

## Methods

<p>The <b>IPinName</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [IPinName::GetPinName](nf-portcls-ipinname-getpinname.md) | The GetPinName method retrieves the friendly name of an audio endpoint. |


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | portcls.h |
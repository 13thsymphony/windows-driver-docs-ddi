---
UID: NC:hdaudio.PGET_RESOURCE_INFORMATION
title: PGET_RESOURCE_INFORMATION
author: windows-driver-content
description: The GetResourceInformation routine retrieves information about hardware resources.The function pointer type for a GetResourceInformation routine is defined as follows.
old-location: audio\getresourceinformation.htm
old-project: audio
ms.assetid: ba1f0fa2-77dd-4ec3-86c8-c5d74465743f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetResourceInformation, GetResourceInformation callback function [Audio Devices], PGET_RESOURCE_INFORMATION, aud-prop2_03b48e3f-0650-45eb-b1d2-0db5e2e98636.xml, audio.getresourceinformation, hdaudio/GetResourceInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	hdaudio.h
api_name:
-	GetResourceInformation
product: Windows
targetos: Windows
req.typenames: SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---


# PGET_RESOURCE_INFORMATION callback function
The <code>GetResourceInformation</code> routine retrieves information about hardware resources.

The function pointer type for a <code>GetResourceInformation</code> routine is defined as follows.

## Syntax

```
PGET_RESOURCE_INFORMATION PgetResourceInformation;

void PgetResourceInformation(
  PVOID _context,
  PUCHAR CodecAddress,
  PUCHAR FunctionGroupStartNode
)
{...}
```

## Parameters

`_context`

Specifies the context value from the <b>Context</b> member of the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a><u>, </u><a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>, or <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a> structure.

`CodecAddress`



`FunctionGroupStartNode`




## Return Value

None

## Remarks

A codec contains one or more function groups. Each function group contains some number of nodes that are numbered sequentially beginning with the starting node. For example, if a function group contains three nodes and the starting node has a node ID of 9, the other two nodes in the function group have node IDs 10 and 11. For more information, see the Intel High Definition Audio Specification at the <a href="http://go.microsoft.com/fwlink/p/?linkid=42508">Intel HD Audio</a> website.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | hdaudio.h (include Hdaudio.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a>



<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PGET_RESOURCE_INFORMATION callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
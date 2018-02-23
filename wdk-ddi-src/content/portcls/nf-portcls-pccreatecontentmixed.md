---
UID: NF:portcls.PcCreateContentMixed
title: PcCreateContentMixed function
author: windows-driver-content
description: The PcCreateContentMixed function computes the DRM content rights for a composite stream containing mixed content from some number of KS audio streams.
old-location: audio\pccreatecontentmixed.htm
old-project: audio
ms.assetid: 9b916d43-26ab-4354-8537-2d4789c5fb52
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: PcCreateContentMixed function [Audio Devices], portcls/PcCreateContentMixed, PcCreateContentMixed, audpc-routines_40c3dd23-60cb-48dc-a570-1ba007a27bb2.xml, audio.pccreatecontentmixed
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcCreateContentMixed function in Microsoft Windows XP and later operating systems.
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Portcls.lib
-	Portcls.dll
apiname:
-	PcCreateContentMixed
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# PcCreateContentMixed function
The <b>PcCreateContentMixed</b> function computes the DRM content rights for a composite stream containing mixed content from some number of KS audio streams. Note that this function call is identical in operation to the <a href="..\drmk\nf-drmk-drmcreatecontentmixed.md">DrmCreateContentMixed</a> function, and its parameter definitions and return value are also identical.

## Syntax

````
PORTCLASSAPI NTSTATUS NTAPI  PcCreateContentMixed(void);
````

## Parameters

`paContentId`

TBD

`cContentId`

TBD

`pMixedContentId`

TBD


## Return Value

See return value definition in <a href="..\drmk\nf-drmk-drmcreatecontentmixed.md">DrmCreateContentMixed</a>.

## Remarks

For more information, see the comments in <a href="..\drmk\nf-drmk-drmcreatecontentmixed.md">DrmCreateContentMixed</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The PortCls system driver implements the PcCreateContentMixed function in Microsoft Windows XP and later operating systems.  |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | Portcls.lib |

## See Also

<a href="..\drmk\nf-drmk-drmcreatecontentmixed.md">DrmCreateContentMixed</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcCreateContentMixed function%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
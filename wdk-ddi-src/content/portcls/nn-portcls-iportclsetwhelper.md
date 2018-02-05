---
UID : NN:portcls.IPortClsEtwHelper
title : IPortClsEtwHelper
author : windows-driver-content
description : The IPortClsEtwHelper interface allows an audio miniport driver to access the Event Tracing for Windows (ETW) helper functions.
old-location : audio\iportclsetwhelper.htm
old-project : audio
ms.assetid : 7BF9E3AB-D508-4FB8-8C47-C0B338933A56
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : audio.iportclsetwhelper, IPortClsEtwHelper interface [Audio Devices], IPortClsEtwHelper interface [Audio Devices], described, IPortClsEtwHelper, portcls/IPortClsEtwHelper
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : interface
req.header : portcls.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IPortClsEtwHelper interface

The <code>IPortClsEtwHelper</code> interface allows an audio miniport driver to access the Event Tracing for Windows (ETW) helper functions.

The miniport driver uses the information from the helper functions to report glitching errors.

## Methods

<p>The <b>IPortClsEtwHelper</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [portcls.IPortClsEtwHelper.MiniportWriteEtwEvent](nf-portcls-iportclsetwhelper-miniportwriteetwevent.md) | The MiniportWriteEtwEvent method is used by an audio miniport driver for providing the information about an Event Tracing for Windows (ETW) event. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Windows |
| **Header** | portcls.h |

## See Also

<a href="https://msdn.microsoft.com/9FF2A5D6-9382-4EE6-AA21-DCF47210F73B">Glitch Reporting for Offloaded Audio</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsEtwHelper interface%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID : NF:upssvc.UPSCancelWait
title : UPSCancelWait function
author : windows-driver-content
description : The UPSCancelWait function cancels all waits initiated by calls to UPSWaitForStateChange.
old-location : battery\upscancelwait.htm
old-project : battery
ms.assetid : 8ac611fc-5634-4857-8533-6e170fe884b2
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : UPSCancelWait, upssvc/UPSCancelWait, UPS_fns_79aba7aa-4204-4532-873a-8566ed6168f8.xml, UPSCancelWait function [Battery Devices], battery.upscancelwait
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : upssvc.h
req.include-header : Upssvc.h
req.target-type : Desktop
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
req.typenames : UMDETW_ALLOCATION_USAGE
req.product : Windows 10 or later.
---


# UPSCancelWait function
The <b>UPSCancelWait</b> function cancels all waits initiated by calls to <a href="..\upssvc\nf-upssvc-upswaitforstatechange.md">UPSWaitForStateChange</a>.

## Syntax

````
void UPSCancelWait(
   void 
);
````

## Parameters

This function has no parameters.

## Return Value

None

## Remarks

The call returns immediately.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | upssvc.h (include Upssvc.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\upssvc\nf-upssvc-upswaitforstatechange.md">UPSWaitForStateChange</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [battery\battery]:%20UPSCancelWait function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
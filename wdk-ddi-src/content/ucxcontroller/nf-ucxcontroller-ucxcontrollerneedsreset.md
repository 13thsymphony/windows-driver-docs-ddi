---
UID : NF:ucxcontroller.UcxControllerNeedsReset
title : UcxControllerNeedsReset function
author : windows-driver-content
description : Initiates a non-Plug and Play (PnP) controller reset operation by queuing an event into the controller reset state machine.
old-location : buses\_ucxcontrollerneedsreset.htm
old-project : usbref
ms.assetid : FAE099E4-6BE9-4637-934F-9F86FFDCAA6A
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : UcxControllerNeedsReset, ucxcontroller/UcxControllerNeedsReset, UcxControllerNeedsReset method [Buses], buses._ucxcontrollerneedsreset
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ucxcontroller.h
req.include-header : Ucxclass.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : <=DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : UCX_CONTROLLER_STATE
req.product : Windows 10 or later.
---


# UcxControllerNeedsReset function
Initiates a non-Plug and Play (PnP) controller reset operation by queuing an event 
        into the controller reset state machine.

## Syntax

````
BOOL UcxControllerNeedsReset(
  [in] UCXCONTROLLER Controller
);
````

## Parameters

`Controller`

A handle to the controller object to reset. The client driver retrieved the handle in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>.


## Return Value

If the operation is successful, the method returns TRUE. Otherwise it returns FALSE.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ucxcontroller.h (include Ucxclass.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcxControllerNeedsReset method%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
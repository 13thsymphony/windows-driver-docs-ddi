---
UID: NC:ucxcontroller.EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER
title: EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER function
author: windows-driver-content
description: The client driver's implementation that UCX calls to retrieve the current 32-bit frame number.
old-location: buses\evt_ucx_controller_get_current_framenumber.htm
old-project: usbref
ms.assetid: 2755d0fd-9801-4d54-89cb-54f8b984288c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: PEVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER
req.alt-loc: Ucxcontroller.h
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
req.typenames: *PUCM_PD_REQUEST_DATA_OBJECT, UCM_PD_REQUEST_DATA_OBJECT
req.product: Windows 10 or later.
---

# EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER function



## -description
The client driver's implementation that UCX calls to retrieve the current 32-bit frame number.



## -syntax

````
EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER EvtUcxControllerGetCurrentFrameNumber;

NTSTATUS EvtUcxControllerGetCurrentFrameNumber(
  _In_  UCXCONTROLLER UcxController,
  _Out_ PULONG        FrameNumber
)
{ ... }

typedef EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER PEVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER;
````


## -parameters

### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


### -param FrameNumber [out]

A pointer to the current 32-bit frame number.


## -returns
If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.


## -remarks
The UCX client driver registers its <i>EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER</i> implementation with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_CONTROLLER_GET_CURRENT_FRAMENUMBER callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


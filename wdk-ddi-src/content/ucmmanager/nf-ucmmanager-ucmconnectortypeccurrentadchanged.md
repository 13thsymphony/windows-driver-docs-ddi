---
UID: NF:ucmmanager.UcmConnectorTypeCCurrentAdChanged
title: UcmConnectorTypeCCurrentAdChanged function
author: windows-driver-content
description: Notifies the USB connector manager framework extension (UcmCx) when the specified connector changes the current advertisement. Either the connector changes it (when it is DFP/Source), or the partner changed it (when it is UFP/Sink).
old-location: buses\ucmconnectortypeccurrentadchanged.htm
old-project: usbref
ms.assetid: 26C4D840-2287-4DC2-B039-FD8D2FB92288
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UcmConnectorTypeCCurrentAdChanged, UcmConnectorTypeCCurrentAdChanged method [Buses], buses.ucmconnectortypeccurrentadchanged, ucmmanager/UcmConnectorTypeCCurrentAdChanged
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmmanager.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: UcmCxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	UcmCxstub.lib
-	UcmCxstub.dll
api_name:
-	UcmConnectorTypeCCurrentAdChanged
product:
- Windows
targetos: Windows
req.typenames: PORT_DATA_1, *PPORT_DATA_1
req.product: Windows 10 or later.
---


# UcmConnectorTypeCCurrentAdChanged function
Notifies the USB connector manager framework extension (UcmCx) when the specified connector changes the current advertisement. Either the connector changes it (when it is DFP/Source), or the partner changed it (when it is UFP/Sink).

## Syntax

```
NTSTATUS UcmConnectorTypeCCurrentAdChanged(
  UCMCONNECTOR      Connector,
  UCM_TYPEC_CURRENT CurrentAdvertisement
);
```

## Parameters

`Connector`

Handle to the connector object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt187909">UcmConnectorCreate</a>.

`CurrentAdvertisement`

The new current advertisement of the connector indicated by one of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187945">UCM_TYPEC_CURRENT</a>-typed flags.


## Return Value

<b>UcmConnectorTypeCCurrentAdChanged</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> value.

## Remarks

When using a Type-C connector for charging, the partner connector sends a current advertisement when it's attached to the local connector. That initial advertisement is report to UcmCx  by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt187915">UcmConnectorTypeCAttach</a>.  During the lifetime of the connection, the current level advertised by the source might change. The client driver must notify UcmCx about  that change by calling method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** | 2.15 |
| **Header** | ucmmanager.h (include Ucmcx.h) |
| **Library** | UcmCxstub.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt187909">UcmConnectorCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187915">UcmConnectorTypeCAttach</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187916">UcmConnectorTypeCCurrentAdChanged</a>
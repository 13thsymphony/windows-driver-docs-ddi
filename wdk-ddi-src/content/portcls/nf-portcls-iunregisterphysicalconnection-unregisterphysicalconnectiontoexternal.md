---
UID: NF:portcls.IUnregisterPhysicalConnection.UnregisterPhysicalConnectionToExternal
title: IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal method
author: windows-driver-content
description: The UnregisterPhysicalConnectionToExternal method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnectionToExternal.
old-location: audio\iunregisterphysicalconnection_unregisterphysicalconnectiontoexternal.htm
old-project: audio
ms.assetid: 250bf99c-d5fa-459b-bd94-d438368379f1
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IUnregisterPhysicalConnection, IUnregisterPhysicalConnection interface [Audio Devices], UnregisterPhysicalConnectionToExternal method, IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal, UnregisterPhysicalConnectionToExternal method [Audio Devices], UnregisterPhysicalConnectionToExternal method [Audio Devices], IUnregisterPhysicalConnection interface, UnregisterPhysicalConnectionToExternal,IUnregisterPhysicalConnection.UnregisterPhysicalConnectionToExternal, audio.iunregisterphysicalconnection_unregisterphysicalconnectiontoexternal, audmp-routines_9c455ca4-88c6-46a3-9ec6-a5f176802947.xml, portcls/IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
-	COM
api_location:
-	portcls.h
api_name:
-	IUnregisterPhysicalConnection.UnregisterPhysicalConnectionToExternal
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal method
The <code>UnregisterPhysicalConnectionToExternal</code> method deletes the registration of a physical connection that was registered by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff537729">PcRegisterPhysicalConnectionToExternal</a>.

## Syntax

```
NTSTATUS UnregisterPhysicalConnectionToExternal(
  PDEVICE_OBJECT  DeviceObject,
  PUNKNOWN        FromUnknown,
  ULONG           FromPin,
  PUNICODE_STRING ToString,
  ULONG           ToPin
);
```

## Parameters

`DeviceObject`

Pointer to the device object for the adapter device. This parameter must point to a system structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>.

`FromUnknown`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536842">IPort</a> interface of a port driver object. The port driver object that is associated with <i>FromUnknown</i> is bound to the subdevice that supplies the connection's data source pin.

`FromPin`

Specifies a pin ID. This parameter identifies the data source (output) pin on the filter that is associated with the <i>FromUnknown</i> interface.

`ToString`

Pointer to a null-terminated Unicode string that contains the name of the external filter that supplies the connection's data sink pin.

`ToPin`

Specifies a pin ID. This parameter identifies the data sink (input) pin on the external filter that is named by the <i>ToString</i> parameter.


## Return Value

<b>UnregisterPhysicalConnectionToExternal</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## Remarks

For more information, see <a href="https://msdn.microsoft.com/d8ebd6d9-37ed-4890-aae1-5ecf58f2e22a">Dynamic Audio Subdevices</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536842">IPort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537022">IUnregisterPhysicalConnection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537729">PcRegisterPhysicalConnectionToExternal</a>
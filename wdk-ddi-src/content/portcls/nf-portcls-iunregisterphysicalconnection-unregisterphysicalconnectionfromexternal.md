---
UID: NF:portcls.IUnregisterPhysicalConnection.UnregisterPhysicalConnectionFromExternal
title: IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal method
author: windows-driver-content
description: The UnregisterPhysicalConnectionFromExternal method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnectionFromExternal.
old-location: audio\iunregisterphysicalconnection_unregisterphysicalconnectionfromexternal.htm
old-project: audio
ms.assetid: 82d71ee0-13e1-4f7f-ad81-9e1b6e484052
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IUnregisterPhysicalConnection, IUnregisterPhysicalConnection interface [Audio Devices], UnregisterPhysicalConnectionFromExternal method, IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal, UnregisterPhysicalConnectionFromExternal method [Audio Devices], UnregisterPhysicalConnectionFromExternal method [Audio Devices], IUnregisterPhysicalConnection interface, UnregisterPhysicalConnectionFromExternal,IUnregisterPhysicalConnection.UnregisterPhysicalConnectionFromExternal, audio.iunregisterphysicalconnection_unregisterphysicalconnectionfromexternal, audmp-routines_24091cfd-dee9-400a-8cb6-f3a4a44ed9c5.xml, portcls/IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal
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
-	IUnregisterPhysicalConnection.UnregisterPhysicalConnectionFromExternal
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal method
The <b>UnregisterPhysicalConnectionFromExternal</b> method deletes the registration of a physical connection that was registered by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff537728">PcRegisterPhysicalConnectionFromExternal</a>.

## Syntax

```
NTSTATUS UnregisterPhysicalConnectionFromExternal(
  PDEVICE_OBJECT  DeviceObject,
  PUNICODE_STRING FromString,
  ULONG           FromPin,
  PUNKNOWN        ToUnknown,
  ULONG           ToPin
);
```

## Parameters

`DeviceObject`

Pointer to the device object for the adapter device. This parameter must point to a system structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>.

`FromString`

Pointer to a null-terminated Unicode string that contains the name of the external filter that supplies the connection's data source pin.

`FromPin`

Specifies a pin ID. This parameter identifies the data source (output) pin on the external filter that is named by the <i>FromString</i> parameter.

`ToUnknown`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536842">IPort</a> interface of a port driver object. The port driver object that is associated with <i>ToUnknown</i> is bound to the subdevice that supplies the connection's data sink pin.

`ToPin`

Specifies a pin ID. This parameter identifies the data sink (input) pin on the filter that is associated with the <i>ToUnknown</i> interface.


## Return Value

<b>UnregisterPhysicalConnectionFromExternal</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537728">PcRegisterPhysicalConnectionFromExternal</a>
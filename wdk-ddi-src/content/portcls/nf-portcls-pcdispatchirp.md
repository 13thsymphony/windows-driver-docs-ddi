---
UID : NF:portcls.PcDispatchIrp
title : PcDispatchIrp function
author : windows-driver-content
description : The PcDispatchIrp function dispatches an IRP to the PortCls system driver's default handler.
old-location : audio\pcdispatchirp.htm
old-project : audio
ms.assetid : 01add66e-a007-4b1d-add6-c5be71dd0d61
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : PcDispatchIrp
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : portcls.h
req.include-header : 
req.target-type : Universal
req.target-min-winverclnt : The PortCls system driver implements the PcDispatchIrp function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : PcDispatchIrp
req.alt-loc : Portcls.lib,Portcls.dll
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
req.typenames : PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# PcDispatchIrp function
The <b>PcDispatchIrp</b> function dispatches an IRP to the PortCls system driver's default handler.

## Syntax

````
PORTCLASSAPI NTSTATUS NTAPI PcDispatchIrp(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp
);
````

## Parameters

`pDeviceObject`



`pIrp`




## Return Value

<b>PcDispatchIrp</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## Remarks

As part of its initialization process, the <a href="..\portcls\nf-portcls-pcinitializeadapterdriver.md">PcInitializeAdapterDriver</a> function loads pointers to handlers for several IRPs into the driver object. Following the call to <b>PcInitializeAdapterDriver</b>, an adapter driver can choose to overwrite one or more of the PortCls handler pointers with pointers to its own IRP handlers.

If, after receiving an IRP, the adapter driver's IRP handler determines that the IRP should be handled by the PortCls IRP handler instead, the adapter driver's handler calls <b>PcDispatchIrp</b> to forward the IRP to the PortCls handler.

For a code example, see the SB16 sample audio driver in the Microsoft Windows Driver Kit (WDK).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | portcls.h |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_irp.md">IRP</a>
</dt>
<dt>
<a href="..\portcls\nf-portcls-pcinitializeadapterdriver.md">PcInitializeAdapterDriver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcDispatchIrp function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
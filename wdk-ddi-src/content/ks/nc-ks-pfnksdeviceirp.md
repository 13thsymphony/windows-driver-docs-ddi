---
UID : NC:ks.PFNKSDEVICEIRP
title : PFNKSDEVICEIRP
author : windows-driver-content
description : An AVStream minidriver's IRP handler routine is called when these IRPs is dispatched by the device.IRP_MN_QUERY_REMOVE_DEVICEIRP_MN_QUERY_STOP_DEVICEIRP_MN_QUERY_INTERFACE
old-location : stream\avstrminidevicequeryremove.htm
old-project : stream
ms.assetid : c31d7e52-46f7-46b9-9fa2-1778f2301b4d
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : NpdBrokerUninitialize
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ks.h
req.include-header : Ks.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : AVStrMiniDeviceQueryRemove
req.alt-loc : ks.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL (See Remarks section)
req.typenames : KEYWORDSELECTOR
---


# PFNKSDEVICEIRP callback function
An AVStream minidriver's IRP handler routine is called when these IRPs is dispatched by the device.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff551705">IRP_MN_QUERY_REMOVE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551725">IRP_MN_QUERY_STOP_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>

## Syntax

```
PFNKSDEVICEIRP Pfnksdeviceirp;

NTSTATUS Pfnksdeviceirp(
  PKSDEVICE Device,
  PIRP Irp
)
{...}
```

## Parameters

`Device`

Pointer to the <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> that dispatched the IRP.

`Irp`

The IRP issued by <i>Device</i>.


## Return Value

Should return STATUS_SUCCESS or the error code that was returned from the attempt to perform the operation. If this is not the case, return an appropriate error code.

## Remarks

The minidriver specifies this routine's address in the <b>QueryRemove</b> member of its <a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a> structure.

This routine is called when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551705">IRP_MN_QUERY_REMOVE_DEVICE</a> is dispatched by the device. It will usually be provided by minidrivers that want to prevent removal of the device or by minidrivers that must disallow activity that would otherwise prevent them from committing to a device removal operation. If this routine is not provided, AVStream will assume that the device can commit to a removal.

The routine is called at IRQL = PASSIVE_LEVEL and may not return STATUS_PENDING; a success code indicates that the device can commit to a removal and an error code indicates that it cannot.

Return success if the device can be removed (or drivers can be updated) without disrupting the machine.

This routine is optional.

The minidriver specifies a pointer to this routine in the <b>QueryStop</b> member of its <a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a> structure.

Use <i>AVStrMiniQueryStop</i> to prevent the stopping of the device or to disallow activity that would prevent the minidriver from committing to a stop operation. If this routine is not specified, AVStream assumes that the minidriver can commit to a stop operation.

Success indicates that the device can commit to a stop and an error code indicates that it cannot. Do not return STATUS_PENDING.

A driver or system component sends this IRP to get information about an interface exported by your driver. For more information about the IRP, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>.

The minidriver specifies this routine's address in the <b>QueryInterface</b> member of its <a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL (See Remarks section) |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSDEVICEIRP routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
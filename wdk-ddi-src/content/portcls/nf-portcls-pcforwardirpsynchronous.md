---
UID: NF:portcls.PcForwardIrpSynchronous
title: PcForwardIrpSynchronous function
author: windows-driver-content
description: The PcForwardIrpSynchronous function is used by IRP handlers to forward Plug and Play IRPs to the physical device object (PDO).
old-location: audio\pcforwardirpsynchronous.htm
old-project: audio
ms.assetid: 29f69d26-6788-4c52-b6a4-ef96991ea238
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcForwardIrpSynchronous
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcForwardIrpSynchronous function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PcForwardIrpSynchronous
req.alt-loc: Portcls.lib,Portcls.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# PcForwardIrpSynchronous function



## -description
The <b>PcForwardIrpSynchronous</b> function is used by IRP handlers to forward Plug and Play IRPs to the <a href="wdkgloss.p#wdkgloss.physical_device_object__pdo_#wdkgloss.physical_device_object__pdo_"><i>physical device object (PDO)</i></a>.



## -syntax

````
NTSTATUS PcForwardIrpSynchronous(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp
);
````


## -parameters

### -param DeviceObject [in]

Pointer to the audio device's device object. This parameter must point to a system structure of type <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>.


### -param Irp [in]

Pointer to the <a href="..\wdm\ns-wdm-_irp.md">IRP</a> that is to be forwarded


## -returns
<b>PcForwardIrpSynchronous</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.


## -remarks
<b>PcForwardIrpSynchronous</b> causes the next PDO to receive the IRP and block until the IRP has been completed by the physical device driver. At that point, <b>PcForwardIrpSynchronous</b> unblocks and returns to the caller. The caller (an IRP handler) should eventually return--possibly with a status of STATUS_PENDING. In general, any IRP handler that calls this function must specify the action IRP_ACTION_FINISH upon returning. Any other action would result in the IRP being forwarded to the physical device a second time.

The <a href="..\portcls\nf-portcls-pccompleteirp.md">PcCompleteIrp</a> function is used when an IRP handler returns STATUS_PENDING and the IRP must be completed later.


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_irp.md">IRP</a>
</dt>
<dt>
<a href="..\portcls\nf-portcls-pccompleteirp.md">PcCompleteIrp</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcForwardIrpSynchronous function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


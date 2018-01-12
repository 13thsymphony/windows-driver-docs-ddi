---
UID: NC:srb.PHW_INTERRUPT
title: PHW_INTERRUPT
author: windows-driver-content
description: The PHW_INTERRUPT routine prototype declares the miniport driver's interrupt handler routine.
old-location: storage\phw_interrupt.htm
old-project: storage
ms.assetid: d61892c6-f6ca-4077-909e-a21076375e5a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: srb.h
req.include-header: Storport.h, Srb.h, Storport.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: (*PHW_INTERRUPT)
req.alt-loc: srb.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# PHW_INTERRUPT callback



## -description
The PHW_INTERRUPT routine prototype declares the miniport driver's interrupt handler routine. 



## -prototype

````
typedef BOOLEAN (*PHW_INTERRUPT)(
  _In_ PVOID DeviceExtension 
);
````


## -parameters

### -param DeviceExtension  [in]

Pointer to the miniport driver's per-HBA storage area. 


## -returns
If the interrupt handler routine determines that its HBA generated the interrupt, it returns <b>TRUE</b>. If the interrupt handler determines that its HBA did not generate the interrupt, it should return <b>FALSE</b> as soon as possible. 


## -remarks
The interrupt handler routine for both SCSI and StorPort miniport drivers are declared using this prototype. 

For more information about the SCSI miniport driver's interrupt handler routine see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557312">HwScsiInterrupt</a>. 

For more information about the miniport driver's interrupt handler routine that is used with the StorPort driver see <a href="..\storport\nc-storport-hw_interrupt.md">HwStorInterrupt</a>. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Srb.h (include Storport.h, Srb.h, or Storport.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557312">HwScsiInterrupt</a>
</dt>
<dt>
<a href="..\storport\nc-storport-hw_interrupt.md">HwStorInterrupt</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PHW_INTERRUPT callback function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


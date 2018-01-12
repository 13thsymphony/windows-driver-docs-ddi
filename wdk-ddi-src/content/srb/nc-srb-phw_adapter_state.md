---
UID: NC:srb.PHW_ADAPTER_STATE
title: PHW_ADAPTER_STATE
author: windows-driver-content
description: The PHW_INITIALIZE routine prototype declares a routine that saves or restores the state of the miniport driver's HBA.
old-location: storage\phw_adapter_state.htm
old-project: storage
ms.assetid: 68483404-5ea7-47f6-a6ae-6909e5b6759e
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
req.alt-api: (*PHW_ADAPTER_STATE)
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

# PHW_ADAPTER_STATE callback



## -description
The PHW_INITIALIZE routine prototype declares a routine that saves or restores the state of the miniport driver's HBA. 



## -prototype

````
typedef BOOLEAN (*PHW_ADAPTER_STATE)(
  _In_ PVOID   DeviceExtension ,
  _In_ PVOID   Context,
  _In_ BOOLEAN SaveState
);
````


## -parameters

### -param DeviceExtension  [in]

Pointer to the miniport driver's per-HBA storage area. 


### -param Context [in]

Reserved for system use.


### -param SaveState [in]

Indicates, when <b>TRUE</b>, that the miniport driver should save the current state of the HBA until the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557278">HwScsiAdapterState</a> routine is called again with <i>SaveState</i> set to <b>FALSE</b> to restore the saved state.


## -returns
The routine declared by this prototype returns <b>TRUE</b> if it successfully saved or restored the HBA state, <b>FALSE</b> otherwise. 


## -remarks
Only SCSI miniport drivers use this prototype. Miniport drivers that work with the StorPort driver do not use the routine that is declared by this prototype.

For more information about the routine declared by this prototype, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557278">HwScsiAdapterState</a>. 


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557278">HwScsiAdapterState</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PHW_ADAPTER_STATE callback function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


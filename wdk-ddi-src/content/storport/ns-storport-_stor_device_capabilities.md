---
UID: NS.STORPORT._STOR_DEVICE_CAPABILITIES
title: _STOR_DEVICE_CAPABILITIES
author: windows-driver-content
description: The STOR_DEVICE_CAPABILITIES structure reports device capabilities to the Storport driver in response to a capabilities query in a SCSI request block (SRB) with a function of SRB_FUNCTION_PNP.
old-location: storage\stor_device_capabilities.htm
old-project: storage
ms.assetid: 62BE93C6-8E1C-4430-BB07-C25E8D4076B0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _STOR_DEVICE_CAPABILITIES, PSTOR_DEVICE_CAPABILITIES, *PSTOR_DEVICE_CAPABILITIES, STOR_DEVICE_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STOR_DEVICE_CAPABILITIES
req.alt-loc: storport.h
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
req.product: Windows 10 or later.
---

# _STOR_DEVICE_CAPABILITIES structure



## -description
The <b>STOR_DEVICE_CAPABILITIES</b> structure reports device capabilities to the Storport driver in response to a capabilities query in a SCSI request block (SRB) with a function of SRB_FUNCTION_PNP.<b> STOR_DEVICE_CAPABILITIES</b> is a subset of the <a href="kernel.device_capabilities">DEVICE_CAPABILITIES</a> structure containing the members relevant to storage devices.



## -syntax

````
typedef struct _STOR_DEVICE_CAPABILITIES {
  ULONG Version;
  ULONG DeviceD1  :1;
  ULONG DeviceD2  :1;
  ULONG LockSupported  :1;
  ULONG EjectSupported  :1;
  ULONG Removeable  :1;
  ULONG DockDevice  :1;
  ULONG UniqueID  :1;
  ULONG SilentInstall  :1;
  ULONG RawDeviceOK  :1;
  ULONG SurpriseRemovalOK  :1;
  ULONG NoDisplayInUI  :1;
} STOR_DEVICE_CAPABILITIES, *PSTOR_DEVICE_CAPABILITIES;
````


## -struct-fields

### -field Version

Specifies the version of the structure. Set to STOR_DEVICE_CAPABILITIES_EX_VERSION_1 by Storport.


### -field DeviceD1

Specifies whether the device hardware supports the D1 power state. Miniport drivers set this bit to 0.


### -field DeviceD2

Specifies whether the device hardware supports the D2 power state. Miniport drivers set this bit to 0.


### -field LockSupported

Specifies whether the device supports physical-device locking that prevents device ejection. This member pertains to ejecting a LUN or a unit device.


### -field EjectSupported

Specifies whether the device supports software-controlled device ejection while the system is in the <b>PowerSystemWorking</b> state. This member pertains to ejecting a LUN or unit device.


### -field Removeable

Specifies whether the device can be dynamically removed from its immediate parent. If <b>Removable</b> is set to <b>TRUE</b>, the device does not belong to the same physical object as its parent. 

If <b>Removable</b> is set to <b>TRUE</b>, the device is displayed in the Unplug or Eject Hardware program, unless <b>SurpriseRemovalOK</b> is also set to <b>TRUE</b>.


### -field DockDevice

Specifies whether the device is a docking peripheral.


### -field UniqueID

Specifies whether the device's instance ID is unique system-wide. This bit is clear if the instance ID is unique only within the scope of the bus.


### -field SilentInstall

Specifies whether <b>Device Manager</b> should suppress all installation dialog boxes; except required dialog boxes such as "no compatible drivers found."


### -field RawDeviceOK

Specifies whether the driver for the underlying bus can drive the device if there is no function driver (for example, SCSI devices in pass-through mode). This mode of operation is called raw mode.


### -field SurpriseRemovalOK

Specifies whether the miniport driver for the device can handle the case where the device is removed before Storport can send SRB_FUNCTION_PNP with <b>StorRemoveDevice</b> as the <b>PnPAction</b> in the <a href="storage.scsi_pnp_request_block">SCSI_PNP_REQUEST_BLOCK</a> structure. If <b>SurpriseRemovalOK</b> is set to <b>TRUE</b>, the device can be safely removed from its immediate parent regardless of the state that its driver is in. 


### -field NoDisplayInUI

Do not display the device in the user interface. If this bit is set, the device is never displayed in the user interface, even if the device is present but fails to start. Miniport drivers do not set this bit.


## -remarks
When a miniport driver receives an SRB in its <a href="storage.hwstorstartio">HwStorStartIo</a> routine where the SRB function is SRB_FUNCTION_PNP, the SRB is formatted as a <a href="storage.scsi_pnp_request_block">SCSI_PNP_REQUEST_BLOCK</a> structure. If the <b>PnPAction</b> member of the SRB is <b>StorQueryCapabilities</b>, the miniport can return a <b>STOR_DEVICE_CAPABILITIES</b> structure in the <b>DataBuffer</b> member of the SRB.

Storport sends this structure to the miniport with all members initialized to 0. On return, only the <b>Removable</b> field is used from this structure.

Starting with Windows 8, miniports should use the <a href="storage.stor_device_capabilities_ex">STOR_DEVICE_CAPABILITIES_EX</a> structure to indicate support for additional capabilities.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows Vista.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.device_capabilities">DEVICE_CAPABILITIES</a>
</dt>
<dt>
<a href="storage.scsi_pnp_request_block">SCSI_PNP_REQUEST_BLOCK</a>
</dt>
<dt>
<a href="storage.stor_device_capabilities_ex">STOR_DEVICE_CAPABILITIES_EX</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_DEVICE_CAPABILITIES structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


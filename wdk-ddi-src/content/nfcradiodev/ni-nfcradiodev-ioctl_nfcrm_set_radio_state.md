---
UID: NI.nfcradiodev.IOCTL_NFCRM_SET_RADIO_STATE
title: IOCTL_NFCRM_SET_RADIO_STATE
author: windows-driver-content
description: This IOCTL is used by the radio management application or service to set the radio power state of the proximity device.
old-location: nfpdrivers\ioctl_nfcrm_set_radio_state.htm
old-project: nfpdrivers
ms.assetid: C54C774A-3FBB-4850-BBB2-2B330CC64A8D
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _NFC_CX_RF_DISCOVERY_CONFIG, *PNFC_CX_RF_DISCOVERY_CONFIG, NFC_CX_RF_DISCOVERY_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: nfcradiodev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_NFCRM_SET_RADIO_STATE
req.alt-loc: nfcradiodev.h
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
---

# IOCTL_NFCRM_SET_RADIO_STATE IOCTL



## -description
This IOCTL is used by the radio management application or service to set the radio power state of the proximity device. The MediaRadioOn field is used to indicate the request power state. When the proximity radio power state is disabled, the driver should disable the proximity device interfaces (GUID_DEVINTERFACE_NFP and GUID_DEVINTERFACE_SMARTCARD_READER interfaces) and disable the P2P and reader/writer modes of the device. If the proximity radio power state is enabled, the driver should enable the proximity device interfaces and enable P2P and reader/writer modes of the controller. For more information about optimizing power modes on this device, see <a href="nfpdrivers.nfc_power_management">NFC Power Management</a>.



## -ioctlparameters

### -input-buffer

<a href="nfpdrivers._nfcrm_set_radio_state_"> NFCRM_SET_RADIO_STATE structure</a>



### -input-buffer-length
sizeof(NFCRM_SET_RADIO_STATE)


### -output-buffer
None


### -output-buffer-length
None


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

 


## -remarks
The <b>STATUS_INVALID_PARAMETER</b> return code is no longer required. A bug was discovered in Windows 10 build 10240, that Windows would send a non-null output parameter with this IOCTL. This bug was fixed in later versions of Windows. To simplify code, drivers can ignore the output parameters in all versions of Windows 10.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Nfcradiodev.h</dt>
</dl>
</td>
</tr>
</table>
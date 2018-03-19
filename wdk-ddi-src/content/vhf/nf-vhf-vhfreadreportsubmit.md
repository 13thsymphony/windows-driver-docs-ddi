---
UID: NF:vhf.VhfReadReportSubmit
title: VhfReadReportSubmit function
author: windows-driver-content
description: The HID source driver calls this method to submit a HID Read (Input) Report to Virtual HID Framework (VHF).
old-location: hid\vhfreadreportsubmit.htm
old-project: hid
ms.assetid: DCC4EB4C-B9A0-4E25-B3BD-4CAB07022A7B
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: VhfReadReportSubmit, VhfReadReportSubmit method [Human Input Devices], hid.vhfreadreportsubmit, vhf/VhfReadReportSubmit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vhf.h
req.include-header: 
req.target-type: Windows
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
req.lib: VhfKm.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	vhfKm.lib
-	vhfKm.dll
api_name:
-	VhfReadReportSubmit
product: Windows
targetos: Windows
req.typenames: USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, *PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
req.product: Windows 10 or later.
---


# VhfReadReportSubmit function
The HID source driver calls this method to submit a HID Read (Input) Report to Virtual HID Framework (VHF).

## Syntax

````
NTSTATUS VhfReadReportSubmit(
  [in] VHFHANDLE        VhfHandle,
  [in] PHID_XFER_PACKET HidTransferPacket
);
````

## Parameters

`VhfHandle`

A handle to a virtual HID device that your HID source driver received in the previous call to <a href="..\vhf\nf-vhf-vhfcreate.md">VhfCreate</a>.

`HidTransferPacket`

A pointer to a <a href="..\vhf\ns-vhf-_hid_xfer_packet.md">HID_XFER_PACKET</a> structure that describes the HID report.


## Return Value

If the <b>VhfReadReportSubmit</b> call succeeds, the method returns STATUS_SUCCESS. Otherwise an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS </a> value.

## Remarks

The HID source driver can choose to implement its buffering policy or let Virtual HID Framework (VHF) handle buffering. 

If the driver uses its own buffering policy, then it must implement and register an <a href="..\vhf\nc-vhf-evt_vhf_ready_for_next_read_report.md">EvtVhfReadyForNextReadReport</a> callback function in its call to <a href="..\vhf\nf-vhf-vhfcreate.md">VhfCreate</a>. It must call <i>VhfReadReportSubmit</i> only once after VHF has invoked <i>EvtVhfReadyForNextReadReport</i>. After the callback has been invoked, the driver can reuse the transfer buffer pointed to by <i>HidTransferPacket</i>. The driver must wait for the next time that VHF invokes <i>EvtVhfReadyForNextReadReport</i> before calling this method again. 

If the HID source driver does not implement the <a href="..\vhf\nc-vhf-evt_vhf_ready_for_next_read_report.md">EvtVhfReadyForNextReadReport</a> callback, then there are no restrictions on calling this method. VHF uses the default buffering policy. The driver can reuse the transfer buffer after the call returns.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | vhf.h |
| **Library** | VhfKm.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/26964963-792F-4529-B4FC-110BF5C65B35">Write a HID source driver by using Virtual HID Framework (VHF)</a>
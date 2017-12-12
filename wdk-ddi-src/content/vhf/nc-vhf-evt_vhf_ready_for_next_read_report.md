---
UID: NC.vhf.EVT_VHF_READY_FOR_NEXT_READ_REPORT
title: EVT_VHF_READY_FOR_NEXT_READ_REPORT
author: windows-driver-content
description: The HID source driver implements this event call back function to use its buffering scheme for HID Input Reports, and wants to get notified when the next report can be submitted to VHF.
old-location: hid\evtvhfreadyfornextreadreport.htm
old-project: hid
ms.assetid: 02DDBE00-C342-474B-8D06-FBB929BA4760
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, *PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: vhf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EvtVhfReadyForNextReadReport
req.alt-loc: vhf.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# EVT_VHF_READY_FOR_NEXT_READ_REPORT callback



## -description
The HID source driver implements this event call back function to use its buffering scheme for HID Input Reports, and wants to get notified when the next report can be submitted to VHF.



## -prototype

````
EVT_VHF_READY_FOR_NEXT_READ_REPORT EvtVhfReadyForNextReadReport;

void EvtVhfReadyForNextReadReport(
  _In_ PVOID VhfClientContext
)
{ ... }
````


## -parameters

### -param VhfClientContext [in]

Pointer to the HID source driver-defined context structure that the driver passed in the previous call to <a href="hid.vhfcreate">VhfCreate</a> to create the virtual HID device.


## -returns
This callback function does not return a value.


## -remarks
Virtual HID Framework (VHF) invokes this callback function to notify the HID source driver that it can submit a buffer to get the HID Input Report. After the callback is invoked, the HID source driver must call <a href="hid.vhfreadreportsubmit">VhfReadReportSubmit</a>  only once. If a portion of the HID Input Report is still pending, the driver must wait for VHF to invoke <i>EvtVhfReadyForNextReadReport</i> before the driver can call <b>VhfReadReportSubmit</b> again.

If the HID source driver does not implement this callback function, VHF uses a default buffering policy for HID Read (Input) Reports.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
None supported

</td>
</tr>
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
<dt>Vhf.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/26964963-792F-4529-B4FC-110BF5C65B35">Write a HID source driver by using Virtual HID Framework (VHF)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20EVT_VHF_READY_FOR_NEXT_READ_REPORT callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


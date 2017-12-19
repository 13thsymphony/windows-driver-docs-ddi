---
UID: NS.PTPUSD._PTP_VENDOR_DATA_OUT
title: _PTP_VENDOR_DATA_OUT
author: windows-driver-content
description: The PTP_VENDOR_DATA_OUT structure contains information that the device sends to an application, in response to a command the application issued to the device.
old-location: image\ptp_vendor_data_out.htm
old-project: Image
ms.assetid: 2585c7ce-6dba-491a-86c1-5ee69f28136f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _PTP_VENDOR_DATA_OUT, *PPTP_VENDOR_DATA_OUT, PTP_VENDOR_DATA_OUT, PPTP_VENDOR_DATA_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ptpusd.h
req.include-header: Ptpusd.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PTP_VENDOR_DATA_OUT
req.alt-loc: ptpusd.h
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
req.product: Windows 10 or later.
---

# _PTP_VENDOR_DATA_OUT structure



## -description
The PTP_VENDOR_DATA_OUT structure contains information that the device sends to an application, in response to a command the application issued to the device.



## -syntax

````
typedef struct _PTP_VENDOR_DATA_OUT {
  WORD  ResponseCode;
  DWORD SessionId;
  DWORD TransactionId;
  DWORD Params[PTP_MAX_PARAMS];
  BYTE  VendorReadData[1];
} PTP_VENDOR_DATA_OUT, *PPTP_VENDOR_DATA_OUT;
````


## -struct-fields

### -field ResponseCode

Specifies the response code. These codes are defined in the PIMA 15740:2000 standard.


### -field SessionId

Specifies the session ID. This member is not currently used by the PTP driver and should be set to 0.


### -field TransactionId

Specifies the transaction ID. This member is not currently used by the PTP driver and should be set to 0.


### -field Params

Is an array consisting of PTP_MAX_PARAMS (defined in <i>Ptpusd.h</i>) elements, representing the parameters of the response.


### -field VendorReadData

Is an array containing an (optional) first byte to read from the device.


## -remarks
See <a href="https://msdn.microsoft.com/3d360a9f-5a65-452b-a8ad-080dc7d8c8f5">Vendor-Extended Commands</a> for more information and example code that uses this structure.

For more information about the response codes used in the <b>ResponseCode</b> member, see PIMA 15740:2000, <i>Photography </i>−<i> Electronic still picture imaging </i>−<i> Picture Transfer Protocol (PTP) for Digital Still Photography Devices</i>,<i> First Edition</i>, July 5, 2000, http://www.pima.net/standards/it10/PIMA15740/. 


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Me and in Windows XP and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ptpusd.h (include Ptpusd.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="image.ptp_vendor_data_in">PTP_VENDOR_DATA_IN</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20PTP_VENDOR_DATA_OUT structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


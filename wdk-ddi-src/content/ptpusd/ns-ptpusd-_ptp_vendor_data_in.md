---
UID: NS:ptpusd._PTP_VENDOR_DATA_IN
title: "_PTP_VENDOR_DATA_IN"
author: windows-driver-content
description: The PTP_VENDOR_DATA_IN structure contains information about an arbitrary command that an application issues to the device.
old-location: image\ptp_vendor_data_in.htm
old-project: image
ms.assetid: 896209d0-d545-495b-b743-98c0b9d976ff
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PPTP_VENDOR_DATA_IN, PPTP_VENDOR_DATA_IN, PPTP_VENDOR_DATA_IN structure pointer [Imaging Devices], PTP_VENDOR_DATA_IN, PTP_VENDOR_DATA_IN structure [Imaging Devices], _PTP_VENDOR_DATA_IN, image.ptp_vendor_data_in, ptpusd/PPTP_VENDOR_DATA_IN, ptpusd/PTP_VENDOR_DATA_IN, wiastrct_b0ebb671-78d9-4224-8bde-893fb0afc9f8.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ptpusd.h
req.include-header: Ptpusd.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later.
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ptpusd.h
api_name:
-	PTP_VENDOR_DATA_IN
product: Windows
targetos: Windows
req.typenames: PTP_VENDOR_DATA_IN, *PPTP_VENDOR_DATA_IN
req.product: Windows 10 or later.
---

# _PTP_VENDOR_DATA_IN structure
The PTP_VENDOR_DATA_IN structure contains information about an arbitrary command that an application issues to the device.

## Syntax
````
typedef struct _PTP_VENDOR_DATA_IN {
  WORD  OpCode;
  DWORD SessionId;
  DWORD TransactionId;
  DWORD Params[PTP_MAX_PARAMS];
  DWORD NumParams;
  DWORD NextPhase;
  BYTE  VendorWriteData[1];
} PTP_VENDOR_DATA_IN, *PPTP_VENDOR_DATA_IN;
````

## Members


`NextPhase`

Indicates whether to read data from the device, write data to the device, or neither. This member can be set to one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PTP_NEXTPHASE_NO_DATA

</td>
<td>
No data is to be read from or written to the device.

</td>
</tr>
<tr>
<td>
PTP_NEXTPHASE_READ_DATA

</td>
<td>
Read data from the device.

</td>
</tr>
<tr>
<td>
PTP_NEXTPHASE_WRITE_DATA

</td>
<td>
Write data to the device.

</td>
</tr>
</table>

`NumParams`

Specifies the actual number of elements in the <b>Params</b> array.

`OpCode`

Specifies the command opcode. These codes are defined in the PIMA 15740:2000 standard.

`Params`

Is an array consisting of PTP_MAX_PARAMS (defined in <i>Ptpusd.h</i>) elements, representing the parameters of the command.

`SessionId`

Specifies the session ID. This member is not currently used by the PTP driver and should be set to 0.

`TransactionId`

Specifies the transaction ID. This member is not currently used by the PTP driver and should be set to 0.

`VendorWriteData`

Is an array containing an (optional) first byte to write to the device.

## Remarks
See <a href="https://msdn.microsoft.com/3d360a9f-5a65-452b-a8ad-080dc7d8c8f5">Vendor-Extended Commands</a> for more information and example code that uses this structure. 

For more information about the opcodes used in the <b>OpCode</b> member, see PIMA 15740:2000, <i>Photography </i>−<i> Electronic still picture imaging </i>−<i> Picture Transfer Protocol (PTP) for Digital Still Photography Devices</i>,<i> First Edition</i>, July 5, 2000, http://www.pima.net/standards/it10/PIMA15740/.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me and in Windows XP and later. Available in Windows Me and in Windows XP and later. |
| **Header** | ptpusd.h (include Ptpusd.h) |

## See Also

<a href="..\ptpusd\ns-ptpusd-_ptp_vendor_data_out.md">PTP_VENDOR_DATA_OUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20PTP_VENDOR_DATA_IN structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID : NS:bthioctl._BTH_VENDOR_PATTERN
title : _BTH_VENDOR_PATTERN
author : windows-driver-content
description : The BTH_VENDOR_PATTERN structure specifies a vendor pattern.
old-location : bltooth\bth_vendor_pattern.htm
old-project : bltooth
ms.assetid : 694020c6-dd0a-46c7-9122-cd86ce28d03a
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : PBTH_VENDOR_PATTERN, _BTH_VENDOR_PATTERN, BTH_VENDOR_PATTERN, bthioctl/PBTH_VENDOR_PATTERN, BTH_VENDOR_PATTERN structure [Bluetooth Devices], bltooth.bth_vendor_pattern, PBTH_VENDOR_PATTERN structure pointer [Bluetooth Devices], bth_ref_e5c1f867-d585-4c90-bfe1-7b3c4a6e1582.xml, *PBTH_VENDOR_PATTERN, bthioctl/BTH_VENDOR_PATTERN
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : bthioctl.h
req.include-header : Bthioctl.h
req.target-type : Windows
req.target-min-winverclnt : Versions: Available in Windows Vista, and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<= PASSIVE_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PBTH_VENDOR_PATTERN, BTH_VENDOR_PATTERN"
---

# _BTH_VENDOR_PATTERN structure
The BTH_VENDOR_PATTERN structure specifies a vendor pattern.

## Syntax
````
typedef struct _BTH_VENDOR_PATTERN {
  UCHAR Offset;
  UCHAR Size;
  UCHAR Pattern[1];
} BTH_VENDOR_PATTERN, *PBTH_VENDOR_PATTERN;
````

## Members


`Offset`

The offset, in bytes, of the pattern from the beginning of the event data, excluding the event
     header.

`Pattern`

A buffer that contains pattern data.

`Size`

The size, in bytes, of the pattern.

## Remarks
The BTH_VENDOR_PATTERN structure specifies vendor patterns for the 
    <mshelp:link keywords="bltooth.bth_vendor_specific_command" tabindex="0"><b>
    BTH_VENDOR_SPECIFIC_COMMAND</b></mshelp:link> structure.

A list of patterns can immediately follow the vendor-specific command data that is specified in the 
    <b>Data</b> member of the BTH_VENDOR_SPECIFIC_COMMAND structure.

Patterns are required if a vendor-specific command does not follow the standard HCI flow control and a
    vendor-specific event is generated in response to the vendor-specific command.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bthioctl.h (include Bthioctl.h) |

## See Also

<a href="..\bthioctl\ns-bthioctl-_bth_vendor_specific_command.md">BTH_VENDOR_SPECIFIC_COMMAND</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTH_VENDOR_PATTERN structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
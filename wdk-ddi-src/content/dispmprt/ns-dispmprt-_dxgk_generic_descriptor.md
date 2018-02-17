---
UID: NS:dispmprt._DXGK_GENERIC_DESCRIPTOR
title: "_DXGK_GENERIC_DESCRIPTOR"
author: windows-driver-content
description: The DXGK_GENERIC_DESCRIPTOR structure contains descriptive information about a child device of the display adapter.
old-location: display\dxgk_generic_descriptor.htm
old-project: display
ms.assetid: 181df1a6-044d-406d-bc6d-1b35b3d744fc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DXGK_GENERIC_DESCRIPTOR, display.dxgk_generic_descriptor, DmStructs_f77c03e6-d887-43ba-9499-ce1740cb6c9e.xml, *PDXGK_GENERIC_DESCRIPTOR, dispmprt/PDXGK_GENERIC_DESCRIPTOR, DXGK_GENERIC_DESCRIPTOR structure [Display Devices], PDXGK_GENERIC_DESCRIPTOR structure pointer [Display Devices], dispmprt/DXGK_GENERIC_DESCRIPTOR, PDXGK_GENERIC_DESCRIPTOR, DXGK_GENERIC_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dispmprt.h
apiname:
-	DXGK_GENERIC_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: DXGK_GENERIC_DESCRIPTOR, *PDXGK_GENERIC_DESCRIPTOR
---

# _DXGK_GENERIC_DESCRIPTOR structure
The DXGK_GENERIC_DESCRIPTOR structure contains descriptive information about a child device of the display adapter.

## Syntax
````
typedef struct _DXGK_GENERIC_DESCRIPTOR {
  WCHAR HardwareId[DXGK_MAX_REG_SZ_LEN];
  WCHAR InstanceId[DXGK_MAX_REG_SZ_LEN];
  WCHAR CompatibleId[DXGK_MAX_REG_SZ_LEN];
  WCHAR DeviceText[DXGK_MAX_REG_SZ_LEN];
} DXGK_GENERIC_DESCRIPTOR, *PDXGK_GENERIC_DESCRIPTOR;
````

## Members


`CompatibleId`

A sequence of wide-character strings, each of which is terminated by a single wide NULL character. The last string in the sequence is terminated by two wide NULL characters.

`DeviceText`

A single wide-character string, terminated by two wide NULL characters, that holds the device text of the child device.

`HardwareId`

A single wide-character string, terminated by two wide NULL characters, that holds the hardware ID of the child device.

`InstanceId`

A single wide-character string, terminated by two wide NULL characters, that holds the instance ID of the child device.

## Remarks
The display adapter has two types of child devices: <b>TypeVideoOutput</b> and <b>TypeOther</b>. For child devices of type <b>TypeOther</b>, the display port driver passes a DXGK_GENERIC_DESCRIPTOR structure to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_device_descriptor.md">DxgkDdiQueryDeviceDescriptor</a> function. <i>DxgkDdiQueryDeviceDescriptor</i> must fill in the members of the structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dispmprt.h (include Dispmprt.h) |

## See Also

<a href="..\dispmprt\ns-dispmprt-_dxgk_device_descriptor.md">DXGK_DEVICE_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_GENERIC_DESCRIPTOR structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID: NS:dispmprt._DXGK_DEVICE_DESCRIPTOR
title: "_DXGK_DEVICE_DESCRIPTOR"
author: windows-driver-content
description: The DXGK_DEVICE_DESCRIPTOR structure is used by the display port driver to request that the display miniport driver return all or a portion of a monitor's Extended Display Identification Data (EDID).
old-location: display\dxgk_device_descriptor.htm
old-project: display
ms.assetid: b6d89426-54d3-4f90-8687-c60e515b4d62
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PDXGK_DEVICE_DESCRIPTOR structure pointer [Display Devices], PDXGK_DEVICE_DESCRIPTOR, DmStructs_d66c7175-e264-49f4-94ce-f4a92a678010.xml, _DXGK_DEVICE_DESCRIPTOR, dispmprt/DXGK_DEVICE_DESCRIPTOR, DXGK_DEVICE_DESCRIPTOR structure [Display Devices], dispmprt/PDXGK_DEVICE_DESCRIPTOR, display.dxgk_device_descriptor, DXGK_DEVICE_DESCRIPTOR, *PDXGK_DEVICE_DESCRIPTOR
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
-	DXGK_DEVICE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: DXGK_DEVICE_DESCRIPTOR, *PDXGK_DEVICE_DESCRIPTOR
---

# _DXGK_DEVICE_DESCRIPTOR structure
The DXGK_DEVICE_DESCRIPTOR structure is used by the display port driver to request that the display miniport driver return all or a portion of a monitor's Extended Display Identification Data (EDID).

## Syntax
````
typedef struct _DXGK_DEVICE_DESCRIPTOR {
  ULONG DescriptorOffset;
  ULONG DescriptorLength;
  PVOID DescriptorBuffer;
} DXGK_DEVICE_DESCRIPTOR, *PDXGK_DEVICE_DESCRIPTOR;
````

## Members


`DescriptorBuffer`

A pointer to a buffer that receives all or a portion of the monitor's EDID. This buffer is allocated by the display port driver and filled in by the display miniport driver. The display miniport driver must not write more than <b>DescriptorLength</b> bytes to this buffer.

`DescriptorLength`

An integer that indicates the length, in bytes, of the buffer pointed to by <b>DescriptorBuffer</b>.

`DescriptorOffset`

An integer that indicates an offset, in bytes, into the EDID. This member specifies the beginning of the requested data.

## Remarks
The display port driver passes a DXGK_DEVICE_DESCRIPTOR structure to <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_device_descriptor.md">DxgkDdiQueryDeviceDescriptor</a> to request that the display miniport driver return all or a portion of a monitor's EDID. The desired portion of the EDID is specified by the <b>DescriptorOffset</b> and <b>DescriptorLength</b> members. For example, to request 256 bytes, starting at an offset of 128 bytes into a monitor's EDID, the display port driver would set <b>DescriptorOffset</b> to 128, and <b>DescriptorLength</b> to 256.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dispmprt.h (include Dispmprt.h) |

## See Also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_device_descriptor.md">DxgkDdiQueryDeviceDescriptor</a>

<a href="..\dispmprt\ns-dispmprt-_dxgk_generic_descriptor.md">DXGK_GENERIC_DESCRIPTOR</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_DEVICE_DESCRIPTOR structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID: NS:ntddk._WHEA_PCI_SLOT_NUMBER
title: "_WHEA_PCI_SLOT_NUMBER"
author: windows-driver-content
description: The WHEA_PCI_SLOT_NUMBER structure describes a logical PCI slot.
old-location: whea\whea_pci_slot_number.htm
old-project: whea
ms.assetid: 4e2938a2-6301-4d2a-a467-eca1f5bbb260
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: WHEA_PCI_SLOT_NUMBER, ntddk/PWHEA_PCI_SLOT_NUMBER, PWHEA_PCI_SLOT_NUMBER, whearef_6999e061-3501-48fe-bd6c-383493056665.xml, whea.whea_pci_slot_number, PWHEA_PCI_SLOT_NUMBER structure pointer [WHEA Drivers and Applications], _WHEA_PCI_SLOT_NUMBER, WHEA_PCI_SLOT_NUMBER structure [WHEA Drivers and Applications], ntddk/WHEA_PCI_SLOT_NUMBER, *PWHEA_PCI_SLOT_NUMBER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
-	ntddk.h
apiname:
-	WHEA_PCI_SLOT_NUMBER
product: Windows
targetos: Windows
req.typenames: "*PWHEA_PCI_SLOT_NUMBER, WHEA_PCI_SLOT_NUMBER"
---

# _WHEA_PCI_SLOT_NUMBER structure
The WHEA_PCI_SLOT_NUMBER structure describes a logical PCI slot.

## Syntax
````
typedef struct _WHEA_PCI_SLOT_NUMBER {
  union {
    struct {
      ULONG DeviceNumber  :5;
      ULONG FunctionNumber  :3;
      ULONG Reserved  :24;
    } bits;
    ULONG  AsULONG;
  } u;
} WHEA_PCI_SLOT_NUMBER, *PWHEA_PCI_SLOT_NUMBER;
````

## Members


`u`

A union that contains the following members:

## Remarks
A WHEA_PCI_SLOT_NUMBER structure is contained within the <a href="..\ntddk\ns-ntddk-_whea_aer_bridge_descriptor.md">WHEA_AER_BRIDGE_DESCRIPTOR</a>, <a href="..\ntddk\ns-ntddk-_whea_aer_endpoint_descriptor.md">WHEA_AER_ENDPOINT_DESCRIPTOR</a>, and <a href="..\ntddk\ns-ntddk-_whea_aer_rootport_descriptor.md">WHEA_AER_ROOTPORT_DESCRIPTOR</a> structures.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="..\ntddk\ns-ntddk-_whea_aer_endpoint_descriptor.md">WHEA_AER_ENDPOINT_DESCRIPTOR</a>

<a href="..\ntddk\ns-ntddk-_whea_aer_bridge_descriptor.md">WHEA_AER_BRIDGE_DESCRIPTOR</a>

<a href="..\ntddk\ns-ntddk-_whea_aer_rootport_descriptor.md">WHEA_AER_ROOTPORT_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_PCI_SLOT_NUMBER structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
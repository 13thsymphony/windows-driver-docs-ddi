---
UID: NC:wdm.PCI_MSIX_MASKUNMASK_ENTRY
title: PCI_MSIX_MASKUNMASK_ENTRY
author: windows-driver-content
description: The MaskTableEntry routine masks an interrupt in the MSI-X hardware interrupt table.
old-location: kernel\masktableentry.htm
old-project: kernel
ms.assetid: ADD9AA38-594D-413A-BE8B-BCC6B62EAA8E
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: MaskTableEntry, MaskTableEntry routine [Kernel-Mode Driver Architecture], PCI_MSIX_MASKUNMASK_ENTRY, drvr_interface_c4246cdd-8a44-423e-b145-fae6e1e96716.xml, kernel.masktableentry, kernel.msixmasktableentry, wdm/MaskTableEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista with Service Pack 1 (SP1), Windows Server 2008, and later versions of the Windows operating system.
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
req.irql: "<= DIRQL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	MaskTableEntry
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---


# PCI_MSIX_MASKUNMASK_ENTRY callback function
The <i>MaskTableEntry</i> routine masks an interrupt in the MSI-X hardware interrupt table.

## Syntax

```
PCI_MSIX_MASKUNMASK_ENTRY PciMsixMaskunmaskEntry;

NTSTATUS PciMsixMaskunmaskEntry(
  PVOID Context,
  ULONG TableEntry
)
{...}
```

## Parameters

`Context`

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="..\wdm\ns-wdm-_pci_msix_table_config_interface.md">PCI_MSIX_TABLE_CONFIG_INTERFACE</a> structure for the interface.

`TableEntry`

The index of the table entry in the MSI-X hardware interrupt table.


## Return Value

The <i>MaskTableEntry</i> routine might return one of the following NTSTATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>TableEntry</i> parameter is invalid.

</td>
</tr>
</table>

## Remarks

If a table entry is masked, the device does not generate any interrupts that correspond to that table entry.

You can unmask the table entry by calling <a href="..\wdm\nc-wdm-pci_msix_maskunmask_entry.md">UnmaskTableEntry</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista with Service Pack 1 (SP1), Windows Server 2008, and later versions of the Windows operating system.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | "<= DIRQL" |

## See Also

<a href="..\wdm\nc-wdm-pci_msix_maskunmask_entry.md">UnmaskTableEntry</a>



<a href="..\wdm\ns-wdm-_pci_msix_table_config_interface.md">PCI_MSIX_TABLE_CONFIG_INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCI_MSIX_MASKUNMASK_ENTRY routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
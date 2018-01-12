---
UID: NC:wdm.PCI_MSIX_SET_ENTRY
title: PCI_MSIX_SET_ENTRY
author: windows-driver-content
description: The SetTableEntry routine sets the message ID for a table entry in the MSI-X hardware interrupt table.
old-location: kernel\settableentry.htm
old-project: kernel
ms.assetid: A8F2A43B-CAEF-4EE6-AB3F-1DF5A9D3F7A5
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
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
req.alt-api: SetTableEntry
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DIRQL
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PCI_MSIX_SET_ENTRY callback



## -description
The <i>SetTableEntry</i> routine sets the message ID for a table entry in the MSI-X hardware interrupt table.



## -prototype

````
PCI_MSIX_SET_ENTRY SetTableEntry;

NTSTATUS SetTableEntry(
  _In_ PVOID Context,
  _In_ ULONG TableEntry,
  _In_ ULONG MessageNumber
)
{ ... }
````


## -parameters

### -param Context [in]

A pointer to interface-specific context information.  The caller passes the value that is passed as the <b>Context</b> member of the <a href="..\wdm\ns-wdm-_pci_msix_table_config_interface.md">PCI_MSIX_TABLE_CONFIG_INTERFACE</a> structure for the interface.


### -param TableEntry [in]

The index of the table entry in the MSI-X hardware interrupt table.


### -param MessageNumber [in]

The message ID for the interrupt.  This value is also the index for the interrupt's entry in the <b>MessageInfo</b> member of the <a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">IO_INTERRUPT_MESSAGE_INFO</a> structure that describes the driver's message-signaled interrupts.  The <a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a> function supplies a pointer to this structure.  


## -returns
The <i>SetTableEntry</i> routine might return one of the following NTSTATUS values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The device does not use MSI-X, or the <i>TableEntry</i> or <i>MessageNumber</i> parameters do not correspond to interrupt resources that are assigned to the device. 

 


## -remarks
By default, the operating system assigns the index of the table entry as the message ID for the interrupt.  If there are more table entries than messages, the system sets the remaining table entries to correspond to message zero.  The driver can use the <i>SetTableEntry</i> routine to assign a different message ID.


## -requirements
<table>
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
Version

</th>
<td width="70%">
Available in Windows Vista with Service Pack 1 (SP1), Windows Server 2008, and later versions of the Windows operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DIRQL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">IO_INTERRUPT_MESSAGE_INFO</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioconnectinterruptex.md">IoConnectInterruptEx</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_pci_msix_table_config_interface.md">PCI_MSIX_TABLE_CONFIG_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCI_MSIX_SET_ENTRY routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


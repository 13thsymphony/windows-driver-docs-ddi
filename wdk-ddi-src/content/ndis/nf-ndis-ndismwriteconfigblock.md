---
UID: NF:ndis.NdisMWriteConfigBlock
title: NdisMWriteConfigBlock function
author: windows-driver-content
description: A miniport driver for a PCI Express (PCIe) Virtual Function (VF) calls the NdisMWriteConfigBlock function to write data to a VF configuration block.
old-location: netvista\ndismwriteconfigblock.htm
old-project: netvista
ms.assetid: de7f651b-9847-41e9-9f52-71c2365bac44
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisMWriteConfigBlock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMWriteConfigBlock
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= APC_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMWriteConfigBlock function



## -description
A miniport driver for a PCI Express (PCIe) Virtual Function (VF) calls the <b>NdisMWriteConfigBlock</b> function to write data to a VF configuration block. Write operations on a VF configuration block are handled by the miniport driver of the network adapter's PCIe Physical Function (PF).



## -syntax

````
NDIS_STATUS NdisMWriteConfigBlock(
  _In_ NDIS_HANDLE NdisMiniportHandle,
  _In_ ULONG       BlockId,
  _In_ PVOID       Buffer,
  _In_ ULONG       Length
);
````


## -parameters

### -param NdisMiniportHandle [in]

The network adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.


### -param BlockId [in]

A ULONG value that specifies the identifier of the configuration block to be written to. This identifier is proprietary to the independent hardware vendor (IHV) and is used only by the miniport drivers for the PF and VF on the network adapter.



### -param Buffer [in]

A pointer to a caller-allocated buffer that contains the configuration data to be written.


### -param Length [in]

The number of bytes to write to the configuration block.


## -returns
<b>NdisMWriteConfigBlock</b> can return one of the following status values.
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The write operation completed successfully.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>The write operation failed.

 


## -remarks
The VF miniport driver  calls <b>NdisMWriteConfigBlock</b> to initiate a backchannel write request of VF configuration data by the PF miniport driver. Once notified of this request, the PF driver writes the data to the specified VF configuration block.

A VF configuration block is used for backchannel communication between the PF and VF miniport drivers. The IHV can define one or more VF configuration blocks for the device. Each VF configuration block has an IHV-defined format, length,  and block ID.

For more information about backchannel communication within the single root I/O virtualization (SR-IOV) interface, see <a href="https://msdn.microsoft.com/66D40452-1286-449E-BD6B-AFAD466E03A1">SR-IOV PF/VF Backchannel Communication</a>.

If an independent hardware vendor (IHV) provides a virtual bus driver (VBD) as part of its SR-IOV <a href="devinst.driver_packages">driver package</a>, its miniport driver must not call <b>NdisMWriteConfigBlock</b>. Instead, the driver must interface with the VBD through a private communication channel, and request that the VBD call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451609">WriteVfConfigBlock</a>. This function is exposed from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451146">GUID_VPCI_INTERFACE_STANDARD</a> interface that is supported by the underlying virtual PCI (VPCI) bus driver.

The VBD that runs in a Hyper-V child partition's guest operating system can query the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451146">GUID_VPCI_INTERFACE_STANDARD</a> interface by issuing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> request to its physical device object (PDO) on the VPCI bus. This request must be made from IRQL = PASSIVE_LEVEL. In this request, the driver must  set the <i>InterfaceType</i> parameter to GUID_VPCI_INTERFACE_STANDARD.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
None supported

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.30 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451146">GUID_VPCI_INTERFACE_STANDARD</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451609">WriteVfConfigBlock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMWriteConfigBlock function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


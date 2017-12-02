---
UID: NF.ndis.NdisMQueryProbedBars
title: NdisMQueryProbedBars
author: windows-driver-content
description: A miniport driver calls the NdisMQueryProbedBars function to obtain the values of a network adapter's PCI Express (PCIe) Base Address Registers (BARs).
old-location: netvista\ndismqueryprobedbars.htm
old-project: netvista
ms.assetid: 39deba08-3ff0-4037-b530-0cb4a01fc758
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NdisMQueryProbedBars
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMQueryProbedBars
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
req.irql: PASSIVE_LEVEL
req.iface: 
---

# NdisMQueryProbedBars function



## -description
<p>A miniport driver calls the <b>NdisMQueryProbedBars</b> function to obtain the values of a network adapter's PCI Express (PCIe) Base Address Registers (BARs). This function returns the BAR values that were reported by the network adapter following a query performed by the PCI bus driver. This query determines the memory or I/O address space that is required by the network adapter. </p>


## -syntax

````
NDIS_STATUS NdisMQueryProbedBars(
  _In_  NDIS_HANDLE NdisMiniportHandle,
  _Out_ PULONG      BaseRegisterValues
);
````


## -parameters
<dl>

### -param NdisMiniportHandle [in]

<dd>
<p>The network adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of 
     <a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>.</p>
</dd>

### -param BaseRegisterValues [out]

<dd>
<p>A pointer to an array of ULONG values. The array  contains a ULONG value for each BAR of the PCIe network adapter.</p>
<div class="alert"><b>Note</b>  <b>NdisMQueryProbedBars</b> returns a maximum of PCI_TYPE0_ADDRESSES values within this array.
</div>
<div> </div>
</dd>
</dl>

## -returns
<p><b>NdisMQueryProbedBars</b> can return one of the following status values.</p><dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><p>The query operation completed successfully.</p><dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl><p>The query operation failed.</p>

<p> </p>

## -remarks
<p>The PCI bus driver, which runs in the management operating system  of the Hyper-V parent partition, queries the memory or I/O address space requirements of each  PCI Base Address Register (BAR) of the network adapter. The PCI bus driver performs this query when it first detects the adapter on the bus. </p>

<p>Through this PCI BAR query, the PCI bus driver determines the following:</p>

<p>Whether a PCI BAR is supported by the network adapter.</p>

<p>If a BAR is supported, how much memory or I/O
address space is required for the BAR.</p>

<p>The virtual PCI (VPCI) bus driver runs in the guest operating system of a Hyper-V child partition. When a PCI Express (PCIe) Virtual Function (VF) is attached to the child partition, the VPCI bus driver will expose a virtual network adapter for the VF (<i>VF network adapter</i>). Before it does this, the VPCI bus driver must perform a PCI BAR query to determine the required memory or address space that is required by the VF network adapter.</p>

<p>Because access to the PCI configuration space is a privileged operation, it can only be performed by components that run in the management operating system of a Hyper-V parent partition. When the VPCI bus driver queries the PCI BARs, NDIS issues an object identifier (OID) query request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451870">OID_SRIOV_PROBED_BARS</a> to the PF miniport driver. The results returned by this OID query request are forwarded to the VPCI bus driver so that it can determine how much memory address space would be needed by the VF network adapter. </p>

<p>During the handling of this OID request, the driver can call <b>NdisMQueryProbedBars</b> to obtain the values returned from the BAR query performed by the PCI driver.
</p>

<p>For more information on how to query PCI BAR registers for a VF, see <a href="netvista.querying_the_pci_base_address_registers_of_a_virtual_function">Querying the PCI Base Address Registers of a Virtual Function</a>.</p>

<p>For more information about the SR-IOV interface, see 	<a href="netvista.overview_of_single_root_i_o_virtualization__sr-iov_">Overview of Single Root I/O Virtualization (SR-IOV)</a>.</p>

<p>If an independent hardware vendor (IHV) provides a virtual bus driver (VBD) as part of its SR-IOV <a href="devinst.driver_packages">driver package</a>, its miniport driver must not call <b>NdisMQueryProbedBars</b>. Instead, the driver must interface with the VBD through a private communication channel, and request that the VBD call <a href="..\wdm\nc-wdm-get-virtual-function-probed-bars.md">GetVirtualFunctionProbedBars</a>. This function is exposed from the <a href="kernel.guid_pci_virtualization_interface">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface that is supported by the underlying PCI bus driver.</p>

<p>The VBD that runs in the Hyper-V parent partition's management operating system can query the <a href="kernel.guid_pci_virtualization_interface">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface by issuing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> request to its physical device object (PDO) on the PCI bus. This request must be made from IRQL = PASSIVE_LEVEL. In this request, the driver must  set the <i>InterfaceType</i> parameter to GUID_PCI_VIRTUALIZATION_INTERFACE.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.30 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="..\wdm\nc-wdm-get-virtual-function-probed-bars.md">GetVirtualFunctionProbedBars</a>
</dt>
<dt>
<a href="kernel.guid_pci_virtualization_interface">GUID_PCI_VIRTUALIZATION_INTERFACE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451870">OID_SRIOV_PROBED_BARS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMQueryProbedBars function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

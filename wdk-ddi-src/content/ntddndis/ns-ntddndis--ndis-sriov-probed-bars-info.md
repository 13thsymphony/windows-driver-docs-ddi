---
UID: NS.ntddndis._NDIS_SRIOV_PROBED_BARS_INFO
title: NDIS_SRIOV_PROBED_BARS_INFO
author: windows-driver-content
description: The NDIS_SRIOV_PROBED_BARS_INFO structure specifies the values of the PCI Express (PCIe) Base Address Registers (BARs) of a network adapter that supports the single root I/O virtualization (SR-IOV) interface.
old-location: netvista\ndis_sriov_probed_bars_info.htm
old-project: netvista
ms.assetid: 9f37d9e7-ae8b-448e-a535-f34b01c2bf8a
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NDIS_SRIOV_PROBED_BARS_INFO, NDIS_SRIOV_PROBED_BARS_INFO, *PNDIS_SRIOV_PROBED_BARS_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_SRIOV_PROBED_BARS_INFO
req.alt-loc: Ntddndis.h
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
req.iface: 
---

# NDIS_SRIOV_PROBED_BARS_INFO structure



## -description
<p>
<p>The <b>NDIS_SRIOV_PROBED_BARS_INFO</b> structure specifies the values of the PCI Express (PCIe) Base Address Registers (BARs) of a network adapter that supports the single root I/O virtualization (SR-IOV) interface. 
 </p>
<p>The values specified by the <b>NDIS_SRIOV_PROBED_BARS_INFO</b> structure are those that were reported by the adapter following a query that was performed by the PCI bus driver. This query determines the memory or I/O address space that is required by the device.

</p>
</p>
<p>The <b>NDIS_SRIOV_PROBED_BARS_INFO</b> structure specifies the values of the PCI Express (PCIe) Base Address Registers (BARs) of a network adapter that supports the single root I/O virtualization (SR-IOV) interface. 
 </p>
<p>The values specified by the <b>NDIS_SRIOV_PROBED_BARS_INFO</b> structure are those that were reported by the adapter following a query that was performed by the PCI bus driver. This query determines the memory or I/O address space that is required by the device.

</p>


## -syntax

````
typedef struct _NDIS_SRIOV_PROBED_BARS_INFO {
  NDIS_OBJECT_HEADER Header;
  ULONG              BaseRegisterValuesOffset;
} NDIS_SRIOV_PROBED_BARS_INFO, *PNDIS_SRIOV_PROBED_BARS_INFO;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>The type, revision, and size of the <b>NDIS_SRIOV_PROBED_BARS_INFO</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a> structure.</p>
<p>The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_PROBED_BARS_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: </p>
<p></p>
<dl>

### -field <a id="NDIS_SRIOV_PROBED_BARS_INFO_REVISION_1"></a><a id="ndis_sriov_probed_bars_info_revision_1"></a>NDIS_SRIOV_PROBED_BARS_INFO_REVISION_1

<dd>
<p>Original version for NDIS 6.30 and later.</p>
<p>Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_PROBED_BARS_INFO_REVISION_1.</p>
</dd>
</dl>
</dd>

### -field <b>BaseRegisterValuesOffset</b>

<dd>
<p>A ULONG value that contains the offset, in units of bytes, from the beginning of this structure to an array of ULONG values. The array  contains a ULONG value for each BAR of the PCIe network adapter.</p>
<p>The maximum number of elements within this array is PCI_TYPE0_ADDRESSES.</p>
<p>For more information, see the Remarks section.</p>
</dd>
</dl>

## -remarks
<p>The <b>NDIS_SRIOV_PROBED_BARS_INFO</b> structure is used in OID query requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451870">OID_SRIOV_PROBED_BARS</a>.  Each
    element in the array that follows the <b>NDIS_SRIOV_PROBED_BARS_INFO</b> structure contains a ULONG value for a BAR of the network adapter. The offsets of the elements within the array must match the offsets of the BARs on the adapter.</p>

<p>For more information about the base address registers of a PCI device, see the <i>PCI Local Bus Specification</i>.</p>

## -requirements
<table>
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
<dt>Ntddndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451870">OID_SRIOV_PROBED_BARS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SRIOV_PROBED_BARS_INFO structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

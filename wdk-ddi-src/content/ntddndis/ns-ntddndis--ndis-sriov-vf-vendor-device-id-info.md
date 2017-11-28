---
UID: NS.ntddndis._NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO
title: NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO
author: windows-driver-content
description: The NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO structure specifies the PCI Express (PCIe) vendor and device identifiers (IDs) for a PCIe Virtual Function (VF) network adapter.
old-location: netvista\ndis_sriov_vf_vendor_device_id_info.htm
old-project: netvista
ms.assetid: ecf9f34a-ba05-4ad1-990c-b13d53fd78bb
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO, NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO, *PNDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO
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
req.alt-api: NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO
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

# NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO structure



## -description
<p>
<p>The <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure specifies the PCI Express (PCIe) vendor and device identifiers (IDs) for a PCIe Virtual Function (VF) network adapter. This virtual adapter is exposed within the guest operating system that runs in a Hyper-V child partition. </p>
<p>The <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure contains information that is used for PnP device enumeration in the guest operating system.</p>
</p>
<p>The <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure specifies the PCI Express (PCIe) vendor and device identifiers (IDs) for a PCIe Virtual Function (VF) network adapter. This virtual adapter is exposed within the guest operating system that runs in a Hyper-V child partition. </p>
<p>The <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure contains information that is used for PnP device enumeration in the guest operating system.</p>


## -syntax

````
typedef struct _NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO {
  NDIS_OBJECT_HEADER     Header;
  NDIS_SRIOV_FUNCTION_ID VFId;
  USHORT                 VendorId;
  USHORT                 DeviceId;
} NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO, *PNDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>The type, revision, and size of the <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.</p>
<p>The driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: </p>
<p></p>
<dl>

### -field <a id="NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO_REVISION_1"></a><a id="ndis_sriov_vf_vendor_device_id_info_revision_1"></a>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO_REVISION_1

<dd>
<p>Original version for NDIS 6.30 and later.</p>
<p>Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_VENDOR_DEVICE_ID_INFO_REVISION_1.</p>
</dd>
</dl>
</dd>

### -field <b>VFId</b>

<dd>
<p>An NDIS_SRIOV_FUNCTION_ID value that specifies the unique identifier of the VF network adapter.</p>
<div class="alert"><b>Note</b>  The VF with the specified NDIS_SRIOV_FUNCTION_ID value must have resources that were previously allocated through an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>.

</div>
<div> </div>
</dd>

### -field <b>VendorId</b>

<dd>
<p>A USHORT value that uniquely identifies the vendor of the VF network adapter.</p>
</dd>

### -field <b>DeviceId</b>

<dd>
<p>A USHORT value that uniquely identifies the device type of the VF network adapter.</p>
</dd>
</dl>

## -remarks
<p> The <b>NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO</b> structure is used in the OID method requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451913">OID_SRIOV_VF_VENDOR_DEVICE_ID</a>. </p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451913">OID_SRIOV_VF_VENDOR_DEVICE_ID</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SRIOV_VF_VENDOR_DEVICE_ID_INFO structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

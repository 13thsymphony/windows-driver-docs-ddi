---
UID: NS.ntddndis._NDIS_SRIOV_CAPABILITIES
title: NDIS_SRIOV_CAPABILITIES
author: windows-driver-content
description: The NDIS_SRIOV_CAPABILITIES structure specifies the single root I/O virtualization (SR-IOV) capabilities of the network adapter.
old-location: netvista\ndis_sriov_capabilities.htm
ms.assetid: 57cf980c-4477-4c12-8d82-7a8df8b2922f
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: netvista
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_SRIOV_CAPABILITIES
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
ms.keywords: NDIS_SRIOV_CAPABILITIES, NDIS_SRIOV_CAPABILITIES, *PNDIS_SRIOV_CAPABILITIES
req.iface: 
---

# NDIS_SRIOV_CAPABILITIES structure



## -description
<p>The <b>NDIS_SRIOV_CAPABILITIES</b> structure specifies the single root I/O virtualization (SR-IOV) capabilities of the network adapter.</p>


## -syntax

````
typedef struct _NDIS_SRIOV_CAPABILITIES {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  ULONG              SriovCapabilities;
} NDIS_SRIOV_CAPABILITIES, *PNDIS_SRIOV_CAPABILITIES;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>The type, revision, and size of the <b>NDIS_SRIOV_CAPABILITIES</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.</p>
<p>The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_CAPABILITIES</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: </p>
<p></p>
<dl>

### -field <a id="NDIS_SRIOV_CAPABILITIES__REVISION_1"></a><a id="ndis_sriov_capabilities__revision_1"></a>NDIS_SRIOV_CAPABILITIES _REVISION_1

<dd>
<p>Original version for NDIS 6.30 and later.</p>
<p>Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_CAPABILITIES _REVISION_1.</p>
</dd>
</dl>
</dd>

### -field <b>Flags</b>

<dd>
<p>A ULONG value that contains a bitwise OR of flags. This member is reserved for NDIS</p>
</dd>

### -field <b>SriovCapabilities</b>

<dd>
<p>A ULONG value that contains a bitwise OR of the following flags:</p>
<p></p>
<dl>

### -field <a id="NDIS_SRIOV_CAPS_SRIOV_SUPPORTED"></a><a id="ndis_sriov_caps_sriov_supported"></a>NDIS_SRIOV_CAPS_SRIOV_SUPPORTED

<dd>
<p>Specifies that the network adapter supports SR-IOV functionality. </p>
<div class="alert"><b>Note</b>  This flag must only be set by the miniport driver for the PCI Express (PCIe) Physical Function (PF) of the network adapter. This driver runs in the management operating system. This operating system runs in the Hyper-V parent partition.</div>
<div> </div>
</dd>

### -field <a id="NDIS_SRIOV_CAPS_PF_MINIPORT"></a><a id="ndis_sriov_caps_pf_miniport"></a>NDIS_SRIOV_CAPS_PF_MINIPORT

<dd>
<p>Specifies that this is a PF  miniport driver. </p>
</dd>

### -field <a id="NDIS_SRIOV_CAPS_VF_MINIPORT"></a><a id="ndis_sriov_caps_vf_miniport"></a>NDIS_SRIOV_CAPS_VF_MINIPORT

<dd>
<p>Specifies that this is a PCIe  Virtual Function (VF) miniport driver. </p>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p> The miniport driver uses the <b>NDIS_SRIOV_CAPABILITIES</b> structure to report its SR-IOV capabilities in the following ways:</p>

<p>The  miniport driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a> function from its <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function and sets the <i>MiniportAttributes</i> parameter to a pointer to an  <a href="https://msdn.microsoft.com/library/windows/hardware/ff565924">NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a> structure. The driver advertises SR-IOV support by formatting the 
<b>HardwareSriovCapabilities</b> and <b>CurrentSriovCapabilities</b> members as <b>NDIS_SRIOV_CAPABILITIES</b> structures.</p>

<p>NDIS passes the network adapter's SR-IOV capabilities to overlying drivers that bind to the network adapter in the following way:</p>

<p>When NDIS calls an overlying filter driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function, NDIS passes the network adapter's SR-IOV capabilities through the <i>AttachParameters</i> parameter.  This parameter contains a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff565481">NDIS_FILTER_ATTACH_PARAMETERS</a> structure. The <b>SriovCapabilities</b>  member of this structure contains a pointer to an <b>NDIS_SRIOV_CAPABILITIES</b> structure.</p>

<p>When NDIS calls an overlying protocol driver's <a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>
 function, NDIS passes the network adapter's SR-IOV capabilities through the <i>BindParameters</i> parameter.  This parameter contains a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff565481">NDIS_FILTER_ATTACH_PARAMETERS</a> structure. The <b>SriovCapabilities</b>  member of this structure contains a pointer to an <b>NDIS_SRIOV_CAPABILITIES</b> structure.</p>

<p>For more information on how to report the SR-IOV capabilities of a network adapter, see <a href="NULL">Determining SR-IOV Capabilities</a>.</p>

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
<a href="netvista.miniportinitializeex_requirements">MiniportInitializeEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564832">NDIS_BIND_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565481">NDIS_FILTER_ATTACH_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565924">NDIS_MINIPORT_ADAPTER_HARDWARE_ASSIST_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451859">OID_SRIOV_CURRENT_CAPABILITIES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451862">OID_SRIOV_HARDWARE_CAPABILITIES</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SRIOV_CAPABILITIES structure%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

---
UID: NC.wdm.GET_VIRTUAL_DEVICE_RESOURCES
title: GET_VIRTUAL_DEVICE_RESOURCES
author: windows-driver-content
description: The GetResources routine returns the resources that the PCI Express (PCIe) physical function (PF) requires in order to enable virtualization on a device that supports the single root I/O virtualization (SR-IOV) interface.
old-location: kernel\getresources.htm
old-project: kernel
ms.assetid: 4F29E9BD-F534-45EC-99C3-F006A0E03B31
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, PWDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2012 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetResources
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
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# GET_VIRTUAL_DEVICE_RESOURCES callback



## -description
The <i>GetResources</i> routine returns the resources that the PCI Express (PCIe) physical function (PF) requires in order to enable virtualization on a device that supports the single root I/O virtualization (SR-IOV) interface.



## -prototype

````
GET_VIRTUAL_DEVICE_RESOURCES GetResources;

VOID GetResources(
  _Inout_ PVOID  Context,
  _Out_   PUINT8 CapturedBusNumbers
)
{ ... }
````


## -parameters

### -param Context [in, out]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="kernel.pci_virtualization_interface">PCI_VIRTUALIZATION_INTERFACE</a> structure for the interface.


### -param CapturedBusNumbers [out]

A pointer to a caller-supplied variable in which this routine returns a UINT8 value. This value specifies the number of PCIe buses that have been captured for use by the SR-IOV PF of the device.


## -returns
This routine does not return a value.


## -remarks
A PCIe device typically consumes resources on a single PCI bus.  The PCI driver assigns a device to a PCI bus by writing the bus number into the Secondary Bus Number register and Subordinate Bus Number register in the upstream bridge port. This port is a PCI-to-PCI bridge within a PCIe root port or a PCIe switch port.

A device that supports the SR-IOV interface may create more virtual functions than can be accommodated on the PCI bus on which the device is connected.  In these situations, the upstream bridge port must be configured to capture one or more unused PCI buses.  This is done by writing a larger value to the port's Subordinate Bus Number register.

A device that supports the SR-IOV interface  must capture PCI buses if at least one of the following is true:
<ul>
<li>
The device has more than eight total functions (PFs and VFs) and the device does not support the Alternative Routing Interpretation (ARI) option of the PCI Express 3.0 specification.


</li>
<li>
The device supports ARI and has more than eight total functions, but the upstream bridge port does not support ARI.


</li>
<li>
The device supports ARI and has more than 256 functions, and the upstream bridge port does  support ARI.

</li>
</ul>
<div class="alert"><b>Note</b>  Regardless of ARI support, each captured bus can support 256 functions.</div>
<div> </div>


The device has more than eight total functions (PFs and VFs) and the device does not support the Alternative Routing Interpretation (ARI) option of the PCI Express 3.0 specification.


The device supports ARI and has more than eight total functions, but the upstream bridge port does not support ARI.


The device supports ARI and has more than 256 functions, and the upstream bridge port does  support ARI.

If the device needs more PCIe Requestor IDs (RIDs) in order to enable all  of its VFs, the PCI bus driver does the following:<ol>
<li>
Writes the device’s bus number into the PCIe Secondary Bus Number register.

</li>
<li>
Writes a value that is larger than the device’s bus number into the PCIe Subordinate Bus Number register.

</li>
</ol>The difference between these two register values represents the number of captured bus numbers.



Writes the device’s bus number into the PCIe Secondary Bus Number register.

Writes a value that is larger than the device’s bus number into the PCIe Subordinate Bus Number register.

The <i>GetResources</i> routine is provided by the <a href="kernel.guid_pci_virtualization_interface">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface.


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
Supported in Windows Server 2012 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="kernel.guid_pci_virtualization_interface">GUID_PCI_VIRTUALIZATION_INTERFACE</a>
</dt>
<dt>
<a href="kernel.pci_virtualization_interface">PCI_VIRTUALIZATION_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20GET_VIRTUAL_DEVICE_RESOURCES routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


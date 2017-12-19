---
UID: NC.wdm.GET_VIRTUAL_DEVICE_DATA
title: GET_VIRTUAL_DEVICE_DATA
author: windows-driver-content
description: The GetVirtualFunctionData routine reads data from the PCI Express (PCIe) configuration space of a virtual function (VF) on a device that supports the single root I/O virtualization (SR-IOV) interface.
old-location: kernel\getvirtualfunctiondata.htm
old-project: kernel
ms.assetid: 2DE7417D-C616-4D1F-835D-29F477410F1E
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
req.alt-api: GetVirtualFunctionData
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
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# GET_VIRTUAL_DEVICE_DATA callback



## -description
The  <i>GetVirtualFunctionData</i> routine reads data from the PCI Express (PCIe) configuration space of a virtual function (VF) on a device that supports the single root I/O virtualization (SR-IOV) interface.



## -prototype

````
GET_VIRTUAL_DEVICE_DATA GetVirtualFunctionData;

ULONG GetVirtualFunctionData(
  _Inout_ PVOID  Context,
  _In_    USHORT VirtualFunction,
  _Out_   PVOID  Buffer,
  _In_    ULONG  Offset,
  _In_    ULONG  Length
)
{ ... }
````


## -parameters

### -param Context [in, out]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="kernel.pci_virtualization_interface">PCI_VIRTUALIZATION_INTERFACE</a> structure for the interface.


### -param VirtualFunction [in]

A zero-based value that specifies the VF on the device from which data is to be read.


### -param Buffer [out]

A pointer to the buffer that contains the configuration information read from the PCIe configuration space of the VF.


### -param Offset [in]

The offset into the PCIe configuration space data of the VF. This member specifies where this read operation begins.


### -param Length [in]

The length, in bytes, of the data to be read. 


## -returns
The 
      <i>GetVirtualFunctionData</i> routine returns the length, in bytes, of the PCIe configuration data that was read after a successful read operation. If the read operation is unsuccessful, the routine returns zero. 


## -remarks
The <i>GetVirtualFunctionData</i> routine resembles the <a href="..\wdm\nc-wdm-get_set_device_data.md">GetBusData</a> routine, except that it reads PCIe configuration data from a VF instead of from a device's physical function (PF).

The <i>GetVirtualFunctionData</i> routine is provided by the <a href="kernel.guid_pci_virtualization_interface">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface. The <a href="..\wdm\nc-wdm-get_set_device_data.md">GetBusData</a> routine is provided by the <a href="kernel.guid_bus_interface_standard">GUID_BUS_INTERFACE_STANDARD</a> interface.


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
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="..\wdm\nc-wdm-get_set_device_data.md">GetBusData</a>
</dt>
<dt>
<a href="kernel.guid_bus_interface_standard">GUID_BUS_INTERFACE_STANDARD</a>
</dt>
<dt>
<a href="kernel.guid_pci_virtualization_interface">GUID_PCI_VIRTUALIZATION_INTERFACE</a>
</dt>
<dt>
<a href="kernel.pci_virtualization_interface">PCI_VIRTUALIZATION_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20GET_VIRTUAL_DEVICE_DATA routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


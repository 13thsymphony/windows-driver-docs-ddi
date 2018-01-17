---
UID: NC:wdm.GET_VIRTUAL_FUNCTION_PROBED_BARS
title: GET_VIRTUAL_FUNCTION_PROBED_BARS function
author: windows-driver-content
description: The GetVirtualFunctionProbedBars routine returns the values of the PCI Express (PCIe) Base Address Registers (BARs) of a device that supports the single root I/O virtualization (SR-IOV) interface.
old-location: pci\getvirtualfunctionprobedbars.htm
old-project: PCI
ms.assetid: 02A86A3E-D543-4F0F-9985-7D42F381F8F1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: GET_VIRTUAL_FUNCTION_PROBED_BARS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2012 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetVirtualFunctionProbedBars
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
req.typenames: *PWDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# GET_VIRTUAL_FUNCTION_PROBED_BARS function



## -description
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> routine returns the values of the PCI Express (PCIe) Base Address Registers (BARs) of a device that supports the single root I/O virtualization (SR-IOV) interface. 


<a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> returns the BAR values that were reported by the device after a query that was performed by the PCI bus driver. This query determines the memory or I/O address space that is required by the device.



## -syntax

````
GET_VIRTUAL_FUNCTION_PROBED_BARS GetVirtualFunctionProbedBars;

NTSTATUS GetVirtualFunctionProbedBars(
  _Inout_ PVOID  Context,
  _Out_   PULONG BaseRegisterValues
)
{ ... }
````


## -parameters

### -param Context [in, out]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406642">PCI_VIRTUALIZATION_INTERFACE</a> structure for the interface.


### -param BaseRegisterValues [out]

A pointer to an array of ULONG values. The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> routine returns a value for each BAR of the device.

<div class="alert"><b>Note</b>  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> returns a maximum of <b>PCI_TYPE0_ADDRESSES</b> values within this array.
</div>
<div> </div>

## -returns
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> routine returns one of the following NTSTATUS values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>The device does not support the SR-IOV interface.

 


## -remarks
The PCI bus driver. which runs in the management operating system  of the Hyper-V parent partition, queries the memory or I/O address space requirements of each  BAR of the device. The PCI bus driver performs this query when the it first detects the adapter on the bus. 

Through this BAR query, the PCI bus driver determines the following:

Whether a BAR is supported by the device.

If a BAR is supported, how much memory or I/O
address space is required for the BAR.

The PCI driver performs this BAR query as follows:

The PCI bus driver writes 0xFFFFFFFF to a BAR.

The PCI bus driver reads the BAR to determine the memory or address space that the device requires. A value of zero indicates that the device does not support the BAR.

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> routine is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface.

The following notes apply to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> routine:

The SR-IOV interface does not require that the BARs of a PCIe VF comply with the protocol for determining the size of the memory block or I/O address space of a BAR. Therefore, the virtual PCI (VPCI) driver, which runs in the guest operating system, determines the size by using the equivalent size from the BARs on the physical device. The VPCI driver obtains this information by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> routine.


	The VPCI driver requires the size of the memory or I/O
address space for each BAR after the physical device has started. At that point, the PCI driver cannot perform a BAR query  on the device without altering the current value of the BAR. Therefore, when the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451140">GetVirtualFunctionProbedBars</a> routine is called by the VPCI driver, the PCI driver returns the BAR information that it obtained during the BAR query. The PCI driver performed this query when the device was first detected on the bus.


## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406642">PCI_VIRTUALIZATION_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\pci]:%20GET_VIRTUAL_FUNCTION_PROBED_BARS routine%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


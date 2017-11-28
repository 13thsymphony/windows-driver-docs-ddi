---
UID: NI.pcivirt.IOCTL_SRIOV_PROXY_QUERY_LUID
title: IOCTL_SRIOV_PROXY_QUERY_LUID
author: windows-driver-content
description: This request supplies the local unique identifier of the SR_IOV device implementing the interface.
old-location: pci\ioctl-sriov-proxy-query-luid.htm
old-project: PCI
ms.assetid: 9f10ed34-f718-4c35-9b6f-29554bf30a0f
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PARCLASS_INFORMATION, PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: pcivirt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_SRIOV_PROXY_QUERY_LUID
req.alt-loc: Pcivirt.h
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

# IOCTL_SRIOV_PROXY_QUERY_LUID IOCTL



## -description
<p>This request supplies the local unique
identifier of the SR_IOV device implementing the interface.</p>


## -syntax

````

   
    case IOCTL_SRIOV_PROXY_QUERY_LUID:

        status = WdfRequestRetrieveOutputBuffer(Request,
                                                sizeof(LUID),
                                                &luid,
                                                NULL);
        if (!NT_SUCCESS(status))
        {
            break;
        }

        RtlCopyMemory(luid, &deviceContext->Luid, sizeof(LUID));
        WdfRequestSetInformation(Request, sizeof(LUID));
        status = STATUS_SUCCESS;
        break;

````


## -ioctlparameters

### -input-buffer

<text></text>

### -input-buffer-length

<text></text>

### -output-buffer
<p>A pointer to a <a href="buses._sriov_proxy_query_luid_output">SRIOV_PROXY_QUERY_LUID_OUTPUT</a> structure that is filled with the identifier.</p>

<p>A pointer to a <a href="buses._sriov_proxy_query_luid_output">SRIOV_PROXY_QUERY_LUID_OUTPUT</a> structure that is filled with the identifier.</p>

### -output-buffer-length
<p>The size of the <a href="buses._sriov_proxy_query_luid_output">SRIOV_PROXY_QUERY_LUID_OUTPUT</a> structure.</p>

<p>The size of the <a href="buses._sriov_proxy_query_luid_output">SRIOV_PROXY_QUERY_LUID_OUTPUT</a> structure.</p>

<p>The size of the <a href="buses._sriov_proxy_query_luid_output">SRIOV_PROXY_QUERY_LUID_OUTPUT</a> structure.</p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

## -remarks
<p>This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.</p>

<p>This IOCTL request originates in the user mode and  is handled by the physical function (PF) driver in order to supply the local unique
identifier of the physical device.  This request is only required for SR-IOV devices doing direct assignment. </p>

<p>Before sending this request, the user mode application must obtain a handle to the PCI Express SR-IOV device by querying for GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.</p>

<p>In this example, the PF driver generates a unique identifier by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff566415">ZwAllocateLocallyUniqueId</a>  and stores it in the device context. </p>

<p>This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.</p>

<p>This IOCTL request originates in the user mode and  is handled by the physical function (PF) driver in order to supply the local unique
identifier of the physical device.  This request is only required for SR-IOV devices doing direct assignment. </p>

<p>Before sending this request, the user mode application must obtain a handle to the PCI Express SR-IOV device by querying for GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.</p>

<p>In this example, the PF driver generates a unique identifier by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff566415">ZwAllocateLocallyUniqueId</a>  and stores it in the device context. </p>

<p>This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.</p>

<p>This IOCTL request originates in the user mode and  is handled by the physical function (PF) driver in order to supply the local unique
identifier of the physical device.  This request is only required for SR-IOV devices doing direct assignment. </p>

<p>Before sending this request, the user mode application must obtain a handle to the PCI Express SR-IOV device by querying for GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.</p>

<p>In this example, the PF driver generates a unique identifier by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff566415">ZwAllocateLocallyUniqueId</a>  and stores it in the device context. </p>

<p>This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.</p>

<p>This IOCTL request originates in the user mode and  is handled by the physical function (PF) driver in order to supply the local unique
identifier of the physical device.  This request is only required for SR-IOV devices doing direct assignment. </p>

<p>Before sending this request, the user mode application must obtain a handle to the PCI Express SR-IOV device by querying for GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.</p>

<p>In this example, the PF driver generates a unique identifier by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff566415">ZwAllocateLocallyUniqueId</a>  and stores it in the device context. </p>

<p>This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.</p>

<p>This IOCTL request originates in the user mode and  is handled by the physical function (PF) driver in order to supply the local unique
identifier of the physical device.  This request is only required for SR-IOV devices doing direct assignment. </p>

<p>Before sending this request, the user mode application must obtain a handle to the PCI Express SR-IOV device by querying for GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.</p>

<p>In this example, the PF driver generates a unique identifier by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff566415">ZwAllocateLocallyUniqueId</a>  and stores it in the device context. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Pcivirt.h</dt>
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
<dt>
<a href="buses._sriov_proxy_query_luid_output">SRIOV_PROXY_QUERY_LUID_OUTPUT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20IOCTL_SRIOV_PROXY_QUERY_LUID control code%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

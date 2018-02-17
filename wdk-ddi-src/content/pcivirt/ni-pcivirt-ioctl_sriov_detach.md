---
UID: NI:pcivirt.IOCTL_SRIOV_DETACH
title: IOCTL_SRIOV_DETACH
author: windows-driver-content
description: The request indicates that the virtualization stack wants to unregister for Plug and Play events (previously registered through the IOCTL_SRIOV_ATTACH request).
old-location: pci\ioctl-sriov-detach.htm
old-project: PCI
ms.assetid: 8ede4a48-317b-46be-834a-a67b638b28c0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PCI.ioctl-sriov-detach, IOCTL_SRIOV_DETACH control code [Buses], IOCTL_SRIOV_DETACH, pcivirt/IOCTL_SRIOV_DETACH
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Pcivirt.h
apiname:
-	IOCTL_SRIOV_DETACH
product: Windows
targetos: Windows
req.typenames: "*PSRIOV_PF_EVENT, SRIOV_PF_EVENT"
---

# IOCTL_SRIOV_DETACH IOCTL
The  request indicates that the virtualization stack wants to unregister for Plug and Play events (previously registered through the <a href="https://msdn.microsoft.com/c1129d60-eeb0-4c90-b181-365f3379d89e">IOCTL_SRIOV_ATTACH</a> request).

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<text></text>

### Input Buffer Length
<text></text>

### Output Buffer
<text></text>

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.

## Remarks
This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.

From here on, the PF should not expect to receive  <a href="https://msdn.microsoft.com/5299ec17-1fcb-4449-9ec4-73a4d818df0d">IOCTL_SRIOV_EVENT_COMPLETE</a> and <a href="https://msdn.microsoft.com/3f2d67e0-abab-40a1-b4a9-cb65e81884e9">IOCTL_SRIOV_NOTIFICATION</a> requests.


The driver that must stop waiting for <a href="https://msdn.microsoft.com/5299ec17-1fcb-4449-9ec4-73a4d818df0d">IOCTL_SRIOV_EVENT_COMPLETE</a>.
If the driver is currently waiting it should stop waiting and continue 
 processing Plug and Play IRPs. 

In this example handling of the IOCTL_SRIOV_DETACH request, the PF driver maintains PnP states in its device context. The deviceContext-&gt;PnpRebalancing is set to TRUE, when the driver receives <a href="https://msdn.microsoft.com/library/windows/hardware/ff551725">IRP_MN_QUERY_STOP_DEVICE</a> and set to FALSE when it receives IRP_MN_START_DEVICE.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>    case IOCTL_SRIOV_DETACH:

        WdfWaitLockAcquire(deviceContext-&gt;PnpStateLock, NULL);

        deviceContext-&gt;PnpVspAttached = FALSE;

        if (deviceContext-&gt;PnpRebalancing != FALSE)
        {
            //
            // Any new client (VSP state machine) will not know about
            // the current rebalance is it should block attach until
            // rebalance is over.
            //

    								deviceContext&gt;PnpSafeToAttach = FALSE;
    								KeClearEvent(&amp;deviceContext&gt;PnpSafeEvent);

        }

        //
        // Unblock the PnP thread if it waiting for an IO control from the
        // client as the client just detached.
        //
        deviceContext-&gt;PnpEventStatus = STATUS_SUCCESS;
        KeSetEvent(&amp;deviceContext-&gt;PnpUnblockEvent, IO_NO_INCREMENT, FALSE);

        WdfWaitLockRelease(deviceContext-&gt;PnpStateLock);

        status = STATUS_SUCCESS;
        break;


</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pcivirt.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/c1129d60-eeb0-4c90-b181-365f3379d89e">IOCTL_SRIOV_ATTACH</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20IOCTL_SRIOV_DETACH control code%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
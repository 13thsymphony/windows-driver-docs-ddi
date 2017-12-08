---
UID: NC.dispmprt.DXGKDDI_GET_CHILD_CONTAINER_ID
title: DXGKDDI_GET_CHILD_CONTAINER_ID
author: windows-driver-content
description: Queries the container ID for the specified target. Implemented by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers.
old-location: display\dxgkddigetchildcontainerid.htm
old-project: display
ms.assetid: e7073fb3-0cb7-425e-9ffb-d7eaa963a70f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _SYMBOL_INFO_EX, SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiGetChildContainerId
req.alt-loc: dispmprt.h
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
---

# DXGKDDI_GET_CHILD_CONTAINER_ID callback



## -description
 Queries the container ID for the specified target. Implemented by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers.


## -prototype

````
PDXGKDDI_GET_CHILD_CONTAINER_ID DxgkDdiGetChildContainerId;

_Check_return_ NTSTATUS* DxgkDdiGetChildContainerId(
  _In_    PVOID                    MiniportDeviceContext,
  _In_    ULONG                    ChildUid,
  _Inout_ PDXGK_CHILD_CONTAINER_ID ContainerId
)
{ ... }
````


## -parameters

### -param MiniportDeviceContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.



### -param ChildUid [in]

A ULONG value that uniquely identifies the child device. The display miniport driver  previously provided this identifier when its  <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a> function was called.

### -param ContainerId [in, out]

A pointer to a <a href="display.dxgk_child_container_id">DXGK_CHILD_CONTAINER_ID</a> structure. For more information, see the Remarks section.

## -returns
Returns one of the following error codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The driver has updated the structure pointed to by the <i>ContainerId</i> parameter with  container ID information obtained from the display hardware.
<dl>
<dt><b>STATUS_MONITOR_NODESCRIPTOR</b></dt>
</dl>The driver has accepted the default container ID information provided in the structure pointed to by  <i>ContainerId</i>.

 

Otherwise the function returns one of the status codes defined in Ntstatus.h.

## -remarks
The operating system calls the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a> function to enumerate the child devices of the display adapter. The operating system then calls the display miniport driver's <a href="display.dxgkddiquerydevicedescriptor">DxgkDdiQueryDeviceDescriptor</a> function for each child device to obtain the  Extended Display Information Data (EDID) for the device. For more information on this procedure, see <a href="https://msdn.microsoft.com/3bec2117-aef4-41fc-b88a-0081c7c9fe3d">Enumerating Child Devices of a Display Adapter</a>.

Based on the device's EDID data, the operating system generates a default container ID for the child device. Then, the operating system calls the display miniport driver's <i>DxgkDdiGetChildContainerId</i> function and passes a pointer to a <a href="display.dxgk_child_container_id">DXGK_CHILD_CONTAINER_ID</a> structure through the <i>ContainerId</i> parameter. The <b>ContainerId</b> member of this structure contains the default container ID for the child display device.

The display miniport driver can either accept the default container ID or set the <b>ContainerId</b> member to a unique identifier for the device before it returns from the call to <i>DxgkDdiGetChildContainerId</i>.

For more information about Container IDs, see <a href="devinst.container_ids">Container IDs</a>.

## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 8
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
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Dispmprt.h (include Dispmprt.h)</dt>
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
<dt>
<a href="display.dxgk_child_container_id">DXGK_CHILD_CONTAINER_ID</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>
</dt>
<dt>
<a href="display.dxgkddiquerydevicedescriptor">DxgkDdiQueryDeviceDescriptor</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PDXGKDDI_GET_CHILD_CONTAINER_ID callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

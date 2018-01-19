---
UID : NE:hwnclx._HWN_CLX_EXPORT_INDEX
title : _HWN_CLX_EXPORT_INDEX
author : windows-driver-content
description : Defines the position for each of the Hardware Notification exports in the export table.
old-location : gpiobtn\_hwn_clx_export_index.htm
old-project : gpiobtn
ms.assetid : fcbbd188-438a-4eaa-8034-67ca52d1fb56
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : _HWN_CLX_EXPORT_INDEX, *PHWN_CLX_EXPORT_INDEX, HWN_CLX_EXPORT_INDEX
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : hwnclx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1709
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : HWN_CLX_EXPORT_INDEX
req.alt-loc : Hwnclx.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : "*PHWN_CLX_EXPORT_INDEX, HWN_CLX_EXPORT_INDEX"
---

# _HWN_CLX_EXPORT_INDEX Enumeration
Defines the position for each of the Hardware Notification exports in the export table.

## Syntax
````
typedef enum _HWN_CLX_EXPORT_INDEX { 
  RegisterClientIndex             = 0x0,
  UnregisterClientIndex,
  AddDevicePreDeviceCreateIndex,
  AddDevicePostDeviceCreateIndex,
  HwNExportLastExportIndex
} HWN_CLX_EXPORT_INDEX;
````

## Constants

<table>

<tr>
<td>AddDevicePostDeviceCreateIndex</td>
<td>Position of the <a href="..\hwnclx\nf-hwnclx-hwnprocessadddevicepostdevicecreate.md">HwNProcessAddDevicePostDeviceCreate</a> hardware notification in the export table.</td>
</tr>

<tr>
<td>AddDevicePreDeviceCreateIndex</td>
<td>Position of the <a href="..\hwnclx\nf-hwnclx-hwnprocessadddevicepredevicecreate.md">HwNProcessAddDevicePreDeviceCreate</a> hardware notification in the export table.</td>
</tr>

<tr>
<td>HwNExportLastExportIndex</td>
<td>Position of the last hardware notification in the export table.</td>
</tr>

<tr>
<td>RegisterClientIndex</td>
<td>Position of the <a href="..\hwnclx\nf-hwnclx-hwnregisterclient.md">HwNRegisterClient</a> hardware notification in the export table.</td>
</tr>

<tr>
<td>UnregisterClientIndex</td>
<td>Position of the <a href="..\hwnclx\nf-hwnclx-hwnunregisterclient.md">HwNUnregisterClient</a> hardware notification in the export table.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hwnclx.h |

## See Also

<dl>
<dt><a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn789335">Hardware notifications support</a></dt>
<dt>
<a href="https://msdn.microsoft.com/405ff6db-9bc0-42f3-a740-49dd3967a8b3">Hardware notifications reference</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [gpiobtn\gpiobtn]:%20HWN_CLX_EXPORT_INDEX enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
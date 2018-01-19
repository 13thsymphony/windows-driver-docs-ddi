---
UID : NE:irb.IDE_CONTROL_ACTION
title : IDE_CONTROL_ACTION
author : windows-driver-content
description : The IDE_CONTROL_ACTION enumeration type indicates the control action to be performed by a IdeHwControl routine.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location : storage\ide_control_action.htm
old-project : storage
ms.assetid : a63d1a2f-d560-492f-9b73-198e42cb4300
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDE_CONTROL_ACTION, IDE_CONTROL_ACTION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : irb.h
req.include-header : Irb.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IDE_CONTROL_ACTION
req.alt-loc : irb.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : IDE_CONTROL_ACTION
---

# IDE_CONTROL_ACTION Enumeration
The IDE_CONTROL_ACTION enumeration type indicates the control action to be performed by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a> routine.

## Syntax
````
typedef enum  { 
  IdeStart          = 0,
  IdeStop           = 1,
  IdePowerUp        = 2,
  IdePowerDown      = 3,
  IdeVendorDefined  = 4
} IDE_CONTROL_ACTION;
````

## Constants

<table>

<tr>
<td>IdePowerDown</td>
<td>Indicates that the miniport driver should power down the channel.</td>
</tr>

<tr>
<td>IdePowerUp</td>
<td>Indicates that the miniport driver should power up the channel.</td>
</tr>

<tr>
<td>IdeStart</td>
<td>Indicates that the miniport driver should start the channel.</td>
</tr>

<tr>
<td>IdeStop</td>
<td>Indicates that the miniport driver should stop the channel.</td>
</tr>

<tr>
<td>IdeVendorDefined</td>
<td>Indicates that the miniport driver should perform a vendor-defined control action.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | irb.h (include Irb.h) |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IDE_CONTROL_ACTION enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID: NC:storport.HW_STATE_CHANGE
title: HW_STATE_CHANGE
author: windows-driver-content
description: A miniport-provided callback that is called after a notification from StorPortStateChangeDetected is processed.
old-location: storage\hwstorstatechange.htm
old-project: storage
ms.assetid: E7E5E26A-B477-453C-AAFC-9B3572F4FC72
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HW_STATE_CHANGE, HwStorStateChange, HwStorStateChange routine [Storage Devices], storage.hwstorstatechange, storport/HwStorStateChange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
req.irql: DISPATCH
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	storport.h
api_name:
-	HwStorStateChange
product: Windows
targetos: Windows
req.typenames: STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER
req.product: Windows 10 or later.
---


# HW_STATE_CHANGE callback function
A miniport-provided callback that is called  after a notification from <a href="https://msdn.microsoft.com/3E5E9C4E-5B82-4656-BDF2-23A9A8D40ADF"> StorPortStateChangeDetected</a> is processed.

## Syntax

```
HW_STATE_CHANGE HwStateChange;

void HwStateChange(
  PVOID HwDeviceExtension,
  PVOID Context,
  SHORT AddressType,
  PVOID Address,
  ULONG Status
)
{...}
```

## Parameters

`HwDeviceExtension`



`Context`

The context supplied as <i>HwStateChangeContext</i> by the miniport in the call to <a href="https://msdn.microsoft.com/3E5E9C4E-5B82-4656-BDF2-23A9A8D40ADF"> StorPortStateChangeDetected</a>.

`AddressType`

The type of the address in <i>Address</i>.

`Address`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451518">STOR_ADDRESS</a> structure for the entity whose state change was processed.

`Status`

The processing status for the state change notification.


## Return Value

None.

## Remarks

The <i>HwStorStateChange</i> is called with the StartIo lock acquired by Storport.

This callback enables miniports to do any additional processing that is needed after hardware addition or removal. If a hardware change occurs on the HBA port or bus, the miniport can call <a href="https://msdn.microsoft.com/3E5E9C4E-5B82-4656-BDF2-23A9A8D40ADF"> StorPortStateChangeDetected</a> to alert the system of the event.

If the value for <i>Status</i> is  &lt; 0x80000000, then the notification processing was successful. Otherwise, the notification process failed.

The name <i>HwStorStateChange</i> is just a placeholder for the miniport function that is pointed to by the <i>HwStateChange</i> parameter of  <a href="https://msdn.microsoft.com/3E5E9C4E-5B82-4656-BDF2-23A9A8D40ADF"> StorPortStateChangeDetected</a>. The actual prototype of this routine is defined in <i>Storport.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
HW_STATE_CHANGE (
    _In_ PVOID HwDeviceExtension,
    _In_opt_ PVOID Context,
    _In_ SHORT AddressType,
    _In_ PVOID Address,
    _In_ ULONG Status
    );</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 8 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **IRQL** | DISPATCH |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451518">STOR_ADDRESS</a>



<a href="https://msdn.microsoft.com/3E5E9C4E-5B82-4656-BDF2-23A9A8D40ADF"> StorPortStateChangeDetected</a>
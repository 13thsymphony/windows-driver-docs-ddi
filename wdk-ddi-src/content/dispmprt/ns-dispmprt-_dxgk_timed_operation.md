---
UID: NS:dispmprt._DXGK_TIMED_OPERATION
title: "_DXGK_TIMED_OPERATION"
author: windows-driver-content
description: The DXGK_TIMED_OPERATION structure describes a timed operation, which is used in the Timed Operation Interface.
old-location: display\dxgk_timed_operation.htm
old-project: display
ms.assetid: 6b377ba5-cd3b-433e-bd9c-315203c3bc69
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PDXGK_TIMED_OPERATION structure pointer [Display Devices], DmStructs_1d58055e-2e81-4a42-b596-390752f0db84.xml, DXGK_TIMED_OPERATION structure [Display Devices], dispmprt/DXGK_TIMED_OPERATION, _DXGK_TIMED_OPERATION, DXGK_TIMED_OPERATION, dispmprt/PDXGK_TIMED_OPERATION, *PDXGK_TIMED_OPERATION, PDXGK_TIMED_OPERATION, display.dxgk_timed_operation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	dispmprt.h
apiname:
-	DXGK_TIMED_OPERATION
product: Windows
targetos: Windows
req.typenames: DXGK_TIMED_OPERATION, *PDXGK_TIMED_OPERATION
---

# _DXGK_TIMED_OPERATION structure
The DXGK_TIMED_OPERATION structure describes a timed operation, which is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570086">Timed Operation Interface</a>.

## Syntax
````
typedef struct _DXGK_TIMED_OPERATION {
  USHORT        Size;
  ULONG_PTR     OwnerTag;
  BOOLEAN       OsHandled;
  BOOLEAN       TimeoutTriggered;
  LARGE_INTEGER Timeout;
  LARGE_INTEGER StartTick;
} DXGK_TIMED_OPERATION, *PDXGK_TIMED_OPERATION;
````

## Members


`OsHandled`

[system] For system use only.

`OwnerTag`

[system] A pointer to the place in the code that started the timed operation.

`Size`

[in] The size, in bytes, of this structure.

`StartTick`

[system] For system use only.

`Timeout`

[system] For system use only.

`TimeoutTriggered`

[out] A Boolean value that specifies whether the time-out was triggered.

## Remarks
Display miniport drivers should not change of rely on members that are marked with the  [system] designation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dispmprt.h (include Dispmprt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570086">Timed Operation Interface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_TIMED_OPERATION structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
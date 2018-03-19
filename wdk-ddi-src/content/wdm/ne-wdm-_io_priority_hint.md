---
UID: NE:wdm._IO_PRIORITY_HINT
title: "_IO_PRIORITY_HINT"
author: windows-driver-content
description: The IO_PRIORITY_HINT enumeration type specifies the priority hint for an IRP.
old-location: kernel\io_priority_hint.htm
old-project: kernel
ms.assetid: 38d19398-b34f-4934-b643-df119ebd9711
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IO_PRIORITY_HINT, IO_PRIORITY_HINT enumeration [Kernel-Mode Driver Architecture], IoPriorityCritical, IoPriorityHigh, IoPriorityLow, IoPriorityNormal, IoPriorityVeryLow, MaxIoPriorityTypes, _IO_PRIORITY_HINT, kernel.io_priority_hint, sysenum_0b8187d9-c762-45d2-a310-294c3c696608.xml, wdm/IO_PRIORITY_HINT, wdm/IoPriorityCritical, wdm/IoPriorityHigh, wdm/IoPriorityLow, wdm/IoPriorityNormal, wdm/IoPriorityVeryLow, wdm/MaxIoPriorityTypes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	IO_PRIORITY_HINT
product: Windows
targetos: Windows
req.typenames: IO_PRIORITY_HINT
req.product: Windows 10 or later.
---

# _IO_PRIORITY_HINT Enumeration
The <b>IO_PRIORITY_HINT</b> enumeration type specifies the <a href="https://msdn.microsoft.com/c34afff2-32f2-451b-ab16-ff048d5c3204">priority hint</a> for an IRP.

## Syntax
````
typedef enum _IO_PRIORITY_HINT { 
  IoPriorityVeryLow   = 0,
  IoPriorityLow       = 1,
  IoPriorityNormal    = 2,
  IoPriorityHigh      = 3,
  IoPriorityCritical  = 4,
  MaxIoPriorityTypes  = 5
} IO_PRIORITY_HINT;
````

## Constants

<table>
            
                <tr>
                    <td>IoPriorityVeryLow</td>
                    <td>Specifies the lowest possible priority hint level. The system uses this value for background I/O operations.</td>
                </tr>
            
                <tr>
                    <td>IoPriorityLow</td>
                    <td>Specifies a low-priority hint level.</td>
                </tr>
            
                <tr>
                    <td>IoPriorityNormal</td>
                    <td>Specifies a normal-priority hint level. This value is the default setting for an IRP.</td>
                </tr>
            
                <tr>
                    <td>IoPriorityHigh</td>
                    <td>Specifies a high-priority hint level. This value is reserved for use by the system.</td>
                </tr>
            
                <tr>
                    <td>IoPriorityCritical</td>
                    <td>Specifies the highest-priority hint level. This value is reserved for use by the system.</td>
                </tr>
            
                <tr>
                    <td>MaxIoPriorityTypes</td>
                    <td>Marks the limit for priority hints. Any priority hint value must be less than <b>MaxIoPriorityTypes</b>.</td>
                </tr>
</table>

## Remarks

For more information about priority hints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565403">Using IRP Priority Hints</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\wdm\nf-wdm-iosetiopriorityhint.md">IoSetIoPriorityHint</a>



<a href="..\wdm\nf-wdm-iogetiopriorityhint.md">IoGetIoPriorityHint</a>
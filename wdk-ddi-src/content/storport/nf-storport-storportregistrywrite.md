---
UID: NF:storport.StorPortRegistryWrite
title: StorPortRegistryWrite function
author: windows-driver-content
description: The StorPortRegistryWrite routine is called by the miniport driver to convert the registry data contained in a specified buffer from ASCII to Unicode and to then write the data to the miniport driver's per-HBA storage area.
old-location: storage\storportregistrywrite.htm
old-project: storage
ms.assetid: 9f149e86-7855-4a10-8e0c-8b1aff261946
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortRegistryWrite, StorPortRegistryWrite routine [Storage Devices], storage.storportregistrywrite, storport/StorPortRegistryWrite, storprt_dda4d4a4-d312-4076-8b72-842517a701c5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortRegistryWrite
product:
- Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortRegistryWrite function
The <b>StorPortRegistryWrite</b> routine is called by the miniport driver to convert the registry data contained in a specified buffer from ASCII to Unicode and to then write the data to the miniport driver's per-HBA storage area.

## Syntax

```
STORPORT_API BOOLEAN StorPortRegistryWrite(
  PVOID  HwDeviceExtension,
  PUCHAR ValueName,
  ULONG  Global,
  ULONG  Type,
  PUCHAR Buffer,
  ULONG  BufferLength
);
```

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>. The port driver frees this memory when it removes the device. The miniport driver must be running at IRQL PASSIVE_LEVEL when it calls this routine.

`ValueName`

Pointer to a string that specifies the value name.

`Global`

Indicates whether the operation is to be adapter specific or to relate to all adapters.

`Type`

One of the following registry data types.

<table>
<tr>
<th>Type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
REG_SZ

</td>
<td>
Unicode null-terminated string.

</td>
</tr>
<tr>
<td>
REG_EXPAND_SZ

</td>
<td>
Unicode null-terminated string with environment variable references.

</td>
</tr>
<tr>
<td>
REG_BINARY

</td>
<td>
Binary data.

</td>
</tr>
<tr>
<td>
REG_DWORD

</td>
<td>
32-bit double word.

</td>
</tr>
<tr>
<td>
REG_DWORD_LITTLE_ENDIAN

</td>
<td>
32-bit double word with a little-endian format.

</td>
</tr>
<tr>
<td>
REG_DWORD_BIG_ENDIAN

</td>
<td>
32-bit double word with a big-endian format.

</td>
</tr>
<tr>
<td>
REG_LINK

</td>
<td>
Unicode string that specifies a symbolic link.

</td>
</tr>
<tr>
<td>
REG_MULTI_SZ

</td>
<td>
Multiple Unicode strings.

</td>
</tr>
<tr>
<td>
REG_RESOURCE_LIST

</td>
<td>
Resource list in the resource map.

</td>
</tr>
<tr>
<td>
REG_FULL_RESOURCE_DESCRIPTOR

</td>
<td>
Resource list in the hardware description.

</td>
</tr>
<tr>
<td>
REG_RESOURCE_REQUIREMENTS_LIST

</td>
<td>
Resource requirement list.

</td>
</tr>
<tr>
<td>
REG_QWORD

</td>
<td>
64-bit quadlet number.

</td>
</tr>
<tr>
<td>
REG_QWORD_LITTLE_ENDIAN

</td>
<td>
64-bit quadlet number with a little-endian format.

</td>
</tr>
</table>

`Buffer`

Pointer to a buffer that contains the registry data to be written.

`BufferLength`

Specifies the size of the buffer pointed to by <i>Buffer</i>.


## Return Value

<b>StorPortRegistryWrite</b> returns a Boolean value of <b>TRUE</b> if the registry data was successfully converted and written; otherwise, this routine returns <b>FALSE</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | StorPortIrql |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567108">StorPortInitialize</a>
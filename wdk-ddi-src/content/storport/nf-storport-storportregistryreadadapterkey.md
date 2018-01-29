---
UID : NF:storport.StorPortRegistryReadAdapterKey
title : StorPortRegistryReadAdapterKey function
author : windows-driver-content
description : The StorPortRegistryReadAdapterKey routine is called by the miniport driver to read the hardware or device registry adapter keys located in registry at HKLM/CurrentControlSet/Enum/&lt;Instance path&gt;/DeviceParameters/...
old-location : storage\storportregistryreadadapterkey.htm
old-project : storage
ms.assetid : 85D43276-53A1-4CEE-99FE-23ED8BECB316
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : StorPortRegistryWriteAdapterKey, StorPortRegistryReadAdapterKey, storport/StorPortRegistryWriteAdapterKey, StorPortRegistryWriteAdapterKey routine [Storage Devices], storage.storportregistryreadadapterkey
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : storport.h
req.include-header : Storport.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Storport.lib
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : STOR_SPINLOCK
req.product : Windows 10 or later.
---


# StorPortRegistryReadAdapterKey function
The <b>StorPortRegistryReadAdapterKey</b> routine is called by the miniport driver to read the hardware or device registry adapter keys located in registry at HKLM/CurrentControlSet/Enum/&lt;Instance path&gt;/DeviceParameters/... these keys are read from in the <a href="https://msdn.microsoft.com/417a4ab0-9723-4b3b-aa8c-342598874d61">INF DDInstall.HW Section</a>.

## Syntax

````
STORPORT_STATUS StorPortRegistryWriteAdapterKey(
  _In_     PVOID  HwDeviceExtension,
  _In_opt_ PCWSTR SubKeyName,
  _In_     PCWSTR ValueName,
  _In_     ULONG  ValueType,
  _Inout_  PVOID  ValueData,
  _Inout_  ULONG  ValueDataLength
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device. The miniport driver must be running at IRQL PASSIVE_LEVEL when it calls this routine.

`SubKeyName`

The miniport subkey.

`ValueName`

The name of the Value under the key.

`ValueType`

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

`ValueData`

Pointer to a the data that contains the registry data to be read. The data is converted from UNICODE to a NULL-terminated ASCII string.

`ValueDataLength`

Specifies the size of the data pointed to by <i>ValueData</i>.


## Return Value

Returns STOR_STATUS_SUCCESS when the operation is successful, otherwise the appropriate error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | storport.h (include Storport.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortRegistryReadAdapterKey routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
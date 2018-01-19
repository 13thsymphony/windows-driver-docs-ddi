---
UID : NF:wdm.IoGetDeviceInterfaceAlias
title : IoGetDeviceInterfaceAlias function
author : windows-driver-content
description : The IoGetDeviceInterfaceAlias routine returns the alias device interface of the specified device interface instance, if the alias exists.
old-location : kernel\iogetdeviceinterfacealias.htm
old-project : kernel
ms.assetid : 667c9524-be12-4f02-b921-6067abfb1dde
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : IoGetDeviceInterfaceAlias
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IoGetDeviceInterfaceAlias
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL (see Remarks section)
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# IoGetDeviceInterfaceAlias function
The <b>IoGetDeviceInterfaceAlias</b> routine returns the alias device interface of the specified device interface instance, if the alias exists.

## Syntax

````
NTSTATUS IoGetDeviceInterfaceAlias(
  _In_        PUNICODE_STRING SymbolicLinkName,
  _In_  const GUID            *AliasInterfaceClassGuid,
  _Out_       PUNICODE_STRING AliasSymbolicLinkName
);
````

## Parameters

`SymbolicLinkName`

Pointer to the name of the device interface instance for which to retrieve an alias. The caller typically received this string from a call to <a href="..\wdm\nf-wdm-iogetdeviceinterfaces.md">IoGetDeviceInterfaces</a> or in a PnP notification structure.

`AliasInterfaceClassGuid`

Pointer to a GUID specifying the interface class of the alias to retrieve.

`AliasSymbolicLinkName`

Specifies a pointer to a <b>NULL</b> Unicode string. On successful return, <i>AliasSymbolicLinkName</i>.<b>Buffer</b> points to a string containing the name of the alias. The caller must free the Unicode string with <a href="..\wdm\nf-wdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a> when it is no longer needed.


## Return Value

<b>IoGetDeviceInterfaceAlias</b> returns STATUS_SUCCESS if the call was successful. Possible error return values are described following.
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>Possibly indicates that there is no alias of the specified interface class.
<dl>
<dt><b>STATUS_OBJECT_PATH_NOT_FOUND</b></dt>
</dl>Possibly indicates that there is no alias of the specified interface class.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>Possibly indicates an invalid <i>SymbolicLinkName</i> or an invalid <i>AliasClassGuid</i>.

## Remarks

Device interfaces are considered aliases if they are exposed by the same underlying device and have identical interface reference strings, but are of different interface classes.

The <i>SymbolicLinkName</i> parameter specifies a device interface instance for a particular device, belonging to a particular interface class, with a particular reference string. <b>IoGetDeviceInterfaceAlias</b> returns another device interface instance for the same device and reference string, but of a different interface class, if it exists.

For example, the function driver for a fault-tolerant volume could register and set two device interfaces, one of the fault-tolerant-volume interface class and one of the volume interface class. Another driver could call <b>IoGetDeviceInterfaceAlias</b> with the symbolic link for one of the interfaces and ask whether the other interface exists by specifying its interface class.

Two device interfaces with <b>NULL</b> reference strings are aliases if they are exposed by the same underlying device and have different interface class GUIDs.

Callers of <b>IoGetDeviceInterfaceAlias</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL (see Remarks section) |
| **DDI compliance rules** | PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-ioregisterdeviceinterface.md">IoRegisterDeviceInterface</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetDeviceInterfaceAlias routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
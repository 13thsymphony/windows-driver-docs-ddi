---
UID : NF:wdm.IoCreateSymbolicLink
title : IoCreateSymbolicLink function
author : windows-driver-content
description : The IoCreateSymbolicLink routine sets up a symbolic link between a device object name and a user-visible name for the device.
old-location : kernel\iocreatesymboliclink.htm
old-project : kernel
ms.assetid : be080007-f88e-4cea-b15d-58dc4ac2cb66
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : IoCreateSymbolicLink, kernel.iocreatesymboliclink, wdm/IoCreateSymbolicLink, k104_8311eaf7-a12f-470d-b81f-83a12697ddbe.xml, IoCreateSymbolicLink routine [Kernel-Mode Driver Architecture]
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
req.ddi-compliance : IrqlIoPassive3, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# IoCreateSymbolicLink function
The <b>IoCreateSymbolicLink</b> routine sets up a symbolic link between a device object name and a user-visible name for the device.

## Syntax

````
NTSTATUS IoCreateSymbolicLink(
  _In_ PUNICODE_STRING SymbolicLinkName,
  _In_ PUNICODE_STRING DeviceName
);
````

## Parameters

`SymbolicLinkName`

Pointer to a buffered Unicode string that is the user-visible name.

`DeviceName`

Pointer to a buffered Unicode string that is the name of the driver-created device object.


## Return Value

<b>IoCreateSymbolicLink</b> returns STATUS_SUCCESS if the symbolic link object was created.

## Remarks

WDM drivers do not name device objects and therefore should not use this routine. Instead, a WDM driver should call <a href="..\wdm\nf-wdm-ioregisterdeviceinterface.md">IoRegisterDeviceInterface</a> to set up a symbolic link. 

For more information about when to use <b>IoCreateSymbolicLink</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556420">Named Device Objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | IrqlIoPassive3, PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-iocreateunprotectedsymboliclink.md">IoCreateUnprotectedSymbolicLink</a>

<a href="..\ntddk\nf-ntddk-ioassignarcname.md">IoAssignArcName</a>

<a href="..\wdm\nf-wdm-iodeletesymboliclink.md">IoDeleteSymbolicLink</a>

<a href="..\wdm\nf-wdm-ioregisterdeviceinterface.md">IoRegisterDeviceInterface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoCreateSymbolicLink routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
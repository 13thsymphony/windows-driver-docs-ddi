---
UID : NF:wdm.NtPowerInformation
title : NtPowerInformation function
author : windows-driver-content
description : The ZwPowerInformation routine sets or retrieves system power information.
old-location : kernel\zwpowerinformation.htm
old-project : kernel
ms.assetid : BA1D5AD2-E3E5-42CB-8E77-627B23078F80
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : NtPowerInformation, kernel.zwpowerinformation, wdm/NtPowerInformation, PlatformInformation, ZwPowerInformation, wdm/ZwPowerInformation, ZwPowerInformation routine [Kernel-Mode Driver Architecture]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h
req.target-type : Universal
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ntoskrnl.lib
req.dll : Ntoskrnl.lib
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


# NtPowerInformation function
The <b>ZwPowerInformation</b> routine sets or retrieves system power information.

## Syntax

````
NTSTATUS ZwPowerInformation(
  _In_      POWER_INFORMATION_LEVEL InformationLevel,
  _In_opt_  PVOID                   InputBuffer,
  _In_      ULONG                   InputBufferLength,
  _Out_opt_ PVOID                   OutputBuffer,
  _In_      ULONG                   OutputBufferLength
);
````

## Parameters

`InformationLevel`

Specifies the requested information level, which indicates the specific power information to be set or retrieved. Currently, the only supported <i>POWER_INFORMATION_LEVEL</i> value is <b>PlatformInformation</b>.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="PlatformInformation"></a><a id="platforminformation"></a><a id="PLATFORMINFORMATION"></a><dl>
<dt><b>PlatformInformation</b></dt>
</dl>
</td>
<td width="60%">
Information represents the currently supported power capabilities of the system. Information may change as drivers are installed. For example, the installation of legacy device drivers that do not support power management might modify the capabilities of the system.

</td>
</tr>
</table>

`InputBuffer`

Pointer to a caller-allocated input buffer. This parameter must be <b>NULL</b>, otherwise <b>ERROR_INVALID_PARAMETER</b> is returned.

`InputBufferLength`

Size, in bytes, of the buffer at <i>InputBuffer</i>. The parameter must be set to zero.

`OutputBuffer`

A pointer to an output buffer. The data type of this buffer depends on the information level requested in the <i>InformationLevel</i> parameter. For the <b>PlatformInformation</b> level, the only currently supported value, the <i>OutputBuffer </i> parameter is required and should be of the <a href="..\wdm\ns-wdm-_power_platform_information.md">POWER_PLATFORM_INFORMATION</a> type.

`OutputBufferLength`

Size, in bytes, of the output buffer. Depending on the information level requested, the buffer may be variably sized. <i>PlatformInformation</i>, the only currently supported value, requires a buffer that is the size of a <a href="..\wdm\ns-wdm-_power_platform_information.md">POWER_PLATFORM_INFORMATION</a> structure.


## Return Value

Returns STATUS_SUCCESS if the call is successful. If the call fails, possible error codes include the following:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The output buffer is of insufficient size to contain the data being returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <b>PlatformInformation</b> information level, which is the only currently supported value, requires no input buffer and must contain an output buffer. The caller either supplied an input buffer or no output buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller had insufficient access rights to perform the requested action.

</td>
</tr>
</table>

## Remarks

<a href="https://msdn.microsoft.com/library/windows/hardware/dn957451">NtPowerInformation</a> and <b>ZwPowerInformation</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h) |
| **Library** | Ntoskrnl.lib |
| **DLL** | Ntoskrnl.lib |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>

<a href="..\wdm\ns-wdm-_power_platform_information.md">POWER_PLATFORM_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwPowerInformation routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
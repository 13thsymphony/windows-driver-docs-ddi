---
UID: NF:wdmsec.WdmlibIoValidateDeviceIoControlAccess
title: WdmlibIoValidateDeviceIoControlAccess function
author: windows-driver-content
description: The WdmlibIoValidateDeviceIoControlAccess function verifies that the sender of an IRP_MJ_DEVICE_CONTROL or IRP_MJ_FILE_SYSTEM_CONTROL IRP has the specified access to the device object.
old-location: kernel\wdmlibiovalidatedeviceiocontrolaccess.htm
old-project: kernel
ms.assetid: F986A431-A70D-4488-A792-F37128902C7E
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: FILE_READ_ACCESS, FILE_WRITE_ACCESS, IoValidateDeviceIoControlAccess, WdmlibIoValidateDeviceIoControlAccess, WdmlibIoValidateDeviceIoControlAccess function [Kernel-Mode Driver Architecture], kernel.wdmlibiovalidatedeviceiocontrolaccess, wdmsec/IoValidateDeviceIoControlAccess, wdmsec/WdmlibIoValidateDeviceIoControlAccess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdmsec.h
req.include-header: Wdmsec.h, Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows. Drivers that must also work for Windows 2000 and Windows XP can instead link to Wdmsec.lib to use this routine. (The Wdmsec.lib library first shipped with the Windows XP Service Pack 1 [SP1] and Windows Server 2003 editions of the Driver Development Kit [DDK] and now ships with the Windows Driver Kit [WDK].)
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	WdmlibIoValidateDeviceIoControlAccess
-	IoValidateDeviceIoControlAccess
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_ITEM, *PWORK_QUEUE_ITEM
req.product: Windows 10 or later.
---


# WdmlibIoValidateDeviceIoControlAccess function
The <b>WdmlibIoValidateDeviceIoControlAccess</b> function verifies that the sender of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550751">IRP_MJ_FILE_SYSTEM_CONTROL</a> IRP has the specified access to the device object.

## Syntax

````
NTSTATUS WdmlibIoValidateDeviceIoControlAccess(
  _In_ PIRP  Irp,
  _In_ ULONG RequiredAccess
);
````

## Parameters

`Irp`

Specifies the <a href="..\wdm\ns-wdm-_irp.md">IRP</a> on which to perform the access check.

`RequiredAccess`

Specifies the type of access to the device object that the request sender must have. The caller can specify one or more of the following flags.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="FILE_READ_ACCESS"></a><a id="file_read_access"></a><dl>
<dt><b>FILE_READ_ACCESS</b></dt>
</dl>
</td>
<td width="60%">
The request sender must have read access to the device object

</td>
</tr>
<tr>
<td width="40%"><a id="FILE_WRITE_ACCESS"></a><a id="file_write_access"></a><dl>
<dt><b>FILE_WRITE_ACCESS</b></dt>
</dl>
</td>
<td width="60%">
The request sender must have write access to the device object.

</td>
</tr>
</table>


## Return Value

<b>WdmlibIoValidateDeviceIoControlAccess</b> returns an NTSTATUS value. Possible return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The request sender has the necessary access to the device object. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The request sender does not have the necessary access to the device object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified parameters are invalid. For example, if the routine is passed an IRP that is not an <b>IRP_MJ_DEVICE_CONTROL</b> or <b>IRP_MJ_FILE_SYSTEM_CONTROL</b> IRP, it returns STATUS_INVALID_PARAMETER. 

</td>
</tr>
</table>

## Remarks

<b>WdmlibIoValidateDeviceIoControlAccess</b> allows drivers to perform dynamic access checks for IOCTLs. Use this routine to require more restrictive access than that specified in the IOCTL's definition. If the routine returns STATUS_ACCESS_DENIED, then the driver can complete the request with the STATUS_ACCESS_DENIED status value.

For example, if an IOCTL is defined with a <i>RequiredAccess</i> value of FILE_ANY_ACCESS, then by default any request sender with SYNCHRONIZE access to the device object can send the IOCTL. Use 
             <b>WdmlibIoValidateDeviceIoControlAccess</b> to require more stringent security at run time. For more information about the <i>RequiredAccess</i> value of an IOCTL, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543023">Defining I/O Control Codes</a>.

The access checks are only performed if the <b>RequestorMode</b> member of the <a href="..\wdm\ns-wdm-_irp.md">IRP</a> structure is <b>UserMode</b>. If <b>RequestorMode</b> is <b>KernelMode</b>, the routine automatically returns STATUS_SUCCESS.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Server 2003 and later versions of Windows. Drivers that must also work for Windows 2000 and Windows XP can instead link to Wdmsec.lib to use this routine. (The Wdmsec.lib library first shipped with the Windows XP Service Pack 1 [SP1] and Windows Server 2003 editions of the Driver Development Kit [DDK] and now ships with the Windows Driver Kit [WDK].)  |
| **Target Platform** | Universal |
| **Header** | wdmsec.h (include Wdmsec.h, Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\ns-wdm-_irp.md">IRP</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WdmlibIoValidateDeviceIoControlAccess function%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
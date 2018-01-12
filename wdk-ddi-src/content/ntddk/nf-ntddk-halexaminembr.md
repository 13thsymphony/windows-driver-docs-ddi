---
UID: NF:ntddk.HalExamineMBR
title: HalExamineMBR function
author: windows-driver-content
description: The HalExamineMBR routine reads the master boot record (MBR) of a disk and returns data from the MBR if the MBR is of the type specified by the caller.
old-location: kernel\halexaminembr.htm
old-project: kernel
ms.assetid: 6db72f2c-af24-4807-b90b-65dc2b309dc7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: HalExamineMBR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HalExamineMBR
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.typenames: *PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT
---

# HalExamineMBR function



## -description
The <b>HalExamineMBR</b> routine reads the master boot record (MBR) of a disk and returns data from the MBR if the MBR is of the type specified by the caller.



## -syntax

````
VOID HalExamineMBR(
  _In_  PDEVICE_OBJECT DeviceObject,
  _In_  ULONG          SectorSize,
  _In_  ULONG          MBRTypeIdentifier,
  _Out_ PVOID          *Buffer
);
````


## -parameters

### -param DeviceObject [in]

A pointer to the device object for the device being examined.


### -param SectorSize [in]

The minimum number of bytes that an I/O operation can fetch from the device being examined. If this value is less than 512, <b>HalExamineMBR</b> reads 512 bytes to ensure that it reads an entire partition table.


### -param MBRTypeIdentifier [in]

MBR partition type identifier. This parameter specifies the type of MBR that may be on the disk. For more information, see Remarks.


### -param Buffer [out]

A pointer to a location to which <b>HalExamineMBR</b> writes a pointer to a buffer that contains data from the MBR. The layout of the buffer depends on the MBR partition type. <b>HalExamineMBR</b> allocates the storage for this buffer. The caller must deallocate this buffer as soon as possible by calling the <a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a> routine.

<b>HalExamineMBR</b> sets *<i>Buffer</i> = <b>NULL</b> if the MBR partition type of the disk does not match that specified by <i>MBRTypeIdentifier</i> or if there is an error.


## -returns
None


## -remarks
For a list of system-defined MBR partition type identifiers, see the table in <a href="..\ntdddisk\ns-ntdddisk-_partition_information.md">PARTITION_INFORMATION</a>. These identifiers are defined in the Ntdddisk.h header file.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows XP.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975204">PowerIrpDDis</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>
</dt>
<dt>
<a href="..\ntdddisk\ns-ntdddisk-_partition_information.md">PARTITION_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20HalExamineMBR routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


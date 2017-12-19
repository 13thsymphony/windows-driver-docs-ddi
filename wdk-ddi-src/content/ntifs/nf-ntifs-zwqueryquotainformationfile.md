---
UID: NF.ntifs.ZwQueryQuotaInformationFile
title: ZwQueryQuotaInformationFile function
author: windows-driver-content
description: The ZwQueryQuotaInformationFile routine retrieves quota entries associated with the volume specified by the FileHandle parameter.
old-location: kernel\zwqueryquotainformationfile.htm
old-project: kernel
ms.assetid: 572477c7-8588-415e-b66f-adab977ab373
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: ZwQueryQuotaInformationFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwQueryQuotaInformationFile,NtQueryQuotaInformationFile
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
---

# ZwQueryQuotaInformationFile function



## -description
The <b>ZwQueryQuotaInformationFile</b> routine retrieves quota entries associated with the volume specified by the <i>FileHandle</i> parameter. 



## -syntax

````
NTSTATUS ZwQueryQuotaInformationFile(
  _In_     HANDLE           FileHandle,
  _Out_    PIO_STATUS_BLOCK IoStatusBlock,
  _Out_    PVOID            Buffer,
  _In_     ULONG            Length,
  _In_     BOOLEAN          ReturnSingleEntry,
  _In_opt_ PVOID            SidList,
  _In_     ULONG            SidListLength,
  _In_opt_ PSID             StartSid,
  _In_     BOOLEAN          RestartScan
);
````


## -parameters

### -param FileHandle [in]

A handle for the file object that represents the file or volume for which the quota information is requested.


### -param IoStatusBlock [out]

The address of the caller's I/O status block.


### -param Buffer [out]

A buffer to receive the quota information for the volume. The quota information is formatted as one or more <a href="ifsk.file_quota_information">FILE_QUOTA_INFORMATION</a> structures. The <b>NextEntryOffset</b> field in the <b>FILE_QUOTA_INFORMATION</b> structure contains the offset, in bytes, of the next quota entry in the list. If there are no more entries after the current one, this member is zero.


### -param Length [in]

The length in bytes of the buffer.


### -param ReturnSingleEntry [in]

A Boolean value that indicates if only a single entry should be returned rather than filling the buffer with as many entries as possible.


### -param SidList [in, optional]

An optional list of SIDs whose quota information is to be returned. Each entry in the list is a <a href="ifsk.file_get_quota_information">FILE_GET_QUOTA_INFORMATION</a> structure. The <b>NextEntryOffset</b> field in the <b>FILE_GET_QUOTA_INFORMATION</b> structure contains the offset, in bytes, of the next quota entry in the list. If there are no more entries after the current one, this member is zero.


### -param SidListLength [in]

The length in bytes of the <b>SID</b> list, if one was specified.


### -param StartSid [in, optional]

An optional pointer to the <b>SID</b> of the entry at which to begin scanning the quota information. This parameter should be set if the returned information is to start with an entry other than the first SID. This parameter is ignored if a <i>SidList</i> parameter is specified. 


### -param RestartScan [in]

A Boolean value that indicates whether the scan of the quota information is to be restarted from the beginning. Set this parameter to <b>TRUE</b> if the scan of the quota information is to start at the first entry in the volume's quota information list. Set to <b>FALSE</b> if resuming the scan from a previous call to <b>ZwQueryQuotaInformationFile</b>. The caller must set this parameter to <b>TRUE</b> when calling <b>ZwQueryQuotaInformationFile</b> for the first time.


## -returns
The <b>ZwQueryQuotaInformationFile</b> routine returns STATUS_SUCCESS if at least one <a href="ifsk.file_quota_information">FILE_QUOTA_INFORMATION</a> structure is returned in the <i>Buffer</i> parameter or an appropriate NTSTATUS value such as one of the following:
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES </b></dt>
</dl>There were insufficient resources to complete the operation. This is an error code.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>Quotas are not enabled on the volume. This is an error code.
<dl>
<dt><b>STATUS_INVALID_SID</b></dt>
</dl>The<i> StartSid</i> parameter did not contain a valid <b>SID</b>. This is an error code.
<dl>
<dt><b>STATUS_QUOTA_LIST_INCONSISTENT</b></dt>
</dl>The<i> SidList</i> parameter did not contain a valid, properly formed list. This is an error code.

 


## -remarks
The amount of information returned by <b>ZwQueryQuotaInformationFile</b> is based on the size of the quota information associated with the volume, the size of the buffer, and whether a specific set of entries has been requested.

A call to <b>ZwQueryQuotaInformationFile</b> will result in an <a href="ifsk.irp_mj_query_quota">IRP_MJ_QUERY_QUOTA</a> request being sent to the device object that is associated with the file object whose handle is stored in the <i>FileHandle</i> parameter.

If the underlying file system does not support quota information (FAT and CDFS file systems, for example), <b>ZwQueryQuotaInformationFile</b> will fail returning STATUS_INVALID_DEVICE_REQUEST.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.


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
Available in Windows 7 and later versions of Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or FltKernel.h)</dt>
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
<a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.file_get_quota_information">FILE_GET_QUOTA_INFORMATION</a>
</dt>
<dt>
<a href="ifsk.file_quota_information">FILE_QUOTA_INFORMATION</a>
</dt>
<dt>
<a href="kernel.io_status_block">IO_STATUS_BLOCK</a>
</dt>
<dt>
<a href="ifsk.iocheckquotabuffervalidity">IoCheckQuotaBufferValidity</a>
</dt>
<dt>
<a href="ifsk.irp_mj_query_quota">IRP_MJ_QUERY_QUOTA</a>
</dt>
<dt>
<a href="ifsk.irp_mj_set_quota">IRP_MJ_SET_QUOTA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="kernel.zwsetquotainformationfile">ZwSetQuotaInformationFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwQueryQuotaInformationFile routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


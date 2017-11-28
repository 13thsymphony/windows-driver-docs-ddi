---
UID: NF.ntifs.RtlCreateSystemVolumeInformationFolder
title: RtlCreateSystemVolumeInformationFolder
author: windows-driver-content
description: The RtlCreateSystemVolumeInformationFolder routine verifies the existence of the &#0034;System Volume Information&#0034; folder on a file system volume. If the folder is not present, then the folder is created.
old-location: ifsk\rtlcreatesystemvolumeinformationfolder.htm
old-project: ifsk
ms.assetid: bcbbddc7-6675-4555-bd05-588762148554
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: RtlCreateSystemVolumeInformationFolder
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Windows XP and later Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlCreateSystemVolumeInformationFolder
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.iface: 
---

# RtlCreateSystemVolumeInformationFolder function



## -description
<p>The <b>RtlCreateSystemVolumeInformationFolder</b> routine verifies the existence of the "System Volume Information" folder on a file system volume. If the folder is not present, then the folder is created. </p>


## -syntax

````
NTSTATUS RtlCreateSystemVolumeInformationFolder(
  _In_ PCUNICODE_STRING VolumeRootPath
);
````


## -parameters
<dl>

### -param <i>VolumeRootPath</i> [in]

<dd>
<p>A pointer to a path to the root of the volume.</p>
</dd>
</dl>

## -returns
<p>The <b>RtlCreateSystemVolumeInformationFolder</b> routine returns STATUS_SUCCESS or an appropriate error status representing the final completion status of the operation. Possible error status codes include the following: </p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p>A temporary buffer required by this function could not be allocated. </p>

<p> </p>

## -remarks
<p>The <b>RtlCreateSystemVolumeInformationFolder</b> routine verifies the existence of the "System Volume Information" folder on the given volume. </p>

<p>If the folder is not present, then the folder is created. If the volume is an NTFS volume, the folder is created with an access control list (<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>) containing one access control entry (<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>) indicating full access for the local SYSTEM account, and the ACE will have the inheritance bits set. The folder will be created with the FILE_ATTRIBUTE_HIDDEN and FILE_ATTRIBUTE_SYSTEM attributes set.</p>

<p>If the folder is already present and the volume is an NTFS volume, the ACE that indicates full control for SYSTEM will be checked and if necessary modified to have the inheritance bits set.</p>

<p>For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.</p>

<p>The <b>RtlCreateSystemVolumeInformationFolder</b> routine verifies the existence of the "System Volume Information" folder on the given volume. </p>

<p>If the folder is not present, then the folder is created. If the volume is an NTFS volume, the folder is created with an access control list (<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>) containing one access control entry (<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>) indicating full access for the local SYSTEM account, and the ACE will have the inheritance bits set. The folder will be created with the FILE_ATTRIBUTE_HIDDEN and FILE_ATTRIBUTE_SYSTEM attributes set.</p>

<p>If the folder is already present and the volume is an NTFS volume, the ACE that indicates full control for SYSTEM will be checked and if necessary modified to have the inheritance bits set.</p>

<p>For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>This routine is available on Windows XP and later Windows operating systems. </p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or FltKernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlCreateSystemVolumeInformationFolder routine%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

---
UID: NE:fltuserstructures._FLT_FILESYSTEM_TYPE
title: _FLT_FILESYSTEM_TYPE
author: windows-driver-content
description: The FLT_FILESYSTEM_TYPE enumeration identifies the type of file system being used on a volume.
old-location: ifsk\flt_filesystem_type.htm
old-project: ifsk
ms.assetid: b4bdfa93-3db5-4dfa-b539-112927cbedb0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _FLT_FILESYSTEM_TYPE, *PFLT_FILESYSTEM_TYPE, FLT_FILESYSTEM_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fltuserstructures.h
req.include-header: FltUser.h, FltKernel.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FLT_FILESYSTEM_TYPE
req.alt-loc: fltUserStructures.h
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
req.typenames: *PFLT_FILESYSTEM_TYPE, FLT_FILESYSTEM_TYPE
---

# _FLT_FILESYSTEM_TYPE enumeration



## -description
The <b>FLT_FILESYSTEM_TYPE</b> enumeration identifies the type of file system being used on a volume. 



## -syntax

````
typedef enum _FLT_FILESYSTEM_TYPE { 
  FLT_FSTYPE_UNKNOWN,
  FLT_FSTYPE_RAW,
  FLT_FSTYPE_NTFS,
  FLT_FSTYPE_FAT,
  FLT_FSTYPE_CDFS,
  FLT_FSTYPE_UDFS,
  FLT_FSTYPE_LANMAN,
  FLT_FSTYPE_WEBDAV,
  FLT_FSTYPE_RDPDR,
  FLT_FSTYPE_NFS,
  FLT_FSTYPE_MS_NETWARE,
  FLT_FSTYPE_NETWARE,
  FLT_FSTYPE_BSUDF,
  FLT_FSTYPE_MUP,
  FLT_FSTYPE_RSFX,
  FLT_FSTYPE_ROXIO_UDF1,
  FLT_FSTYPE_ROXIO_UDF2,
  FLT_FSTYPE_ROXIO_UDF3,
  FLT_FSTYPE_TACIT,
  FLT_FSTYPE_FS_REC,
  FLT_FSTYPE_INCD,
  FLT_FSTYPE_INCD_FAT,
  FLT_FSTYPE_EXFAT,
  FLT_FSTYPE_PSFS,
  FLT_FSTYPE_GPFS,
  FLT_FSTYPE_NPFS,
  FLT_FSTYPE_MSFS,
  FLT_FSTYPE_CSVFS,
  FLT_FSTYPE_REFS,
  FLT_FSTYPE_OPENAFS
} FLT_FILESYSTEM_TYPE, *PFLT_FILESYSTEM_TYPE;
````


## -enum-fields

### -field FLT_FSTYPE_UNKNOWN

Unknown file system type.


### -field FLT_FSTYPE_RAW

Microsoft RAW file system. File system namespace: \FileSystem\RAW. 


### -field FLT_FSTYPE_NTFS

Microsoft NTFS file system. File system namespace:  \FileSystem\Ntfs.


### -field FLT_FSTYPE_FAT

Microsoft FAT file system. File system namespace: \FileSystem\Fastfat. 


### -field FLT_FSTYPE_CDFS

Microsoft CDFS file system. File system namespace: \FileSystem\Cdfs.


### -field FLT_FSTYPE_UDFS

Microsoft UDFS file system. File system namespace: \FileSystem\Udfs.


### -field FLT_FSTYPE_LANMAN

Microsoft LanMan Redirector. File system namespace: \FileSystem\MRxSmb.


### -field FLT_FSTYPE_WEBDAV

Microsoft WebDav redirector. File system namespace: \FileSystem\MRxDav.


### -field FLT_FSTYPE_RDPDR

Microsoft Terminal Server redirector. File system namespace: \Driver\rdpdr.


### -field FLT_FSTYPE_NFS

Microsoft NFS file system. File system namespace: \FileSystem\NfsRdr.


### -field FLT_FSTYPE_MS_NETWARE

Microsoft NetWare redirector. File system namespace: \FileSystem\nwrdr.


### -field FLT_FSTYPE_NETWARE

Novell NetWare redirector.


### -field FLT_FSTYPE_BSUDF

The BsUDF CD-ROM driver. File system namespace: \FileSystem\BsUDF.


### -field FLT_FSTYPE_MUP

Microsoft MUP redirector. File system namespace: \FileSystem\Mup.


### -field FLT_FSTYPE_RSFX

Microsoft WinFS redirector. File system namespace: \FileSystem\RsFxDrv.


### -field FLT_FSTYPE_ROXIO_UDF1

Roxio UDF writeable file system. File system namespace: \FileSystem\cdudf_xp.


### -field FLT_FSTYPE_ROXIO_UDF2

Roxio UDF readable file system. File system namespace: \FileSystem\UdfReadr_xp.


### -field FLT_FSTYPE_ROXIO_UDF3

Roxio DVD file system. File system namespace: \FileSystem\DVDVRRdr_xp.


### -field FLT_FSTYPE_TACIT

Tacit file system. Namespace: \Device\TCFSPSE.


### -field FLT_FSTYPE_FS_REC

Microsoft file system recognizer. File system namespace: \FileSystem\Fs_rec.


### -field FLT_FSTYPE_INCD

Nero InCD file system. File system namespace: \FileSystem\InCDfs.


### -field FLT_FSTYPE_INCD_FAT

Nero InCD FAT file system. File system namespace: \FileSystem\InCDFat.


### -field FLT_FSTYPE_EXFAT

Microsoft EXFat file system. File system namespace: \FileSystem\exfat.


### -field FLT_FSTYPE_PSFS

PolyServ file system. File system namespace: \FileSystem\psfs.


### -field FLT_FSTYPE_GPFS

IBM General Parallel File System. File system namespace: \FileSystem\gpfs.


### -field FLT_FSTYPE_NPFS

Microsoft named pipe file system. File system namespace: \FileSystem\npfs.


### -field FLT_FSTYPE_MSFS

Microsoft mailslot file system. File system namespace: \FileSystem\msfs.


### -field FLT_FSTYPE_CSVFS

Microsoft cluster shared volume file system. File system namespace: \FileSystem\csvfs.


### -field FLT_FSTYPE_REFS

Microsoft ReFS file system. File system namespace: \FileSystem\refs.


### -field FLT_FSTYPE_OPENAFS

 OpenAFS file system. File system namespace: \FileSystem\AFSRedirector.


## -remarks
New file systems that are not part of the <b>FLT_FILESYSTEM_TYPE</b> enumeration are treated as <b>FLT_FSTYPE_UNKNOWN</b>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows XP and later versions of the Windows operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>FltUserStructures.h (include FltUser.h or FltKernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fltuserstructures\ns-fltuserstructures-_filter_volume_standard_information.md">FILTER_VOLUME_STANDARD_INFORMATION</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetfilesystemtype.md">FltGetFileSystemType</a>
</dt>
<dt>
<a href="..\fltuserstructures\ns-fltuserstructures-_instance_aggregate_standard_information.md">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_instance_setup_callback.md">PFLT_INSTANCE_SETUP_CALLBACK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FLT_FILESYSTEM_TYPE enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


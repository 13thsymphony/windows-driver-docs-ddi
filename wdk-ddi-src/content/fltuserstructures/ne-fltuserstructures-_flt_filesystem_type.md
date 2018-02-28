---
UID: NE:fltuserstructures._FLT_FILESYSTEM_TYPE
title: "_FLT_FILESYSTEM_TYPE"
author: windows-driver-content
description: The FLT_FILESYSTEM_TYPE enumeration identifies the type of file system being used on a volume.
old-location: ifsk\flt_filesystem_type.htm
old-project: ifsk
ms.assetid: b4bdfa93-3db5-4dfa-b539-112927cbedb0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFLT_FILESYSTEM_TYPE, FLT_FILESYSTEM_TYPE, FLT_FILESYSTEM_TYPE enumeration [Installable File System Drivers], FLT_FSTYPE_BSUDF, FLT_FSTYPE_CDFS, FLT_FSTYPE_CSVFS, FLT_FSTYPE_EXFAT, FLT_FSTYPE_FAT, FLT_FSTYPE_FS_REC, FLT_FSTYPE_GPFS, FLT_FSTYPE_INCD, FLT_FSTYPE_INCD_FAT, FLT_FSTYPE_LANMAN, FLT_FSTYPE_MSFS, FLT_FSTYPE_MS_NETWARE, FLT_FSTYPE_MUP, FLT_FSTYPE_NETWARE, FLT_FSTYPE_NFS, FLT_FSTYPE_NPFS, FLT_FSTYPE_NTFS, FLT_FSTYPE_OPENAFS, FLT_FSTYPE_PSFS, FLT_FSTYPE_RAW, FLT_FSTYPE_RDPDR, FLT_FSTYPE_REFS, FLT_FSTYPE_ROXIO_UDF1, FLT_FSTYPE_ROXIO_UDF2, FLT_FSTYPE_ROXIO_UDF3, FLT_FSTYPE_RSFX, FLT_FSTYPE_TACIT, FLT_FSTYPE_UDFS, FLT_FSTYPE_UNKNOWN, FLT_FSTYPE_WEBDAV, PFLT_FILESYSTEM_TYPE, PFLT_FILESYSTEM_TYPE enumeration pointer [Installable File System Drivers], _FLT_FILESYSTEM_TYPE, fltuserstructures/FLT_FILESYSTEM_TYPE, fltuserstructures/FLT_FSTYPE_BSUDF, fltuserstructures/FLT_FSTYPE_CDFS, fltuserstructures/FLT_FSTYPE_CSVFS, fltuserstructures/FLT_FSTYPE_EXFAT, fltuserstructures/FLT_FSTYPE_FAT, fltuserstructures/FLT_FSTYPE_FS_REC, fltuserstructures/FLT_FSTYPE_GPFS, fltuserstructures/FLT_FSTYPE_INCD, fltuserstructures/FLT_FSTYPE_INCD_FAT, fltuserstructures/FLT_FSTYPE_LANMAN, fltuserstructures/FLT_FSTYPE_MSFS, fltuserstructures/FLT_FSTYPE_MS_NETWARE, fltuserstructures/FLT_FSTYPE_MUP, fltuserstructures/FLT_FSTYPE_NETWARE, fltuserstructures/FLT_FSTYPE_NFS, fltuserstructures/FLT_FSTYPE_NPFS, fltuserstructures/FLT_FSTYPE_NTFS, fltuserstructures/FLT_FSTYPE_OPENAFS, fltuserstructures/FLT_FSTYPE_PSFS, fltuserstructures/FLT_FSTYPE_RAW, fltuserstructures/FLT_FSTYPE_RDPDR, fltuserstructures/FLT_FSTYPE_REFS, fltuserstructures/FLT_FSTYPE_ROXIO_UDF1, fltuserstructures/FLT_FSTYPE_ROXIO_UDF2, fltuserstructures/FLT_FSTYPE_ROXIO_UDF3, fltuserstructures/FLT_FSTYPE_RSFX, fltuserstructures/FLT_FSTYPE_TACIT, fltuserstructures/FLT_FSTYPE_UDFS, fltuserstructures/FLT_FSTYPE_UNKNOWN, fltuserstructures/FLT_FSTYPE_WEBDAV, fltuserstructures/PFLT_FILESYSTEM_TYPE, ifsk.flt_filesystem_type"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltUserStructures.h
api_name:
-	FLT_FILESYSTEM_TYPE
product: Windows
targetos: Windows
req.typenames: FLT_FILESYSTEM_TYPE, *PFLT_FILESYSTEM_TYPE
---

# _FLT_FILESYSTEM_TYPE Enumeration
The <b>FLT_FILESYSTEM_TYPE</b> enumeration identifies the type of file system being used on a volume.

## Syntax
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

## Constants

<table>
            
                <tr>
                    <td>FLT_FSTYPE_BSUDF</td>
                    <td>The BsUDF CD-ROM driver. File system namespace: \FileSystem\BsUDF.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_CDFS</td>
                    <td>Microsoft CDFS file system. File system namespace: \FileSystem\Cdfs.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_CSVFS</td>
                    <td>Microsoft cluster shared volume file system. File system namespace: \FileSystem\csvfs.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_EXFAT</td>
                    <td>Microsoft EXFat file system. File system namespace: \FileSystem\exfat.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_FAT</td>
                    <td>Microsoft FAT file system. File system namespace: \FileSystem\Fastfat.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_FS_REC</td>
                    <td>Microsoft file system recognizer. File system namespace: \FileSystem\Fs_rec.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_GPFS</td>
                    <td>IBM General Parallel File System. File system namespace: \FileSystem\gpfs.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_INCD</td>
                    <td>Nero InCD file system. File system namespace: \FileSystem\InCDfs.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_INCD_FAT</td>
                    <td>Nero InCD FAT file system. File system namespace: \FileSystem\InCDFat.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_LANMAN</td>
                    <td>Microsoft LanMan Redirector. File system namespace: \FileSystem\MRxSmb.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_MS_NETWARE</td>
                    <td>Microsoft NetWare redirector. File system namespace: \FileSystem\nwrdr.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_MSFS</td>
                    <td>Microsoft mailslot file system. File system namespace: \FileSystem\msfs.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_MUP</td>
                    <td>Microsoft MUP redirector. File system namespace: \FileSystem\Mup.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_NETWARE</td>
                    <td>Novell NetWare redirector.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_NFS</td>
                    <td>Microsoft NFS file system. File system namespace: \FileSystem\NfsRdr.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_NPFS</td>
                    <td>Microsoft named pipe file system. File system namespace: \FileSystem\npfs.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_NTFS</td>
                    <td>Microsoft NTFS file system. File system namespace:  \FileSystem\Ntfs.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_OPENAFS</td>
                    <td>OpenAFS file system. File system namespace: \FileSystem\AFSRedirector.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_PSFS</td>
                    <td>PolyServ file system. File system namespace: \FileSystem\psfs.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_RAW</td>
                    <td>Microsoft RAW file system. File system namespace: \FileSystem\RAW.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_RDPDR</td>
                    <td>Microsoft Terminal Server redirector. File system namespace: \Driver\rdpdr.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_REFS</td>
                    <td>Microsoft ReFS file system. File system namespace: \FileSystem\refs.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_ROXIO_UDF1</td>
                    <td>Roxio UDF writeable file system. File system namespace: \FileSystem\cdudf_xp.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_ROXIO_UDF2</td>
                    <td>Roxio UDF readable file system. File system namespace: \FileSystem\UdfReadr_xp.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_ROXIO_UDF3</td>
                    <td>Roxio DVD file system. File system namespace: \FileSystem\DVDVRRdr_xp.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_RSFX</td>
                    <td>Microsoft WinFS redirector. File system namespace: \FileSystem\RsFxDrv.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_TACIT</td>
                    <td>Tacit file system. Namespace: \Device\TCFSPSE.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_UDFS</td>
                    <td>Microsoft UDFS file system. File system namespace: \FileSystem\Udfs.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_UNKNOWN</td>
                    <td>Unknown file system type.</td>
                </tr>
            
                <tr>
                    <td>FLT_FSTYPE_WEBDAV</td>
                    <td>Microsoft WebDav redirector. File system namespace: \FileSystem\MRxDav.</td>
                </tr>
</table>

## Remarks

New file systems that are not part of the <b>FLT_FILESYSTEM_TYPE</b> enumeration are treated as <b>FLT_FSTYPE_UNKNOWN</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of the Windows operating system. Available in Windows XP and later versions of the Windows operating system. |
| **Header** | fltuserstructures.h (include FltUser.h, FltKernel.h) |

## See Also

<a href="..\fltkernel\nc-fltkernel-pflt_instance_setup_callback.md">PFLT_INSTANCE_SETUP_CALLBACK</a>



<a href="..\fltuserstructures\ns-fltuserstructures-_filter_volume_standard_information.md">FILTER_VOLUME_STANDARD_INFORMATION</a>



<a href="..\fltkernel\nf-fltkernel-fltgetfilesystemtype.md">FltGetFileSystemType</a>



<a href="..\fltuserstructures\ns-fltuserstructures-_instance_aggregate_standard_information.md">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FLT_FILESYSTEM_TYPE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
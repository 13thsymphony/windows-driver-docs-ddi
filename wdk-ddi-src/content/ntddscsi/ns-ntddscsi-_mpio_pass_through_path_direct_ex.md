---
UID : NS:ntddscsi._MPIO_PASS_THROUGH_PATH_DIRECT_EX
title : _MPIO_PASS_THROUGH_PATH_DIRECT_EX
author : windows-driver-content
description : The MPIO_PASS_THROUGH_PATH_DIRECT_EX structure is used together with an IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX request to instruct the port driver to send an embedded SCSI command to the target device.
old-location : storage\mpio_pass_through_path_direct_ex.htm
old-project : storage
ms.assetid : 3EB8721D-291E-492A-9BB3-28F411195DD5
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _MPIO_PASS_THROUGH_PATH_DIRECT_EX, *PMPIO_PASS_THROUGH_PATH_DIRECT_EX, MPIO_PASS_THROUGH_PATH_DIRECT_EX
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddscsi.h
req.include-header : Ntddscsi.h
req.target-type : Windows
req.target-min-winverclnt : Available starting with Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : MPIO_PASS_THROUGH_PATH_DIRECT_EX
req.alt-loc : ntddscsi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PMPIO_PASS_THROUGH_PATH_DIRECT_EX, MPIO_PASS_THROUGH_PATH_DIRECT_EX"
---

# _MPIO_PASS_THROUGH_PATH_DIRECT_EX structure
The <b>MPIO_PASS_THROUGH_PATH_DIRECT_EX</b> structure is used together with an <a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path_direct_ex.md">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX</a> request to instruct the port driver to send an embedded SCSI command to the target device.

## Syntax
````
typedef struct _MPIO_PASS_THROUGH_PATH_DIRECT_EX {
  ULONG     PassThroughOffset;
  ULONG     Version;
  USHORT    Length;
  UCHAR     Flags;
  UCHAR     PortNumber;
  ULONGLONG MpioPathId;
} MPIO_PASS_THROUGH_PATH_DIRECT_EX, *PMPIO_PASS_THROUGH_PATH_DIRECT_EX;
````

## Members

        
            `Flags`

            
        
            `Length`

            The size of the <b>MPIO_PASS_THROUGH_PATH_DIRECT_EX</b> structure.
        
            `MpioPathId`

            The <b>PathId</b> for the real LUN. This value can be obtained by using a WMI request for the PDO_INFORMATION that is associated with the real LUN. This value is set only if MPIO_IOCTL_FLAG_USE_PATHID is set.
        
            `PassThroughOffset`

            The offset from the beginning of this structure to a <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_direct_ex.md">SCSI_PASS_THROUGH_DIRECT_EX</a> structure that is configured in the same manner as it is for an <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct_ex.md">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a> request.
        
            `PortNumber`

            The port number if MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set. Otherwise, this member is zero. If MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set, the <b>PathId</b> and <b>TargetId</b> values are taken from the embedded <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_direct_ex.md">SCSI_PASS_THROUGH_DIRECT_EX</a> structure.
        
            `Version`

            Should be zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddscsi.h (include Ntddscsi.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path_direct_ex.md">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT_EX</a>
</dt>
<dt>
<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct_ex.md">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a>
</dt>
<dt>
<a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_direct_ex.md">SCSI_PASS_THROUGH_DIRECT_EX</a>
</dt>
<dt>
<a href="..\srb\ns-srb-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MPIO_PASS_THROUGH_PATH_DIRECT_EX structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
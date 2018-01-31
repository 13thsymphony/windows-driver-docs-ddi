---
UID : NI:mountmgr.IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY
title : IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY
author : windows-driver-content
description : This IOCTL is identical in input and output to IOCTL_MOUNTMGR_QUERY_POINTS.
old-location : storage\ioctl_mountmgr_delete_points_dbonly.htm
old-project : storage
ms.assetid : 507e42a0-e5f6-4864-a665-d06eb4d1a77b
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_mountmgr_delete_points_dbonly, IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY control code [Storage Devices], IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY, mountmgr/IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY, k307_5b02ca9a-551e-42d1-a153-39a6f5d94141.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : mountmgr.h
req.include-header : Mountmgr.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PMOUNTDEV_UNIQUE_ID, MOUNTDEV_UNIQUE_ID"
---

# IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY IOCTL
This IOCTL is identical in input and output to <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_query_points.md">IOCTL_MOUNTMGR_QUERY_POINTS</a>. The difference is that <b>IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY</b> has the side effect of deleting the mount manager database entries for the triples returned. However, the mount manager does not delete the symbolic links corresponding to the database entries.

If the input to this IOCTL is ("\DosDevices\X:", <b>NULL</b>, <b>NULL</b>), where X is the current drive letter for the volume indicated in the input triple, the mount manager adds a special entry to its database indicating that the client does not require a drive letter. On subsequent reboots, the mount manager will not assign a default drive letter to the volume.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
See <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_query_points.md">IOCTL_MOUNTMGR_QUERY_POINTS</a>.

### Input Buffer Length
See <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_query_points.md">IOCTL_MOUNTMGR_QUERY_POINTS</a>.

### Output Buffer
See <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_query_points.md">IOCTL_MOUNTMGR_QUERY_POINTS</a>.

### Output Buffer Length
See <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_query_points.md">IOCTL_MOUNTMGR_QUERY_POINTS</a>.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
See <a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_query_points.md">IOCTL_MOUNTMGR_QUERY_POINTS</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | mountmgr.h (include Mountmgr.h) |
| **IRQL** |  |

## See Also

<a href="..\mountmgr\ni-mountmgr-ioctl_mountmgr_query_points.md">IOCTL_MOUNTMGR_QUERY_POINTS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
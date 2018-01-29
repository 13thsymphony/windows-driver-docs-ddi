---
UID : NS:ntddstor._PERSISTENT_RESERVE_COMMAND
title : _PERSISTENT_RESERVE_COMMAND
author : windows-driver-content
description : The PERSISTENT_RESERVE_COMMAND structure is used together with the IOCTL_STORAGE_PERSISTENT_RESERVE_IN and IOCTL_STORAGE_PERSISTENT_RESERVE_OUT requests to obtain and control information about persistent reservations and reservation keys that are active within a device server.
old-location : storage\persistent_reserve_command.htm
old-project : storage
ms.assetid : c7debd93-0fcd-43c5-a950-8154b62175bf
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : ntddstor/PPERSISTENT_RESERVE_COMMAND, PERSISTENT_RESERVE_COMMAND, *PPERSISTENT_RESERVE_COMMAND, PPERSISTENT_RESERVE_COMMAND structure pointer [Storage Devices], PPERSISTENT_RESERVE_COMMAND, ntddstor/PERSISTENT_RESERVE_COMMAND, storage.persistent_reserve_command, PERSISTENT_RESERVE_COMMAND structure [Storage Devices], _PERSISTENT_RESERVE_COMMAND, structs-general_4fe3d6f6-6e9f-41f5-915c-2636707f429c.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddstor.h
req.include-header : Ntddstor.h
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
req.typenames : "*PPERSISTENT_RESERVE_COMMAND, PERSISTENT_RESERVE_COMMAND"
---

# _PERSISTENT_RESERVE_COMMAND structure
The PERSISTENT_RESERVE_COMMAND structure is used together with the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_persistent_reserve_in.md">IOCTL_STORAGE_PERSISTENT_RESERVE_IN</a> and <a href="..\ntddstor\ni-ntddstor-ioctl_storage_persistent_reserve_out.md">IOCTL_STORAGE_PERSISTENT_RESERVE_OUT</a> requests to obtain and control information about persistent reservations and reservation keys that are active within a device server.

## Syntax
````
typedef struct _PERSISTENT_RESERVE_COMMAND {
  ULONG Version;
  ULONG Size;
  union {
    struct {
      UCHAR  ServiceAction  :5;
      UCHAR  Reserved1  :3;
      USHORT AllocationLength;
    } PR_IN;
    struct {
      UCHAR ServiceAction  :5;
      UCHAR Reserved1  :3;
      UCHAR Type  :4;
      UCHAR Scope  :4;
      UCHAR ParameterList[];
    } PR_OUT;
  };
} PERSISTENT_RESERVE_COMMAND, *PPERSISTENT_RESERVE_COMMAND;
````

## Members


`DUMMYUNIONNAME`



`Size`

The size of this structure.

`Version`

The version of this structure.

## Remarks
The behavior of the storage device when a SCSI Persistent Reserve In command or a SCSI Persistent Reserve Out command is received is described in the <a href="http://go.microsoft.com/fwlink/p/?linkid=153142">SCSI Primary Commands - 2 (SPC-2)</a> specification.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddstor.h (include Ntddstor.h) |

## See Also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_persistent_reserve_out.md">IOCTL_STORAGE_PERSISTENT_RESERVE_OUT</a>

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_persistent_reserve_in.md">IOCTL_STORAGE_PERSISTENT_RESERVE_IN</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PERSISTENT_RESERVE_COMMAND structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID : NS:iscsidef._ISCSI_TargetMapping
title : _ISCSI_TargetMapping
author : windows-driver-content
description : The ISCSI_TargetMapping structure maps a collection of logical unit numbers (LUNs) that are locally defined to a group of 64-bit iSCSI logical unit numbers.
old-location : storage\iscsi_targetmapping.htm
old-project : storage
ms.assetid : 9b8c5024-5d37-4f85-be00-1a60dd9ab323
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _ISCSI_TargetMapping, ISCSI_TargetMapping, *PISCSI_TargetMapping
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : iscsidef.h
req.include-header : Iscsidef.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : ISCSI_TargetMapping
req.alt-loc : iscsidef.h
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
req.typenames : ISCSI_TargetMapping, *PISCSI_TargetMapping
---

# _ISCSI_TargetMapping structure
The ISCSI_TargetMapping structure maps a collection of logical unit numbers (LUNs) that are locally defined to a group of 64-bit iSCSI logical unit numbers.

## Syntax
````
typedef struct _ISCSI_TargetMapping {
  ULONG         OSBus;
  ULONG         OSTarget;
  ULONGLONG     UniqueSessionId;
  ULONG         LUNCount;
  WCHAR         TargetName[223 + 1];
  BOOLEAN       FromPersistentLogin;
  ULONGLONG     Reserved;
  ISCSI_LUNList LUNList[1];
} ISCSI_TargetMapping, *PISCSI_TargetMapping;
````

## Members

        
            `FromPersistentLogin`

            A Boolean value that indicates whether the logon session is persistent. If this member is <b>TRUE</b>, the logon session is persistent and the system creates it automatically when the computer boots up. If this member is <b>FALSE</b>, the logon session is not persistent.
        
            `LUNCount`

            The number of LUNs that are associated with the remote target device.
        
            `LUNList`

            A <a href="..\iscsidef\ns-iscsidef-_iscsi_lunlist.md">ISCSI_LUNList</a> structure that holds a list of LUNs that are associated with the target device.
        
            `OSBus`

            The SCSI bus number (which is valid in the local operating system) that the remote target is mapped to. A value of 0xffffffff indicates that the miniport driver can associate any SCSI bus number with the target.
        
            `OSTarget`

            The SCSI target number (which is valid in the local operating system) that the remote target is mapped to. A value of 0xffffffff indicates that the miniport driver can pick any number to identify the remote target device.
        
            `Reserved`

            Reserved for Microsoft use only.
        
            `TargetName`

            A wide character string that indicates the target name.
        
            `UniqueSessionId`

            A 64-bit integer that uniquely identifies the session. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in their UniqueSessionId parameter. Do not confuse this value with the values in the ISID and TSID members.

    ## Remarks
        A 64-bit iSCSI LUN by itself does not uniquely identify the logical unit that it represents. However, the combination of an iSCSI LUN and the name of the target that the logical unit belongs to does provide a unique identification for that logical unit that is valid anywhere in the network. 

Management applications can use the ISCSI_TargetMapping structure to specify a local LUN number that can be assigned to the target LUN that the operating system finds during device enumerations.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | iscsidef.h (include Iscsidef.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>
</dt>
<dt>
<a href="..\iscsidef\ns-iscsidef-_iscsi_lunlist.md">ISCSI_LUNList</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561573">ISCSI_TargetMapping WMI Class</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_TargetMapping structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
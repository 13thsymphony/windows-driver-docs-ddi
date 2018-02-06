---
UID: NS:iscsicfg._MSiSCSI_BootConfiguration
title: "_MSiSCSI_BootConfiguration"
author: windows-driver-content
description: The MSiSCSI_BootConfiguration structure describes how the boot device is configured.
old-location: storage\msiscsi_bootconfiguration.htm
old-project: storage
ms.assetid: 3a4b55b1-977d-43fb-9968-7a734e04b21b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: structs-iSCSI_eb9ca716-5f5e-4bec-a4e0-e00d5a93b329.xml, *PMSiSCSI_BootConfiguration, MSiSCSI_BootConfiguration structure [Storage Devices], iscsicfg/MSiSCSI_BootConfiguration, MSiSCSI_BootConfiguration, _MSiSCSI_BootConfiguration, iscsicfg/PMSiSCSI_BootConfiguration, storage.msiscsi_bootconfiguration, PMSiSCSI_BootConfiguration structure pointer [Storage Devices], PMSiSCSI_BootConfiguration
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsicfg.h
req.include-header: Iscsicfg.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iscsicfg.h
apiname:
-	MSiSCSI_BootConfiguration
product: Windows
targetos: Windows
req.typenames: MSiSCSI_BootConfiguration, *PMSiSCSI_BootConfiguration
---

# _MSiSCSI_BootConfiguration structure
The MSiSCSI_BootConfiguration structure describes how the boot device is configured.

## Syntax
````
typedef struct _MSiSCSI_BootConfiguration {
  ULONGLONG          LUN;
  ULONGLONG          SecurityFlags;
  ULONG              UsernameSize;
  ULONG              PasswordSize;
  BOOLEAN            DiscoverBootDevice;
  WCHAR              InitiatorNode[223 + 1];
  WCHAR              TargetName[223 + 1];
  ISCSI_TargetPortal TargetPortal;
  ISCSI_LoginOptions LoginOptions;
  UCHAR              Username[1];
} MSiSCSI_BootConfiguration, *PMSiSCSI_BootConfiguration;
````

## Members


`DiscoverBootDevice`

A Boolean value that indicates whether the system should dynamically discover the boot device. If this member is <b>TRUE</b>, the system should dynamically discover the boot device.

`InitiatorNode`

The iSCSI name of the initiator node to use for connecting to the boot device. If this member is <b>NULL</b>, the HBA can choose any initiator node. The iSCSI name for the initiator uniquely identifies the initiator anywhere in the world. For more information about how to specify this name, see the <i>iSCSI </i>specification that is published by the Internet Engineering Task Force (IETF) of the IP storage working group.

`LoginOptions`

A <a href="..\iscsidef\ns-iscsidef-_iscsi_loginoptions.md">ISCSI_LoginOptions</a> structure that specifies the characteristics of the logon session to establish with the boot device.

`LUN`

The logical unit number (LUN) that identifies the logical unit on the target that functions as a boot device.

`PasswordSize`

The size, in bytes, of the string in <b>Password</b>.

`SecurityFlags`

A bitwise OR of security flags that indicate the security requirements of the boot device. For a list of possible flags for this member, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565399">SECURITY_FLAG_QUALIFIERS</a>.

`TargetName`

The iSCSI name for the target that contains the boot device.

`TargetPortal`

A <a href="..\iscsidef\ns-iscsidef-_iscsi_targetportal.md">ISCSI_TargetPortal</a> structure that specifies the portal to use for the connection.

`Username`

A variable length array of characters that specifies the user name to use with the challenge handshake authentication protocol (CHAP). The user name is also known as the <i>CHAP name</i> (CHAP_N). The initiator uses the CHAP name to authenticate the target.

`UsernameSize`

The size, in bytes, of the string in <b>Username</b>.

## Remarks
The WMI tool suite automatically generates a declaration of the MSiSCSI_BootConfiguration structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562979">MSiSCSI_BootConfiguration WMI Class</a> in <i>Config.mof</i>.It is optional that you implement this class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsicfg.h (include Iscsicfg.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562979">MSiSCSI_BootConfiguration WMI Class</a>

<a href="..\iscsidef\ns-iscsidef-_iscsi_targetportal.md">ISCSI_TargetPortal</a>

<a href="..\iscsidef\ns-iscsidef-_iscsi_loginoptions.md">ISCSI_LoginOptions</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565399">SECURITY_FLAG_QUALIFIERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_BootConfiguration structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
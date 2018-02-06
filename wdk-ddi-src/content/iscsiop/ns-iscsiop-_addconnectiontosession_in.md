---
UID: NS:iscsiop._AddConnectionToSession_IN
title: "_AddConnectionToSession_IN"
author: windows-driver-content
description: The AddConnectionToSession_IN structure holds input data for the AddConnectionToSession method, which is used to add a new connection to an already existing session.
old-location: storage\addconnectiontosession_in.htm
old-project: storage
ms.assetid: 7fcb0b87-1f9e-4956-a59a-cd83fa04e5db
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AddConnectionToSession_IN structure [Storage Devices], PAddConnectionToSession_IN structure pointer [Storage Devices], iscsiop/AddConnectionToSession_IN, AddConnectionToSession_IN, structs-iSCSI_4e238073-ca54-4da3-afcc-4b45e4da243f.xml, _AddConnectionToSession_IN, PAddConnectionToSession_IN, iscsiop/PAddConnectionToSession_IN, storage.addconnectiontosession_in, *PAddConnectionToSession_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
-	iscsiop.h
apiname:
-	AddConnectionToSession_IN
product: Windows
targetos: Windows
req.typenames: "*PAddConnectionToSession_IN, AddConnectionToSession_IN"
---

# _AddConnectionToSession_IN structure
The AddConnectionToSession_IN structure holds input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> method, which is used to add a new connection to an already existing session.

## Syntax
````
typedef struct _AddConnectionToSession_IN {
  ULONGLONG          UniqueAdapterId;
  ULONGLONG          UniqueSessionId;
  ULONGLONG          SecurityFlags;
  ULONG              PortNumber;
  ISCSI_LoginOptions LoginOptions;
  ISCSI_TargetPortal TargetPortal;
  ULONG              UsernameSize;
  ULONG              PasswordSize;
  ULONG              KeySize;
  UCHAR              Key[1];
} AddConnectionToSession_IN, *PAddConnectionToSession_IN;
````

## Members


`Key`

A variable-length array of characters that specifies the preshared key that is associated with the target IP address. The number of elements in the array is specified by the KeySize field.

`KeySize`

The preshared key size, in bytes.

`LoginOptions`

A <a href="..\iscsidef\ns-iscsidef-_iscsi_loginoptions.md">ISCSI_LoginOptions</a> structure that describes the characteristics of the target logon session that a connection will be added to.

`PasswordSize`

The password size, in bytes.

`PortNumber`

The number of the port from which to initiate the target logon session.

`SecurityFlags`

A bitwise OR of flags that indicate the security requirements of a target. For a list of possible values for this member, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565399">SECURITY_FLAG_QUALIFIERS</a>.

`TargetPortal`

A <a href="..\iscsidef\ns-iscsidef-_iscsi_targetportal.md">ISCSI_TargetPortal</a> structure that indicates which target portal to use to make the additional connection. The <b>AddConnectionToSession</b> method calls the <b>LoginToTarget</b> method to establish the new connection. If <b>LoginToTarget</b> fails with a status value of either ISCSC_TARGET_MOVED_PERMANENTLY or ISCSC_TARGET_MOVED_TEMPORARILY. <b>TargetPortal</b> will indicate, on output from <b>AddConnectionToSession</b>, the portal that the logon operation should be redirected to. For more information about the ISCSC_TARGET_MOVED_PERMANENTLY and ISCSC_TARGET_MOVED_TEMPORARILY status values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.

`UniqueAdapterId`

A 64-bit integer that uniquely identifies an adapter and a particular loaded instance of a storage miniport driver that manages the adapter. This identifier is unique, not only on the computer where the adapter is located, but also across the entire network.

`UniqueSessionId`

A 64-bit integer that uniquely identifies the session. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a> methods both return this value in their <i>UniqueSessionId</i> parameter. Do not confuse this value with the values in the ISID and TSID members.

`UsernameSize`

The username size, in bytes.

## Remarks
The iSCSI service requires this method. It is optional that you implement this method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="..\iscsidef\ns-iscsidef-_iscsi_loginoptions.md">ISCSI_LoginOptions</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563091">MSiSCSI_Operations WMI Class</a>

<a href="..\iscsiop\ns-iscsiop-_addconnectiontosession_out.md">AddConnectionToSession_OUT</a>

<a href="..\iscsidef\ns-iscsidef-_iscsi_targetportal.md">ISCSI_TargetPortal</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561599">LoginToTarget</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550121">AddConnectionToSession</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565399">SECURITY_FLAG_QUALIFIERS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AddConnectionToSession_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
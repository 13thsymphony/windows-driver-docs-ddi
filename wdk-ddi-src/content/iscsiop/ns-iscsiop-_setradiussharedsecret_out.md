---
UID : NS:iscsiop._SetRADIUSSharedSecret_OUT
title : "_SetRADIUSSharedSecret_OUT"
author : windows-driver-content
description : The SetRADIUSSharedSecret_OUT structure holds the output data for the SetRADIUSSharedSecret method.
old-location : storage\setradiussharedsecret_out.htm
old-project : storage
ms.assetid : 55be7611-3249-4109-a142-c0115dfebb98
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : structs-iSCSI_497fc66e-8a5d-4390-9229-622b359776bc.xml, SetRADIUSSharedSecret_OUT, storage.setradiussharedsecret_out, _SetRADIUSSharedSecret_OUT, iscsiop/SetRADIUSSharedSecret_OUT, *PSetRADIUSSharedSecret_OUT, PSetRADIUSSharedSecret_OUT structure pointer [Storage Devices], SetRADIUSSharedSecret_OUT structure [Storage Devices], PSetRADIUSSharedSecret_OUT, iscsiop/PSetRADIUSSharedSecret_OUT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : iscsiop.h
req.include-header : Iscsiop.h
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
req.typenames : "*PSetRADIUSSharedSecret_OUT, SetRADIUSSharedSecret_OUT"
---

# _SetRADIUSSharedSecret_OUT structure
The SetRADIUSSharedSecret_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565815">SetRADIUSSharedSecret</a> method.

## Syntax
````
typedef struct _SetRADIUSSharedSecret_OUT {
  ULONG Status;
} SetRADIUSSharedSecret_OUT, *PSetRADIUSSharedSecret_OUT;
````

## Members


`Status`

On output, the status of the <b>SetRADIUSSharedSecret</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.

## Remarks
You must implement this method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsiop.h (include Iscsiop.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>

<a href="..\iscsiop\ns-iscsiop-_setradiussharedsecret_in.md">SetRADIUSSharedSecret_IN</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565815">SetRADIUSSharedSecret</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetRADIUSSharedSecret_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
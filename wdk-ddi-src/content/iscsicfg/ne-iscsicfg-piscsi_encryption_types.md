---
UID: NE.iscsicfg.PISCSI_ENCRYPTION_TYPES
title: PISCSI_ENCRYPTION_TYPES
author: windows-driver-content
description: The ISCSI_ENCRYPTION_TYPES enumeration indicates the type of encryption that is supported.
old-location: storage\iscsi_encryption_types.htm
old-project: storage
ms.assetid: f1c7a13b-511a-4e9d-a0e6-9fb27126b1d2
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: PISCSI_ENCRYPTION_TYPES, PISCSI_ENCRYPTION_TYPES, ISCSI_ENCRYPTION_TYPES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: iscsicfg.h
req.include-header: Iscsicfg.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ISCSI_ENCRYPTION_TYPES
req.alt-loc: iscsicfg.h
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
---

# PISCSI_ENCRYPTION_TYPES enumeration



## -description
The ISCSI_ENCRYPTION_TYPES enumeration indicates the type of encryption that is supported. 



## -syntax

````
typedef enum  { 
  ISCSI_ENCRYPT_NONE            = 0,
  ISCSI_ENCRYPT_3DES_HMAC_SHA1  = 1,
  ISCSI_ENCRYPT_AES_CTR         = 2
} ISCSI_ENCRYPTION_TYPES, *PISCSI_ENCRYPTION_TYPES;
````


## -enum-fields

### -field ISCSI_ENCRYPT_NONE

No type of encryption is supported. 


### -field ISCSI_ENCRYPT_3DES_HMAC_SHA1

The initiator or target supports triple data encryption standard (DES), hashed message authentication code (HMAC), and the secure hash algorithm, version 1. 


### -field ISCSI_ENCRYPT_AES_CTR

The initiator or target supports advanced encryption standard (AES) counter mode (CTR). 


## -remarks
The ISCSI_ENCRYPTION_TYPES enumeration is used with the <a href="storage.msiscsi_securitycapabilities_wmi_class">MSiSCSI_SecurityCapabilities WMI Class</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iscsicfg.h (include Iscsicfg.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.msiscsi_securitycapabilities">MSiSCSI_SecurityCapabilities</a>
</dt>
<dt>
<a href="storage.msiscsi_securitycapabilities_wmi_class">MSiSCSI_SecurityCapabilities WMI Class</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_ENCRYPTION_TYPES enumeration%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


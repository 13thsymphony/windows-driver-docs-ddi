---
UID: NS.ISCSICFG._MSISCSI_SECURITYCAPABILITIES
title: _MSiSCSI_SecurityCapabilities
author: windows-driver-content
description: The MSiSCSI_SecurityCapabilities structure describes the security capabilities of an initiator.
old-location: storage\msiscsi_securitycapabilities.htm
old-project: storage
ms.assetid: a385283a-7b24-43aa-b291-541bfd6a91a6
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _MSiSCSI_SecurityCapabilities, MSiSCSI_SecurityCapabilities, PMSiSCSI_SecurityCapabilities, *PMSiSCSI_SecurityCapabilities
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
req.alt-api: MSiSCSI_SecurityCapabilities
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

# _MSiSCSI_SecurityCapabilities structure



## -description
The MSiSCSI_SecurityCapabilities structure describes the security capabilities of an initiator. 



## -syntax

````
typedef struct _MSiSCSI_SecurityCapabilities {
  BOOLEAN ProtectiScsiTraffic;
  BOOLEAN ProtectiSNSTraffic;
  BOOLEAN CertificatesSupported;
  ULONG   EncryptionAvailableCount;
  ULONG   EncryptionAvailable[1];
} MSiSCSI_SecurityCapabilities, *PMSiSCSI_SecurityCapabilities;
````


## -struct-fields

### -field ProtectiScsiTraffic

A Boolean value that indicates whether the initiator can use IPsec to protect iSCSI traffic. If this member is <b>TRUE</b>, the initiator can use IPsec to protect iSCSI traffic. If <b>FALSE</b>, the initiator cannot use IPsec.


### -field ProtectiSNSTraffic

A Boolean value that indicates whether the initiator can use IPsec to protect iSNS traffic. If this member is <b>TRUE</b>, the initiator can use IPsec to protect iSNS traffic. If <b>FALSE</b>, the initiator cannot use IPsec.


### -field CertificatesSupported

A Boolean value that indicates whether the initiator supports certificates. If this member is <b>TRUE</b>, the initiator supports certificates. If this member is <b>FALSE</b>, the initiatiator does not support certificates.


### -field EncryptionAvailableCount

The number of encryption types that the initiator supports. 


### -field EncryptionAvailable

A variable length array of <a href="storage.iscsi_encryption_types">ISCSI_ENCRYPTION_TYPES</a> structures, which indicate types of encryption that the initiator supports. 


## -remarks
The WMI tool suite automatically generates a declaration of the MSiSCSI_SecurityCapabilities structure when it compiles the <a href="storage.msiscsi_securitycapabilities_wmi_class">MSiSCSI_SecurityCapabilities WMI Class</a> in <i>Config.mof</i>. 

Initiators that support IPsec must implement the MSiSCSI_SecurityCapabilities class. 

Initiators must register the MSiSCSI_SecurityCapabilities class using the name of the physical device object (PDO) for the HBA. You must implement this class if the adapter supports IPsec.


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
<a href="storage.iscsi_encryption_types">ISCSI_ENCRYPTION_TYPES</a>
</dt>
<dt>
<a href="storage.msiscsi_securitycapabilities_wmi_class">MSiSCSI_SecurityCapabilities WMI Class</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_SecurityCapabilities structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NS.iscsifnd._ISCSI_DiscoveredTargetPortal2
title: ISCSI_DiscoveredTargetPortal2
author: windows-driver-content
description: The ISCSI_DiscoveredTargetPortal2 structure provides information that is associated with a discovered target portal.
old-location: storage\iscsi_discoveredtargetportal2.htm
old-project: storage
ms.assetid: 68128d39-2490-4c6b-8780-e5aa542a4e3d
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: ISCSI_DiscoveredTargetPortal2, ISCSI_DiscoveredTargetPortal2, *PISCSI_DiscoveredTargetPortal2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsifnd.h
req.include-header: Iscsifnd.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ISCSI_DiscoveredTargetPortal2
req.alt-loc: iscsifnd.h
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
req.iface: 
---

# ISCSI_DiscoveredTargetPortal2 structure



## -description
<p>The ISCSI_DiscoveredTargetPortal2 structure provides information that is associated with a discovered target portal. </p>


## -syntax

````
typedef struct _ISCSI_DiscoveredTargetPortal2 {
  USHORT           Socket;
  ISCSI_IP_Address Address;
  ULONG            SecurityBitmap;
  ULONG            KeySize;
  UCHAR            Key[1];
} ISCSI_DiscoveredTargetPortal2, *PISCSI_DiscoveredTargetPortal2;
````


## -struct-fields
<dl>

### -field <b>Socket</b>

<dd>
<p>The socket number of the portal. </p>
</dd>

### -field <b>Address</b>

<dd>
<p>The network address of the portal. </p>
</dd>

### -field <b>SecurityBitmap</b>

<dd>
<p>A bitmap, which is defined in the <i>iSNS specification</i>, that indicates the security characteristics of logon connections that are made to this target portal. The following table describes possible security flag values. </p>
<table>
<tr>
<th>Security flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>ISCSI_SECURITY_FLAG_TUNNEL_MODE_PREFERRED</p>
</td>
<td>
<p>The initiator HBA should log on targets by using IPsec tunnel mode. If this bit is not set IPsec tunnel mode is not required. </p>
</td>
</tr>
<tr>
<td>
<p>ISCSI_SECURITY_FLAG_TRANSPORT_MODE_PREFERRED</p>
</td>
<td>
<p>The initiator HBA should log on targets by using IPsec transport mode. If this bit is not set IPsec transport mode is not required. </p>
</td>
</tr>
<tr>
<td>
<p>ISCSI_SECURITY_FLAG_PFS_ENABLED</p>
</td>
<td>
<p>The initiator HBA should log on targets with Perfect Forward Secrecy (PFS) mode enabled; otherwise, the initiator HBA should make the session connection with PFS mode disabled. </p>
</td>
</tr>
<tr>
<td>
<p>ISCSI_SECURITY_FLAG_AGGRESSIVE_MODE_ENABLED</p>
</td>
<td>
<p>The initiator HBA should log on targets with aggressive mode enabled. If this bit is not set the initiator HBA should make the session connection with aggressive mode disabled.</p>
</td>
</tr>
<tr>
<td>
<p>ISCSI_SECURITY_FLAG_MAIN_MODE_ENABLED</p>
</td>
<td>
<p>The initiator HBA should log on targets with main mode enabled. If this bit is not set the initiator HBA should make the session connection with main mode disabled. </p>
</td>
</tr>
<tr>
<td>
<p>ISCSI_SECURITY_FLAG_IKE_IPSEC_ENABLED</p>
</td>
<td>
<p>The initiator HBA should log on targets with the IKE/IPsec protocol enabled. If this bit is not set the IKE/IPsec protocol is disabled.</p>
</td>
</tr>
<tr>
<td>
<p>ISCSI_SECURITY_FLAG_VALID</p>
</td>
<td>
<p>The other mask values are valid. If this bit is not set security flags are not specified.. </p>
</td>
</tr>
</table>
<p> </p>
<p>For more information about how to configure the default security characteristics that are assigned of the target portal in the registry, see the Remarks section.</p>
</dd>

### -field <b>KeySize</b>

<dd>
<p>The size, in bytes, of the encryption key in the <b>Key</b> member.</p>
</dd>

### -field <b>Key</b>

<dd>
<p>A variable-length array of characters that contains the encryption key that is associated with the portal address.</p>
</dd>
</dl>

## -remarks
<p>The ISCSI_DiscoveredTargetPortal2 structure is a superset of the information that is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561509">ISCSI_DiscoveredTargetPortal</a> structure, which only defines the target portal address. In addition to the network address of the target portal, the ISCSI_DiscoveredTargetPortal2 structure contains information about the target portal's security characteristics.</p>

<p>If the iSNS server does not assign a security bitmap to the target portal, the operating system associates the bitmap in the <b>DefaultSecurityBitmap</b> registry value with the portal. The <b>DefaultSecurityBitmap</b> registry value is located under the following registry key: <b>HKLM\Software\Microsoft\Windows NT\Current Version\ISCSI\Discovery Values</b>. </p>

<p>The default security bitmap is useful in cases where the target portal is configured for IPsec but does not support iSNS. </p>

<p>In general, management applications should use the iSCSI client PSKey command to configure the security bitmap for a target portal. But if there are a large number of portals that have the same security bitmap, the default security bitmap is a good way to automatically assign the same bitmap to all portals.</p>

<p>The WMI tool suite automatically generates a declaration of the ISCSI_DiscoveredTargetPortal2 structure when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561524">ISCSI_DiscoveredTargetPortal WMI Class</a> in <i>Discover.mof</i>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Iscsifnd.h (include Iscsifnd.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561509">ISCSI_DiscoveredTargetPortal</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561524">ISCSI_DiscoveredTargetPortal WMI Class</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561574">ISCSI_TargetPortal</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_DiscoveredTargetPortal2 structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

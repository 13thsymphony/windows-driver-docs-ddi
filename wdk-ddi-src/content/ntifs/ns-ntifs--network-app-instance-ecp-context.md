---
UID: NS.ntifs._NETWORK_APP_INSTANCE_ECP_CONTEXT
title: NETWORK_APP_INSTANCE_ECP_CONTEXT
author: windows-driver-content
description: The NETWORK_APP_INSTANCE_ECP_CONTEXT structure is an Extra Create Parameter (ECP) and contains an application instance identifier to associate with a file.
old-location: ifsk\network_app_instance_ecp_context.htm
old-project: ifsk
ms.assetid: ADB7550F-9191-4EAA-BEBA-0D0D29EC7B03
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: NETWORK_APP_INSTANCE_ECP_CONTEXT, NETWORK_APP_INSTANCE_ECP_CONTEXT, *PNETWORK_APP_INSTANCE_ECP_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NETWORK_APP_INSTANCE_ECP_CONTEXT
req.alt-loc: Ntifs.h
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

# NETWORK_APP_INSTANCE_ECP_CONTEXT structure



## -description
<p>The <b>NETWORK_APP_INSTANCE_ECP_CONTEXT</b> structure is an Extra Create Parameter (ECP) and contains an application instance identifier  to associate with a file. This structure is used to identify the files opened for a failover cluster client application when that application resumes access to its files on another node. </p>


## -syntax

````
typedef struct _NETWORK_APP_INSTANCE_ECP_CONTEXT {
  USHORT Size;
  USHORT Reserved;
  GUID   AppInstanceID;
} NETWORK_APP_INSTANCE_ECP_CONTEXT, *PNETWORK_APP_INSTANCE_ECP_CONTEXT;
````


## -struct-fields
<dl>

### -field <b>Size</b>

<dd>
<p>Size of this structure. This member is set to <b>sizeof</b>(NETWORK_APP_INSTANCE_ECP_CONTEXT).</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved. Must be set to zero.</p>
</dd>

### -field <b>AppInstanceID</b>

<dd>
<p>A unique instance identifier for a failover cluster client application. This is a GUID that associates an application  to file opened on a failover cluster node.</p>
</dd>
</dl>

## -remarks
<p>When  failover to a secondary node in a server cluster occurs, a cluster client application needs resumed access to the files it first opened on the failed node. The Cluster Client Failover infrastructure prevents sharing violations for the application's files on the failover node by validating its access to those files. Access is granted to the files the on the failover node having the same application instance identifier as the files opened on other node had  prior to failover. The instance identifier is found  in a <b>NETWORK_APP_INSTANCE_ECP_CONTEXT</b> structure in a file's ECP list.</p>

<p>For example, a file system filter driver will allocate a <b>NETWORK_APP_INSTANCE_ECP_CONTEXT</b> with the unique application instance GUID. The context structure is inserted into the ECP list of a file when it is created or opened. The cluster nodes cache the instance identifier from the ECP when processing the network file system create request. On failover, the resuming node can match the application to its set of opened files and grant access.</p>

<p>The <b>NETWORK_APP_INSTANCE_ECP_CONTEXT</b> is identified in an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a> by <b>GUID_ECP_NETWORK_APP_INSTANCE</b>. This and other system-defined identifiers are described in <a href="ifsk.system_defined_ecps">System-Defined ECPs</a>.</p>

<p>For information about how to use ECPs to associate extra information with a file when the file is created, see <a href="ifsk.using_extra_create_parameters_with_an_irp_mj_create_operation">Using Extra Create Parameters with an IRP_MJ_CREATE Operation</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>This structure is available in Windows 8 and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20NETWORK_APP_INSTANCE_ECP_CONTEXT structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

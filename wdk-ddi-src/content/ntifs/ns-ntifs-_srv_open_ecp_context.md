---
UID: NS.NTIFS._SRV_OPEN_ECP_CONTEXT
title: _SRV_OPEN_ECP_CONTEXT
author: windows-driver-content
description: The SRV_OPEN_ECP_CONTEXT structure is used by a server to conditionally open files in response to client requests.
old-location: ifsk\srv_open_ecp_context.htm
old-project: ifsk
ms.assetid: 6860f512-758d-4a75-88e4-17310b3e6349
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _SRV_OPEN_ECP_CONTEXT, SRV_OPEN_ECP_CONTEXT, *PSRV_OPEN_ECP_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SRV_OPEN_ECP_CONTEXT
req.alt-loc: ntifs.h
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

# _SRV_OPEN_ECP_CONTEXT structure



## -description
The SRV_OPEN_ECP_CONTEXT structure is used by a server to conditionally open files in response to client requests. 



## -syntax

````
typedef struct _SRV_OPEN_ECP_CONTEXT {
  PUNICODE_STRING       ShareName;
  PSOCKADDR_STORAGE_NFS SocketAddress;
  BOOLEAN               OplockBlockState;
  BOOLEAN               OplockAppState;
  BOOLEAN               OplockFinalState;
} SRV_OPEN_ECP_CONTEXT, *PSRV_OPEN_ECP_CONTEXT;
````


## -struct-fields

### -field ShareName

A pointer to a <a href="kernel.unicode_string">UNICODE_STRING</a> structure that supplies the share name for the server that contains the files to be open. 


### -field SocketAddress

A pointer to a <a href="..\ntifs\ns-ntifs-sockaddr_storage.md">SOCKADDR_STORAGE</a> structure that specifies the transport address of a client computer. This client originates the open file request. 


### -field OplockBlockState

A Boolean value that indicates whether the Server Message Block (SMB) server blocks the open thread that is waiting for the oplock break. <b>TRUE</b> indicates that the open thread is in the blocking state and <b>FALSE</b> otherwise. 


### -field OplockAppState

A Boolean value that indicates whether the SMB server requests an oplock with the current open thread. Set to <b>TRUE</b> to request the oplock and <b>FALSE</b> otherwise. 


### -field OplockFinalState

A Boolean value that indicates whether a file-open operation is the final file-open operation to request the oplock. <b>TRUE</b> indicates the final file-open operation to obtain the oplock and <b>FALSE</b> indicates otherwise. 


## -remarks
The file-system stack can determine whether SRV_OPEN_ECP_CONTEXT is attached to the create file request. The file-system stack can then use the information in SRV_OPEN_ECP_CONTEXT to determine which client requested that the file be opened, and why it requested it. For information about how to retrieve the SRV_OPEN_ECP_CONTEXT extra information that is attached to a create file request, see <a href="ifsk.using_ecps_to_process_irp_mj_create_operations_in_a_file_system_filter#retrieving_ecps#retrieving_ecps">Retrieving ECPs</a>. 

The SRV_OPEN_ECP_CONTEXT structure is read-only. You should use it to retrieve information about a server open ECP only. For more information about this issue, see <a href="ifsk.system_defined_ecps">System-Defined ECPs</a>.

The oplock state values (<b>OplockBlockState</b>, <b>OplockAppState</b>, and <b>OplockFinalState</b>) are used with oplock breaking logic for system management for SMB and SMB2. 


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
This structure is available starting with Windows 7. 

</td>
</tr>
<tr>
<th width="30%">
Header

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
<a href="..\ntifs\ns-ntifs-sockaddr_storage.md">SOCKADDR_STORAGE</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SRV_OPEN_ECP_CONTEXT structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


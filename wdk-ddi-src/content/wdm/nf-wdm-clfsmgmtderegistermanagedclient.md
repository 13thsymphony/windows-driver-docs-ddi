---
UID: NF:wdm.ClfsMgmtDeregisterManagedClient
title: ClfsMgmtDeregisterManagedClient function
author: windows-driver-content
description: The ClfsMgmtDeregisterManagedClient routine removes the connection between a client and a log, so that the client no longer manages the log.
old-location: kernel\clfsmgmtderegistermanagedclient.htm
old-project: kernel
ms.assetid: 5dee3b70-9c8d-420d-86f9-9795b4d8b1e8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ClfsMgmtDeregisterManagedClient, ClfsMgmtDeregisterManagedClient routine [Kernel-Mode Driver Architecture], Clfs_management_6a802f4a-8157-42c8-8eda-740a1207714a.xml, kernel.clfsmgmtderegistermanagedclient, wdm/ClfsMgmtDeregisterManagedClient
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
-	ClfsMgmtDeregisterManagedClient
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ClfsMgmtDeregisterManagedClient function
The <b>ClfsMgmtDeregisterManagedClient</b> routine removes the connection between a client and a log, so that the client no longer manages the log.

## Syntax

````
NTSTATUS ClfsMgmtDeregisterManagedClient(
  _In_ CLFS_MGMT_CLIENT Client
);
````

## Parameters

`ClientCookie`

TBD


## Return Value

The <b>ClfsMgmtDeregisterManagedClient</b> routine returns one of the following NTSTATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The client is no longer associated with the log.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
CLFS management was not able to deregister the client.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A <b>NULL</b> value was supplied for the <i>Client</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
The value that  was supplied for the <i>Client</i> parameter does not represent a valid client.

</td>
</tr>
</table>

## Remarks

After calling the <b>ClfsMgmtDeregisterManagedClient</b> routine, a client's callback functions will no longer be invoked.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | Clfs.lib |
| **DLL** | Clfs.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\wdm\nf-wdm-clfsmgmtregistermanagedclient.md">ClfsMgmtRegisterManagedClient</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsMgmtDeregisterManagedClient routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
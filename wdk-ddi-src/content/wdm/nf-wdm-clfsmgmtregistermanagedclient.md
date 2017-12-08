---
UID: NF.wdm.ClfsMgmtRegisterManagedClient
title: ClfsMgmtRegisterManagedClient function
author: windows-driver-content
description: The ClfsMgmtRegisterManagedClient routine creates a client that will manage a CLFS log.
old-location: kernel\clfsmgmtregistermanagedclient.htm
old-project: kernel
ms.assetid: 6f450117-9bd2-4021-b8f1-393db5784136
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: ClfsMgmtRegisterManagedClient
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ClfsMgmtRegisterManagedClient
req.alt-loc: Clfs.sys,Ext-MS-Win-fs-clfs-l1-1-0.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# ClfsMgmtRegisterManagedClient function



## -description
The <b>ClfsMgmtRegisterManagedClient</b> routine creates a client that will manage a CLFS log.


## -syntax

````
NTSTATUS ClfsMgmtRegisterManagedClient(
  _In_  PLOG_FILE_OBJECT               LogFile,
  _In_  PCLFS_MGMT_CLIENT_REGISTRATION RegistrationData,
  _Out_ PCLFS_MGMT_CLIENT              Client
);
````


## -parameters

### -param LogFile [in]

A pointer to a <a href="kernel.log_file_object">LOG_FILE_OBJECT</a> structure that represents the CLFS log stream that the client created by <b>ClfsMgmtRegisterManagedClient</b> will manage.

### -param RegistrationData [in]

An instance of the <a href="kernel.clfs_mgmt_client_registration">CLFS_MGMT_CLIENT_REGISTRATION</a> structure that contains the functions that will be used to manage the log.

### -param Client [out]

A pointer to the client.

## -returns
The <b>ClfsMgmtRegisterManagedClient</b> routine returns one of the following NTSTATUS values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>A client has been created to manage the log.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>CLFS management was not able to create a client to manage the log. 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There is insufficient memory to complete the operation.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An input parameter is invalid.

 

This routine might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS Values</a>.

## -remarks
The <i>Client</i> parameter that  is provided by the <b>ClfsMgmtRegisterManagedClient</b> routine is a required parameter for other CLFS management functions. You should store this value for later use.

A client application must be ready for its callback routine to be called as soon as it calls the <b>ClfsMgmtRegisterManagedClient</b> routine.

More than one client can register with a log stream.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Clfs.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>Clfs.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= APC_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.clfs_mgmt_client_registration">CLFS_MGMT_CLIENT_REGISTRATION</a>
</dt>
<dt>
<a href="kernel.log_file_object">LOG_FILE_OBJECT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsMgmtRegisterManagedClient routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

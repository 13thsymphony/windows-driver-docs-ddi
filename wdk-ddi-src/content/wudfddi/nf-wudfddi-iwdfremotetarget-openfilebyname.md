---
UID: NF:wudfddi.IWDFRemoteTarget.OpenFileByName
title: IWDFRemoteTarget::OpenFileByName method
author: windows-driver-content
description: The OpenFileByName method opens a remote I/O target that is a file.
old-location: wdf\iwdfremotetarget_openfilebyname.htm
old-project: wdf
ms.assetid: 7f0cef78-3edc-434b-af70-39694776e8a7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFRemoteTarget, IWDFRemoteTarget::OpenFileByName, OpenFileByName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IWDFRemoteTarget.OpenFileByName
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFRemoteTarget::OpenFileByName method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OpenFileByName</b> method opens a <a href="wdf.general_i_o_targets_in_umdf">remote I/O target</a> that is a file.



## -syntax

````
HRESULT OpenFileByName(
  [in]           PCWSTR                      pszFileName,
  [in]           DWORD                       DesiredAccess,
  [in, optional] PUMDF_IO_TARGET_OPEN_PARAMS pOpenParams
);
````


## -parameters

### -param pszFileName [in]

A pointer to a caller-supplied, <b>null</b>-terminated string that represents the name of the file to open. For more information about this member, see the <i>FileName</i> parameter of <a href="http://go.microsoft.com/fwlink/p/?linkid=152795">CreateFile</a> in the Windows SDK.


### -param DesiredAccess [in]

A bitmask that specifies the caller's desired access to the file. For more information about this member, see the <i>dwDesiredAccess</i> parameter of <a href="http://go.microsoft.com/fwlink/p/?linkid=152795">CreateFile</a> in the Windows SDK.


### -param pOpenParams [in, optional]

A pointer to a caller-allocated <a href="..\wudfddi\ns-wudfddi-_umdf_io_target_open_params.md">UMDF_IO_TARGET_OPEN_PARAMS</a> structure that contains additional parameters. This parameter is optional and can be <b>NULL</b>.


## -returns
<b>OpenFileByName</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following value:
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>The framework's attempt to allocate memory failed. 

 

This method might return one of the other values that Winerror.h contains.



The framework's <a href="https://msdn.microsoft.com/e84993e1-da10-4041-8fc7-7f40806ee454">verifier</a> reports an error if the framework cannot open the file.


## -remarks
Your driver can use <b>OpenFileByName</b> to open a file, if the driver stack to which your driver belongs does not support the file's device. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff558930">IWDFFileHandleTargetFactory::CreateFileHandleTarget</a> to open a file, if the driver stack to which your driver belongs does support the file's device.

The specified file must be accessible by the account that loaded the UMDF-based driver, which is typically the Local Service account. However, if the driver uses <a href="https://msdn.microsoft.com/368c6741-b51a-4629-8ae6-a7848c07c0fc">impersonation</a> when it calls <b>OpenFileByName</b>, the file must be accessible by the impersonated account.

Do not call <b>OpenFileByName</b> to open a remote target to a control device object. Instead, open the control device directly by calling <a href="http://go.microsoft.com/fwlink/p/?linkid=152795">CreateFile</a>.

For more information about the <b>OpenFileByName</b> method and remote I/O targets, see <a href="https://msdn.microsoft.com/46fac165-3afd-4481-b68d-8d3474e0ff52">General I/O Targets in UMDF</a>.

The following code example creates a remote target object and opens an existing file with read-only access.


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfremotetarget.md">IWDFRemoteTarget</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556928">IWDFDevice2::CreateRemoteTarget</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560276">IWDFRemoteTarget::OpenRemoteInterface</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFRemoteTarget::OpenFileByName method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


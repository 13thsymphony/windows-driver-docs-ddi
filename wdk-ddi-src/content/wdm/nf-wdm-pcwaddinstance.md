---
UID: NF.wdm.PcwAddInstance
title: PcwAddInstance function
author: windows-driver-content
description: The PcwAddInstance function adds the specified instance of the counter set to the consumer buffer.
old-location: devtest\pcwaddinstance.htm
old-project: devtest
ms.assetid: 041761dd-ce52-4018-a226-c5181858326c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcwAddInstance
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PcwAddInstance
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=APC_LEVEL
req.product: Windows 10 or later.
---

# PcwAddInstance function



## -description
The <b>PcwAddInstance</b> function adds the specified instance of the counter set to the consumer buffer. 



## -syntax

````
NTSTATUS PcwAddInstance(
  _In_ PPCW_BUFFER      Buffer,
  _In_ PCUNICODE_STRING Name,
  _In_ ULONG            Id,
  _In_ ULONG            Count,
  _In_ PPCW_DATA        Data
);
````


## -parameters

### -param Buffer [in]

A pointer to the consumer buffer to which the instance of the counter set will be added. Depending on the purpose of the buffer, the function either adds an instance or collects data. 


### -param Name [in]

A pointer to the Unicode string that contains the name of the instance of the counter set.


### -param Id [in]

A numeric value that specifies the <i>Id</i> (identifier) associated with the instance of the counter set.


### -param Count [in]

The number of data blocks associated with this instance.


### -param Data [in]

A pointer to an array of data blocks containing the counter values of this instance.


## -returns
<b>PcwAddInstance</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The instance was successfully added to the buffer.
<dl>
<dt><b>STATUS_INVALID_BUFFER_SIZE</b></dt>
</dl>One of the provider data blocks is too small. For example, suppose that during the call to <a href="devtest.pcwregister">PcwRegister</a>, the provider specifies that counter <i>X</i> is at offset 100 of the first data block of size 4 bytes. If the call to <b>PcwAddInstance</b> specifies that the first data block is 50 bytes, this error status is returned.

 


## -remarks
The <b>PcwAddInstance</b> function either adds an instance or collects data depending on the purpose of the buffer. The purpose of the buffer is defined by the type of callback. The <b>PcwAddInstance</b> function is called from a <a href="..\wdm\nc-wdm-pcw_callback.md">PcwCallback</a> routine when the reason is either to collect data or to enumerate instances. You can get the <i>Buffer</i> from the <i>Info</i> parameter for the <i>PcwCallback</i> routine


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h or Ntddk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nc-wdm-pcw_callback.md">PcwCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20PcwAddInstance function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


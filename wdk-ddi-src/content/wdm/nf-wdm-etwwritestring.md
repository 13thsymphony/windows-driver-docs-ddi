---
UID: NF:wdm.EtwWriteString
title: EtwWriteString function
author: windows-driver-content
description: The EventWriteString function is a tracing function that you can use when no sophisticated data is required. This function is similar to a debug print statement.
old-location: devtest\etwwritestring.htm
old-project: devtest
ms.assetid: 25de7729-f43f-4d16-a379-e1cb1ab8616c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: EtwWriteString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EtwWriteString
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
req.irql: Any level (See Comments section.)
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# EtwWriteString function



## -description
The <b>EventWriteString</b> function is a tracing function that you can use when no sophisticated data is required. This function is similar to a debug print statement. 



## -syntax

````
NTSTATUS EtwWriteString(
  _In_     REGHANDLE RegHandle,
  _In_     UCHAR     Level,
  _In_     ULONGLONG Keyword,
  _In_opt_ LPCGUID   ActivityId,
  _In_     PCWSTR    String
);
````


## -parameters

### -param RegHandle [in]

A Pointer to the event provider registration handle, which is returned by the <b>EtwRegister</b> function if the event provider registration is successful.


### -param Level [in]

The level at which the event is active.  


### -param Keyword [in]

The keyword for the event. A keyword is a bitmask that makes general statements about the category of the event or error. Because the keyword is a bitmask, you can apply more than one keyword to a single event. You can define the keywords and bit positions, or you can use Windows-standard keywords, or you can use combination of your own keywords and the Windows keywords.


### -param ActivityId [in, optional]

The identifier that indicates the activity associated with the event. The <i>ActivityId</i> provides a way to group related events and is used in end-to-end tracing. This identifier is optional and can be <b>NULL</b>.


### -param String [in]

A null-terminated string (WCHAR). 


## -returns
The function returns STATUS_SUCCESS if the event is published successfully.


## -remarks
Because the string produced by <b>EventWriteString</b> function is not localizable, this function is not recommended for use in production code. This function should not be used to log highly visible events.

You can call <b>EtwWriteString</b> at any IRQL. However, when IRQL is greater than APC_LEVEL, any data passed to the <b>EtwWrite</b>, <a href="..\wdm\nf-wdm-etwwriteex.md">EtwWriteEx</a>, <b>EtwWriteString</b>,  and <b>EtwWriteTransfer</b> functions must not be pageable. That is, any kernel-mode routine that is running at IRQL greater than APC_LEVEL cannot access pageable memory. Data passed to the <b>EtwWrite</b>, <b>EtwWriteEx</b>, <b>EtwWriteString</b>, and <b>EtwWriteTransfer</b> functions must reside in system-space memory, regardless of what the IRQL is.


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
Available in Windows Vista and later versions of Windows.

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
Any level (See Comments section.)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-etwwrite.md">EtwWrite</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-etwwriteex.md">EtwWriteEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-etwwritetransfer.md">EtwWriteTransfer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20EtwWriteString function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


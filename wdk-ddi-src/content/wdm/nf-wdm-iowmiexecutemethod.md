---
UID: NF.wdm.IoWMIExecuteMethod
title: IoWMIExecuteMethod function
author: windows-driver-content
description: The IoWMIExecuteMethod routine runs a WMI class method on the specified WMI data block instance.
old-location: kernel\iowmiexecutemethod.htm
old-project: kernel
ms.assetid: 462165e5-2823-4559-bd3e-18850d442cdb
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IoWMIExecuteMethod
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoWMIExecuteMethod
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
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# IoWMIExecuteMethod function



## -description
The <b>IoWMIExecuteMethod</b> routine runs a WMI class method on the specified WMI data block instance.



## -syntax

````
NTSTATUS IoWMIExecuteMethod(
  _In_    PVOID           DataBlockObject,
  _In_    PUNICODE_STRING InstanceName,
  _In_    ULONG           MethodId,
  _In_    ULONG           InBufferSize,
  _Inout_ PULONG          OutBufferSize,
  _Inout_ PUCHAR          InOutBuffer
);
````


## -parameters

### -param DataBlockObject [in]

Pointer to a WMI data block object. The caller opens the data block object for the WMI class with <a href="kernel.iowmiopenblock">IoWMIOpenBlock</a>. The object must be opened with the WMIGUID_EXECUTE access right.


### -param InstanceName [in]

Specifies the name of the instance of the data block. This value corresponds to the value of the <b>InstanceName</b> property for the block.


### -param MethodId [in]

Specifies the method item ID for the method to be set. The value of this parameter corresponds to the value declared in the <b>WmiMethodId</b> qualifier for the method.


### -param InBufferSize [in]

Specifies the size, in bytes, of input data for the method. The actual input data is passed in the buffer pointed to by the <i>InOutBuffer</i> parameter.


### -param OutBufferSize [in, out]

Pointer to a ULONG that specifies the expected size, bytes, of the data output by the method. The actual output data is returned in the buffer pointed to by the <i>InOutBuffer</i> parameter. If the routine succeeds, it updates the memory location to specify the number of bytes actually stored in <i>InOutBuffer</i>. If the routine fails with STATUS_BUFFER_TOO_SMALL, it returns the number of bytes required to return the data.


### -param InOutBuffer [in, out]

Pointer to the buffer where the caller passes the WMI method's input data, and receives the WMI method's output data.


## -returns
The routine returns an NTSTATUS code. Possible return values include:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation succeeded. The routine returns the WMI data in the buffer pointed to by the <i>InOutBuffer</i> parameter. The routine also returns the size, in bytes, of the returned data in the memory location pointed to by the <i>OutBufferSize</i> parameter.
<dl>
<dt><b>STATUS_WMI_GUID_NOT_FOUND</b></dt>
</dl>No drivers implement the WMI class.
<dl>
<dt><b>STATUS_WMI_INSTANCE_NOT_FOUND</b></dt>
</dl>No driver implements an instance of the WMI class with <b>InstanceName</b> property equal to the value specified in the <i>InstanceName</i> parameter.
<dl>
<dt><b>STATUS_WMI_ITEMID_NOT_FOUND</b></dt>
</dl>The WMI class does not contain a method with method ID equal to the value of <i>MethodId</i>.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The buffer passed by the caller in the <i>OutBuffer</i> parameter is too small. The routine returns the required buffer size in the memory location pointed to by the <i>InOutBufferSize</i> parameter. 
<dl>
<dt><b>STATUS_WMI_GUID_DISCONNECTED</b></dt>
</dl>The WMI GUID is no longer available or was never available.

 


## -remarks
<b>IoWMIExecuteMethod</b> determines which drivers might support the specified WMI class and instance name. It issues an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550868">IRP_MN_EXECUTE_METHOD</a> request to each such driver. The driver that exports the data block instance with matching <b>InstanceName</b> property then runs the specified WMI method.


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
Available in Windows XP and later versions of the Windows operating system.

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
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.iowmiopenblock">IoWMIOpenBlock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550868">IRP_MN_EXECUTE_METHOD</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoWMIExecuteMethod routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


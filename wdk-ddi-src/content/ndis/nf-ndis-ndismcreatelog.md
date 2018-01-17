---
UID: NF:ndis.NdisMCreateLog
title: NdisMCreateLog function
author: windows-driver-content
description: NdisMCreateLog allocates and opens a log file in which a miniport driver can write data to be displayed by a driver-dedicated Win32 application.
old-location: netvista\ndismcreatelog.htm
old-project: netvista
ms.assetid: 804112cf-fc59-4a04-b848-4239b32e35d7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisMCreateLog
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCreateLog (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCreateLog (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMCreateLog
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miniport_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisMCreateLog function



## -description
<b>NdisMCreateLog</b> allocates and opens a log file in which a miniport driver can write data to be
  displayed by a driver-dedicated Win32 application.



## -syntax

````
NDIS_STATUS NdisMCreateLog(
  _In_  NDIS_HANDLE  MiniportAdapterHandle,
  _In_  UINT         Size,
  _Out_ PNDIS_HANDLE LogHandle
);
````


## -parameters

### -param MiniportAdapterHandle [in]

Specifies the handle input to 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.


### -param Size [in]

Specifies how many bytes to allocate for the log file. NDIS creates a temporary file that is not
     stored on disk.


### -param LogHandle [out]

Pointer to a caller-supplied variable in which this function returns a handle to the log file.
     This handle is a required parameter to the 
     <b>Ndis</b><i>Xxx</i><b>Log</b> functions that the miniport driver calls subsequently.


## -returns
<b>NdisMCreateLog</b> can return one of the following:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The miniport driver can use the handle returned at 
       <i>LogHandle</i> to write data to the NDIS-allocated log file.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>A log file of the specified size could not be allocated.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>The driver already called 
       <b>NdisMCreateLog</b> successfully.

 


## -remarks
A miniport driver can call the 
    <b>NdisM..Log</b> functions to provide any information the driver writer chooses. Whatever the miniport
    driver logs can be displayed by a driver-dedicated Win32 application. Such an application calls the Win32
    function 
    <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> with IOCTL_NDIS_GET_LOG_DATA periodically to retrieve whatever the miniport driver
    has written to the log file. For example, an under-development miniport driver might write test data to
    be displayed by its corresponding application.

If 
    <b>NdisMCreateLog</b> returns NDIS_STATUS_RESOURCES, the driver can adjust the original 
    <i>Size</i> down and try calling this function again. However, a miniport driver cannot call 
    <b>NdisMCreateLog</b> to create more than one log file after a call succeeds.

Whatever size of log file is allocated, subsequent calls to 
    <a href="..\ndis\nf-ndis-ndismwritelogdata.md">NdisMWriteLogData</a> store data in this
    file, which is treated as a circular buffer. That is, a sequence of calls to 
    <b>NdisMWriteLogData</b> eventually overwrites the data originally written to the log file.


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcloselog.md">NdisMCloseLog</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismflushlog.md">NdisMFlushLog</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismwritelogdata.md">NdisMWriteLogData</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCreateLog function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


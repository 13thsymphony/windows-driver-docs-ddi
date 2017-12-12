---
UID: NF.scsiwmi.ScsiPortWmiSetInstanceName
title: ScsiPortWmiSetInstanceName function
author: windows-driver-content
description: The ScsiPortWmiSetInstanceName routine updates the WNODE_ALL_DATA structure within the request context to specify the position and length of an instance name.
old-location: storage\scsiportwmisetinstancename.htm
old-project: storage
ms.assetid: f624959f-e232-4918-8f0b-f232471c2c67
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: ScsiPortWmiSetInstanceName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: scsiwmi.h
req.include-header: Miniport.h, Scsi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ScsiPortWmiSetInstanceName
req.alt-loc: scsiwmi.h
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
req.product: Windows 10 or later.
---

# ScsiPortWmiSetInstanceName function



## -description
The <b>ScsiPortWmiSetInstanceName</b> routine updates the <a href="kernel.wnode_all_data">WNODE_ALL_DATA</a> structure within the request context to specify the position and length of an instance name. 



## -syntax

````
PWCHAR ScsiPortWmiSetInstanceName(
  _In_    PSCSIWMI_REQUEST_CONTEXT RequestContext,
  _In_    ULONG                    InstanceIndex,
  _In_    ULONG                    InstanceNameLength,
  _Out_   PULONG                   BufferAvail,
  _Inout_ PULONG                   SizeNeeded
);
````


## -parameters

### -param RequestContext [in]

Pointer to a structure of type <a href="storage.scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a> that contains the request context for a WMI SRB. 


### -param InstanceIndex [in]

Contains an index that indicates the instance for which the position and length of the instance name are to be specified. 


### -param InstanceNameLength [in]

Specifies the size in bytes of the instance name.


### -param BufferAvail [out]

Must contain, on input, the number of bytes of buffer space in the <a href="kernel.wnode_all_data">WNODE_ALL_DATA</a> structure that can be used for describing instance names and data. On return, this member contains the number of bytes of buffer space that remain. 

There are three SCSI Port WMI routines that return a value for the available buffer size in their <i>BufferAvail </i>parameter:


<a href="storage.scsiportwmisetinstancecount">ScsiPortWmiSetInstanceCount</a>



<a href="storage.scsiportwmisetdata">ScsiPortWmiSetData</a>


<b>ScsiPortWmiSetInstanceName</b>

The miniport driver must call <b>ScsiPortWmiSetInstanceCount</b> first, but after <b>ScsiPortWmiSetInstanceCount</b> has been called, it does not matter in what order the minidriver calls <b>ScsiPortWmiSetData</b> and <b>ScsiPortWmiSetInstanceName</b>. When calling either <b>ScsiPortWmiSetData</b> or <b>ScsiPortWmiSetInstanceName</b>, the value passed to the routine in its <i>BufferAvail </i>parameter must be the same as the value returned in the <i>BufferAvail </i>parameter by the most recently called SCSI Port WMI routine. For instance, suppose the minidriver calls <b>ScsiPortWmiSetInstanceCount</b> first, and this routine returns a value of 1,000 in its <i>BufferAvail </i>parameter. Next, the minidriver calls <b>ScsiPortWmiSetData</b> which returns a value of 500 in its <i>BufferAvail </i>parameter. Finally, the minidriver calls <b>ScsiPortWmiSetInstanceName</b> which returns a value of 200 in its <i>BufferAvail </i>parameter. The initial value of 1,000 must be passed to <b>ScsiPortWmiSetData</b> in <i>BufferAvail</i>, and the value of 500 must be passed to <b>ScsiPortWmiSetInstanceName</b>. 

If there is not enough memory available to add an instance name of length <i>InstanceNameLength</i>, a zero will be returned in the <i>BufferAvail</i> member. 


### -param SizeNeeded [in, out]

Indicates, on input, the number of bytes needed to describe the WNODE <i>before </i>adding the descriptive data for the instance specified by <i>InstanceIndex</i>. On return, this member will contain the size of the entire WNODE, including the data for the new instance. 


## -returns
The <b>ScsiPortWmiSetInstanceCount</b> routine returns a pointer to the buffer where the caller can store the name of the instance specified in <i>InstanceIndex</i>. If <b>ScsiPortWmiSetInstanceCount</b> cannot allocate enough memory for the instance name, or if the WNODE contained within the request context is not of type <a href="kernel.wnode_all_data">WNODE_ALL_DATA</a>, <b>ScsiPortWmiSetData</b> returns <b>NULL</b>. 


## -remarks
The minidriver must call <a href="storage.scsiportwmisetinstancecount">ScsiPortWmiSetInstanceCount</a> before calling  <b>ScsiPortWmiSetInstanceName</b>.

The parameter <b>RequestContext</b> points to a request context structure, <a href="storage.scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a>, that contains information associated with a <a href="https://msdn.microsoft.com/5c2ed322-0fc9-4004-9a5f-f4d3c6a59fe9">Windows Management Instrumentation</a> (WMI) SCSI request block (SRB). The request context structure, in turn, contains one of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566371">WMI WNODE_XXX Structures</a> used by the WMI system to pass data between user-mode data consumers and kernel-mode data providers such as drivers. 

The <b>ScsiPortWmiSetInstanceName</b> routine requires the WNODE structure that is defined within the request context to be of type <a href="kernel.wnode_all_data">WNODE_ALL_DATA</a>. This is because <b>ScsiPortWmiSetInstanceName</b> can set aside an instance name area for any of the instances associated with a WMI data block. Unlike the <a href="kernel.wnode_single_instance">WNODE_SINGLE_INSTANCE</a> structure which contains information about a single instance, the WNODE_ALL_DATA structure contains an array of pointers to buffer areas for different instances, and <b>ScsiPortWmiSetInstanceCount</b> initializes this array, so that each buffer of instance data can be accessed individually.

The memory allocated for the request context must remain valid until after the miniport driver calls <b>ScsiPortWmiPostProcess</b>, and <b>ScsiPortWmiPostProcess</b> returns the final SRB status and buffer size. If the SRB can pend, the memory for the request context should be allocated from the SRB extension. If the SRB cannot pend, the memory can be allocated from a stack frame that does not go out of scope.


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
Header

</th>
<td width="70%">
<dl>
<dt>Scsiwmi.h (include Miniport.h or Scsi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a>
</dt>
<dt>
<a href="kernel.wnode_single_instance">WNODE_SINGLE_INSTANCE</a>
</dt>
<dt>
<a href="kernel.wnode_all_data">WNODE_ALL_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortWmiSetInstanceName routine%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


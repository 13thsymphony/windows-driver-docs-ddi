---
UID: NC.spbcx.EVT_SPB_CONTROLLER_LOCK
title: EVT_SPB_CONTROLLER_LOCK
author: windows-driver-content
description: An SPB controller driver's EvtSpbControllerLock event callback function locks the SPB controller for accesses of a single target device on the bus.
old-location: spb\evtspbcontrollerlock.htm
old-project: SPB
ms.assetid: E08674F1-CE63-464B-9C70-96F93C574753
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: SPB_TRANSFER_LIST,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: spbcx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EvtSpbControllerLock
req.alt-loc: Spbcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at IRQL <= DISPATCH_LEVEL.
req.iface: 
req.product: Windows 10 or later.
---

# EVT_SPB_CONTROLLER_LOCK callback



## -description
<p>An SPB controller driver's <i>EvtSpbControllerLock</i> event callback function locks the SPB controller for accesses of a single target device on the bus.</p>


## -prototype

````
EVT_SPB_CONTROLLER_LOCK EvtSpbControllerLock;

VOID EvtSpbControllerLock(
  _In_ WDFDEVICE  Controller,
  _In_ SPBTARGET  Target,
  _In_ SPBREQUEST LockRequest
)
{ ... }
````


## -parameters
<dl>

### -param Controller [in]

<dd>
<p>A WDFDEVICE handle to the <a href="kmdf.creating_a_framework_device_object">framework device object</a> that represents the SPB controller.</p>
</dd>

### -param Target [in]

<dd>
<p>An <a href="buses.spbtarget_object_handle">SPBTARGET</a> handle to the target for this I/O request. The target is a peripheral device or port that is attached to the bus. The SPB framework extension (SpbCx) previously assigned this handle to the target in the <a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a> callback that opened the connection to the target.</p>
</dd>

### -param LockRequest [in]

<dd>
<p>An <a href="buses.spbrequest_object_handle">SPBREQUEST</a> handle to an I/O control request to lock the controller.  Your SPB controller driver must complete this request either by performing the requested operation or by returning an error status. For more information, see Remarks.</p>
</dd>
</dl>

## -returns
<p>None.</p>

## -remarks
<p>SpbCx manages the I/O queue for the SPB controller. If the SPB controller driver registers an <i>EvtSpbControllerLock</i> callback function, SpbCx calls this function when a client (peripheral driver) of the controller sends an <a href="https://msdn.microsoft.com/library/windows/hardware/hh450858">IOCTL_SPB_LOCK_CONTROLLER</a> request to a target on the bus. The <i>LockRequest</i> parameter value is a handle that encapsulates this request.</p>

<p>The <i>EvtSpbControllerLock</i> and <a href="https://msdn.microsoft.com/4EB36115-2783-4FD5-9CEE-1F7C971C334D">EvtSpbControllerUnlock</a> functions perform complementary operations. Both functions are optional. If your SPB controller driver implements an <i>EvtSpbControllerUnlock</i> function, the driver is not required to implement an <i>EvtSpbControllerLock</i> function, but might do so. However, if your SPB controller driver implements an <i>EvtSpbControllerLock</i> function, it must also implement an <i>EvtSpbControllerUnlock</i> function. For more information, see Remarks in <a href="https://msdn.microsoft.com/library/windows/hardware/hh406206">SPB_CONTROLLER_CONFIG</a>.</p>

<p>While the lock is in effect, the controller must not allow accesses to targets on the bus other than the target designated by the <i>LockRequest</i> parameter.</p>

<p>If the SPB controller driver needs to change the mode of its controller to temporarily override the normal target selection mechanism, it can do so during the <i>EvtSpbControllerLock</i> callback.  If this mode change involves a long delay or requires the driver to wait for a device interrupt, the driver should initiate the mode change and then return from the callback without delay. Later, the driver can complete the lock operation in a timer DPC or an interrupt DPC.</p>

<p>If the lock operation completes in a DPC, the SPB controller driver should previously have allocated all the resources that it needs for the lock operation.</p>

<p>An <i>EvtSpbControllerLock</i> callback must avoid failing a lock request.  If <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> is enabled, such a failure  will trigger a verifier trap, which will report to the Plug and Play manager that the controller has failed.  SpbCx ignores the failure of an lock request and does not try to handle or mitigate the failure.</p>

<p>The <i>EvtSpbControllerLock</i> function does not return a value.  Instead, the SPB controller driver indicates the status of the lock operation in the completion status of the I/O request that is identified by the <i>LockRequest</i> parameter. Set the completion status to STATUS_SUCCESS.</p>

<p>SpbCx calls the <a href="https://msdn.microsoft.com/4EB36115-2783-4FD5-9CEE-1F7C971C334D">EvtSpbControllerUnlock</a> event callback function to unlock a controller that was previously locked by an <i>EvtSpbControllerLock</i> callback.</p>

<p>To register an <i>EvtSpbControllerLock</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a> method.</p>

<p>For more information about the <i>EvtSpbControllerLock</i> function, see <a href="https://msdn.microsoft.com/C1DED853-059D-481F-A524-E50772072018">Handling Client-Implemented Sequences</a>.</p>

<p>To define an <i>EvtSpbControllerLock</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define an <i>EvtSpbControllerLock</i> callback function that is named <code>MyEvtSpbControllerLock</code>, use the EVT_SPB_CONTROLLER_LOCK function type, as shown in this code example:</p>

<p>Then, implement your callback function as follows:</p>

<p>The EVT_SPB_CONTROLLER_LOCK function type is defined in the Spbcx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the EVT_SPB_CONTROLLER_LOCK function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Spbcx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Called at IRQL &lt;= DISPATCH_LEVEL.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/4EB36115-2783-4FD5-9CEE-1F7C971C334D">EvtSpbControllerUnlock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450858">IOCTL_SPB_LOCK_CONTROLLER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406206">SPB_CONTROLLER_CONFIG</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a>
</dt>
<dt>
<a href="buses.spbrequest_object_handle">SPBREQUEST</a>
</dt>
<dt>
<a href="buses.spbtarget_object_handle">SPBTARGET</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20EVT_SPB_CONTROLLER_LOCK callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

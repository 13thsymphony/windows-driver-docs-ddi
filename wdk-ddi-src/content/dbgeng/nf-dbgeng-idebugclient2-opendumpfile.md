---
UID: NF.dbgeng.IDebugClient2.OpenDumpFile
title: IDebugClient2::OpenDumpFile
author: windows-driver-content
description: The OpenDumpFile method opens a dump file as a debugger target.
old-location: debugger\opendumpfile.htm
old-project: debugger
ms.assetid: c04b79a0-ef20-4ba5-aba9-9335b095cfef
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugClient2, OpenDumpFile, IDebugClient2::OpenDumpFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugClient.OpenDumpFile,IDebugClient2.OpenDumpFile,IDebugClient3.OpenDumpFile,IDebugClient4.OpenDumpFile,IDebugClient5.OpenDumpFile
req.alt-loc: dbgeng.h
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
req.iface: IDebugClient2
---

# IDebugClient2::OpenDumpFile method



## -description
<p>The <b>OpenDumpFile</b> method opens a dump file as a debugger target.</p>


## -syntax

````
HRESULT OpenDumpFile(
  [in] PCSTR DumpFile
);
````


## -parameters
<dl>

### -param DumpFile [in]

<dd>
<p>Specifies the name of the dump file to open.  <i>DumpFile</i> must include the file name extension. <i>DumpFile</i> can include a relative or absolute path; relative paths are relative to the directory in which the debugger was started.  <i>DumpFile</i> can have the form of a file URL, starting with "file://".  If <i>DumpFile</i> specifies a cabinet (.cab) file, the cabinet file is searched for the first file with extension .kdmp, then .hdmp, then .mdmp, and finally .dmp.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>The Unicode version of this method is <a href="debugger.opendumpfilewide">OpenDumpFileWide</a>.</p>

<p>For more information about crash dump files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542783">Dump-File Targets</a>.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>
</dt>
<dt>
<a href="debugger.opendumpfilewide">OpenDumpFileWide</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564611">.opendump (Open Dump File)</a>
</dt>
<dt>
<a href="debugger.adddumpinformationfile">AddDumpInformationFile</a>
</dt>
<dt>
<a href="debugger.adddumpinformationfilewide">AddDumpInformationFileWide</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::OpenDumpFile method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

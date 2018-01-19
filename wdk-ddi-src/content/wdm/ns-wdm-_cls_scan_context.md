---
UID : NS:wdm._CLS_SCAN_CONTEXT
title : _CLS_SCAN_CONTEXT
author : windows-driver-content
description : The CLFS_SCAN_CONTEXT structure holds context information to support a scan of the containers in a Common Log File System (CLFS) log.
old-location : kernel\clfs_scan_context.htm
old-project : kernel
ms.assetid : 4f10abc6-1c86-4401-9af7-26d6c30f6fe8
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _CLS_SCAN_CONTEXT, CLS_SCAN_CONTEXT, *PCLS_SCAN_CONTEXT, PPCLS_SCAN_CONTEXT, CLFS_SCAN_CONTEXT, *PCLFS_SCAN_CONTEXT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdm.h
req.include-header : Wdm.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : CLS_SCAN_CONTEXT
req.alt-loc : wdm.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL (see Remarks section)
req.typenames : CLS_SCAN_CONTEXT, *PCLS_SCAN_CONTEXT, PPCLS_SCAN_CONTEXT
req.product : Windows 10 or later.
---

# _CLS_SCAN_CONTEXT structure
The <b>CLFS_SCAN_CONTEXT</b> structure holds context information to support a scan of the containers in a Common Log File System (CLFS) log. The client allocates this structure by calling <a href="..\wdm\nf-wdm-clfscreatescancontext.md">ClfsCreateScanContext</a>. Then, the client passes the structure repeatedly to <a href="..\wdm\nf-wdm-clfsscanlogcontainers.md">ClfsScanLogContainers</a>.

## Syntax
````
typedef struct _CLS_SCAN_CONTEXT {
  CLFS_NODE_ID                cidNode;
  PLOG_FILE_OBJECT            plfoLog;
  ULONG                       cIndex;
  ULONG                       cContainers;
  ULONG                       cContainersReturned;
  CLFS_SCAN_MODE              eScanMode;
  PCLFS_CONTAINER_INFORMATION pinfoContainer;
} CLS_SCAN_CONTEXT, *PCLS_SCAN_CONTEXT, **PPCLS_SCAN_CONTEXT, CLFS_SCAN_CONTEXT, *PCLFS_SCAN_CONTEXT, **PPCLFS_SCAN_CONTEXT;
````

## Members

        
            `cContainers`

            The number of containers to scan in each call to <b>ClfsScanLogContainers</b>. This is the number of elements in the array pointed to by <i>pinfoContainer</i>.
        
            `cContainersReturned`

            The number of containers actually scanned in a call to <b>ClfsScanLogContainers</b>.
        
            `cidNode`

            A <a href="https://msdn.microsoft.com/99132138-b7ba-47a1-ac40-353d5d70db42">CLFS_NODE_ID</a> structure that contains the scan context's node identity and type.
        
            `cIndex`

            The index of the current container.
        
            `eScanMode`

            This member can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
CLFS_SCAN_INIT

</td>
<td>
The scan is reinitialized and begins at the first container in the container list.

</td>
</tr>
<tr>
<td>
CLFS_SCAN_FORWARD

</td>
<td>
The next set of containers is scanned.

</td>
</tr>
<tr>
<td>
CLFS_SCAN_BACKWARD

</td>
<td>
The previous set of containers is scanned.

</td>
</tr>
<tr>
<td>
CLFS_SCAN_CLOSE

</td>
<td>
The scan is closed. No containers are scanned.

</td>
</tr>
</table>
        
            `pinfoContainer`

            A pointer to an array of <a href="..\wdm\ns-wdm-_cls_container_information.md">CLFS_CONTAINER_INFORMATION</a> structures. The <i>cContainers</i> parameter specifies the number of elements in this array.
        
            `plfoLog`

            A pointer to a <a href="..\wdm\ns-wdm-_file_object.md">LOG_FILE_OBJECT</a> structure that represents a CLFS log.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h) |
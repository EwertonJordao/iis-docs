﻿---
title: ManifestStream.GetChunkInfoAsync Method
TOCTitle: GetChunkInfoAsync Method
ms:assetid: 3e737bcc-ccc5-44b5-a34e-9cb46e08f495
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ822721(v=VS.90)
ms:contentKeyID: 50079476
ms.date: 11/19/2012
mtps_version: v=VS.90
dev_langs:
- csharp
- c++
- jscript
---

# ManifestStream.GetChunkInfoAsync Method

**Applies to:** Windows Store apps only

Gets the chunk info of the given chunk iterator through async call.

## Syntax

``` csharp
public IAsyncOperation<ChunkInfo> GetChunkInfoAsync(
IChunkIter pChunkIter
)
```

``` c++
public:
virtual IAsyncOperation<ChunkInfo>^ GetChunkInfoAsync(
[InAttribute] IChunkIter^ pChunkIter
) sealed
```

``` jscript
public final function GetChunkInfoAsync(
pChunkIter : IChunkIter
) : IAsyncOperation<ChunkInfo>
```

## Parameters

  - pChunkIter  
    Type: IAsyncOperation(ChunkInfo)

## Return Value

If the method succeeds, it returns S\_OK. Otherwise, it returns an HRESULT error code.

## Requirements

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Minimum supported client</strong></p></td>
<td><p>Windows 8</p></td>
</tr>
<tr class="even">
<td><p><strong>Minimum supported server</strong></p></td>
<td><p>Not Supported</p></td>
</tr>
<tr class="odd">
<td><p><strong>Metadata</strong></p></td>
<td><p>Microsoft.Media.AdaptiveStreaming.winmd</p></td>
</tr>
</tbody>
</table>

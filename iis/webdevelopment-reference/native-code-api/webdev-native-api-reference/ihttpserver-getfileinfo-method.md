---
title: "IHttpServer::GetFileInfo Method | Microsoft Docs"
ms.custom: ""
ms.date: "10/07/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c3d91fe-062b-93c1-c5ad-e0dda028d987
caps.latest.revision: 20
author: "shirhatti"
manager: "wpickett"
---
# IHttpServer::GetFileInfo Method
Returns an [IHttpFileInfo](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpfileinfo-interface.md) interface for a specific file path.  
  
## Syntax  
  
```cpp  
virtual HRESULT GetFileInfo(  
   IN PCWSTR pszPhysicalPath,  
   IN HANDLE hUserToken,  
   IN PSID pSid,  
   IN PCWSTR pszVrPath,  
   IN HANDLE hVrToken,  
   IN BOOL fCache,  
   OUT IHttpFileInfo** ppFileInfo,  
   IN IHttpTraceContext* pHttpTraceContext = NULL  
) = 0;  
```  
  
#### Parameters  
 `pszPhysicalPath`  
 [IN] A pointer to a string that contains the physical path to a file.  
  
 `hUserToken`  
 [IN] A `HANDLE` that contains the token for the impersonation user; otherwise, NULL.  
  
 `pSid`  
 [IN] A pointer to a security identifier ([SID](http://go.microsoft.com/fwlink/?LinkId=63529)) that contains the security ID for the impersonation user; otherwise, NULL.  
  
 `pszVrPath`  
 [IN] A pointer to a string that contains the virtual path to register for change notifications; otherwise, NULL.  
  
 `hVrToken`  
 [IN] A `HANDLE` that contains the impersonation token to register for change notifications; otherwise, NULL.  
  
 `fCache`  
 [IN] `true` to indicate that the file should be cached; otherwise, `false`.  
  
 `ppFileInfo`  
 [OUT] A dereferenced pointer to an `IHttpFileInfo` interface.  
  
 `pHttpTraceContext`  
 [IN] A pointer to an optional [IHttpTraceContext](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttptracecontext-interface.md) interface.  
  
## Return Value  
 An `HRESULT`. Possible values include, but are not limited to, those in the following table.  
  
|Value|Definition|  
|-----------|----------------|  
|S_OK|Indicates that the operation was successful.|  
|E_FAIL|Indicates that the call to `GetFileInfo` was made while the module host was terminating.|  
  
## Remarks  
 The `IHttpServer::GetFileInfo` method creates an `IHttpFileInfo` interface for a specific path. This method differs from the [IHttpContext::GetFileInfo](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpcontext-getfileinfo-method.md) method, which returns an `IHttpFileInfo` interface for the file that IIS is processing within a request context.  
  
 The `pszPhysicalPath` and `ppFileInfo` parameters are required to create an `IHttpFileInfo` interface. The `pszPhysicalPath` parameter specifies the path to the file, and the `ppFileInfo` parameter defines the pointer that IIS will populate with the corresponding `IHttpFileInfo` interface.  
  
 The `pszVrPath` and `hVrToken` parameters are optional, and you should set them to NULL if you do not use them. These parameters specify, respectively, the virtual path and impersonation token to use when a module registers for change notifications (for example, if you request caching by setting the `fCache` parameter to `true`).  
  
> [!NOTE]
>  Other configuration settings may prevent IIS from caching the file, even if you specify `true` for the `fCache` parameter.  
  
 The `hUserToken` and `pSid` parameters are also optional, and you should set them to NULL if you do not use them. These parameters specify, respectively, the token and SID for the impersonation user. The remaining optional parameter, `pHttpTraceContext`, specifies the `IHttpTraceContext` interface for tracing.  
  
## Example  
 The following code example demonstrates how to create an HTTP module that performs the following tasks:  
  
1.  Registers for the [RQ_BEGIN_REQUEST](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/request-processing-constants.md) notification.  
  
2.  Creates a [CHttpModule](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/chttpmodule-class.md) class that contains an [OnBeginRequest](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/chttpmodule-onbeginrequest-method.md) method. When a client requests a file, the `OnBeginRequest` method performs the following tasks:  
  
    1.  Maps a path to a relative URL by using the [IHttpContext::MapPath](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpcontext-mappath-method.md) method.  
  
    2.  Creates an `IHttpFileInfo` interface for the file path by using the `IHttpServer::GetFileInfo` method.  
  
    3.  Retrieves the entity tag for the file by using the [IHttpFileInfo::GetETag](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpfileinfo-getetag-method.md) method.  
  
    4.  Returns the entity tag to the client by using the [IHttpResponse::WriteEntityChunks](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpresponse-writeentitychunks-method.md) method.  
  
3.  Removes the `CHttpModule` class from memory and then exits.  
  
<!-- TODO: review snippet reference  [!CODE [IHttpServerGetFileInfo#1](IHttpServerGetFileInfo#1)]  -->  
  
 For more information on how to create and deploy a native DLL module, see [Walkthrough: Creating a Request-Level HTTP Module By Using Native Code](../../../webdevelopment-reference\native-code-development-overview\native-code-dev-overview/walkthrough-creating-a-request-level-http-module-by-using-native-code.md).  
  
 You can optionally compile the code by using the `__stdcall (/Gz)` calling convention instead of explicitly declaring the calling convention for each function.  
  
## Requirements  
  
|Type|Description|  
|----------|-----------------|  
|Client|-   [!INCLUDE[iis70](../../../wmi-provider/includes/iis70-md.md)] on [!INCLUDE[winvista](../../../wmi-provider/includes/winvista-md.md)]<br />-   [!INCLUDE[iis75](../../../wmi-provider/includes/iis75-md.md)] on [!INCLUDE[win7](../../../wmi-provider/includes/win7-md.md)]<br />-   [!INCLUDE[iis80](../../../wmi-provider/includes/iis80-md.md)] on [!INCLUDE[win8](../../../wmi-provider/includes/win8-md.md)]<br />-   [!INCLUDE[iis100](../../../wmi-provider/includes/iis100-md.md)] on [!INCLUDE[win10](../../../wmi-provider/includes/win10-md.md)]|  
|Server|-   [!INCLUDE[iis70](../../../wmi-provider/includes/iis70-md.md)] on [!INCLUDE[winsrv2008](../../../wmi-provider/includes/winsrv2008-md.md)]<br />-   [!INCLUDE[iis75](../../../wmi-provider/includes/iis75-md.md)] on [!INCLUDE[winsrv2008r2](../../../wmi-provider/includes/winsrv2008r2-md.md)]<br />-   [!INCLUDE[iis80](../../../wmi-provider/includes/iis80-md.md)] on [!INCLUDE[winsrv2012](../../../wmi-provider/includes/winsrv2012-md.md)]<br />-   [!INCLUDE[iis85](../../../wmi-provider/includes/iis85-md.md)] on [!INCLUDE[winsrv2012r2](../../../wmi-provider/includes/winsrv2012r2-md.md)]<br />-   [!INCLUDE[iis100](../../../wmi-provider/includes/iis100-md.md)] on [!INCLUDE[winsrv2016](../../../wmi-provider/includes/winsrv2016-md.md)]|  
|Product|-   [!INCLUDE[iis70](../../../wmi-provider/includes/iis70-md.md)], [!INCLUDE[iis75](../../../wmi-provider/includes/iis75-md.md)], [!INCLUDE[iis80](../../../wmi-provider/includes/iis80-md.md)], [!INCLUDE[iis85](../../../wmi-provider/includes/iis85-md.md)], [!INCLUDE[iis100](../../../wmi-provider/includes/iis100-md.md)]<br />-   [!INCLUDE[iisexp75](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/includes/iisexp75-md.md)], [!INCLUDE[iisexp80](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/includes/iisexp80-md.md)], [!INCLUDE[iisexp100](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/includes/iisexp100-md.md)]|  
|Header|Httpserv.h|  
  
## See Also  
 [IHttpServer Interface](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpserver-interface.md)   
 [IHttpContext::GetFileInfo Method](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpcontext-getfileinfo-method.md)
---
title: GetProperties 메서드에 대한 항목 네임스페이스 설정 | Microsoft Docs
Description: GetProperties 메서드 및 ItemNamespaceHeader SOAP 헤더를 사용하여 항목의 경로 또는 ID를 기준으로 속성을 검색하는 방법을 알아봅니다.
ms.date: 03/06/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-server-web-service-net-framework-soap-headers
ms.topic: reference
helpviewer_keywords:
- item properties [Reporting Services]
- ItemNamespaceHeader SOAP header
- GetProperties method
ms.assetid: b0a08639-3101-40a2-abe2-3a41753826d1
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: bc0dee4442b18913521deb97c0c9655188f64631
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2020
ms.locfileid: "80216252"
---
# <a name="setting-the-item-namespace-for-the-getproperties-method"></a>GetProperties 메서드에 대한 항목 네임스페이스 설정
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]에서 <xref:ReportService2010.ItemNamespaceHeader> SOAP 헤더를 사용하여 서로 다른 항목 식별자인 항목의 전체 경로 또는 항목의 ID를 기준으로 항목 속성을 검색할 수 있습니다.  
  
 <xref:ReportService2010.ReportingService2010.GetProperties%2A> 메서드를 호출할 때 일반적으로 속성을 검색하려는 항목의 전체 경로를 인수로 전달합니다. <xref:ReportService2010.ItemNamespaceHeader>를 사용하여 메서드 호출에 대해 SOAP 헤더를 설정하면 항목의 ID를 식별자로 전달하여 <xref:ReportService2010.ReportingService2010.GetProperties%2A>를 사용할 수 있습니다.  
  
 다음 코드 예제에서는 항목의 ID를 기준으로 항목 속성에 대한 값을 검색합니다.  
  
> [!NOTE]  
>  기본적으로 <xref:ReportService2010.ItemNamespaceHeader> 메서드에 전체 경로 이름을 항목 식별자로 전달하는 경우 <xref:ReportService2010.ReportingService2010.GetProperties%2A>에 대한 값을 설정할 필요가 없습니다.  
  
```vb  
Imports System  
Imports System.Collections  
  
Class Sample  
   Sub Main()  
      Dim rs As New ReportingService2010()  
      rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
      rs.Url = "https://<Server Name>/reportserver/ReportService2010.asmx"  
  
      Dim items() As CatalogItem  
  
      Try  
         ' Need the ID property of items. Normally, you would already have   
         ' this stored somewhere.  
         items = rs.ListChildren("/AdventureWorks Sample Reports", False)  
  
         ' Set the item namespace header to be GUID-based  
         rs.ItemNamespaceHeaderValue = New ItemNamespaceHeader()  
         rs.ItemNamespaceHeaderValue.ItemNamespace = ItemNamespaceEnum.GUIDBased  
  
         ' Call GetProperties with item ID.  
         If Not (items Is Nothing) Then  
            Dim item As CatalogItem  
            For Each item In  items  
               Dim properties As [Property]() = rs.GetProperties(item.ID, Nothing)  
               Dim property As [Property]  
               For Each property In  properties  
                  Console.WriteLine(([property].Name + ": " + [property].Value))  
               Next property  
               Console.WriteLine()  
            Next item  
         End If  
  
      Catch e As Exception  
         Console.WriteLine((e.Message + ": " + e.StackTrace))  
      End Try  
   End Sub 'Main  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.Collections;  
  
class Sample  
{  
   static void Main()  
   {  
   ReportingService2010 rs = new ReportingService2010();  
      rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
      rs.Url = "https://<Server Name>/reportserver/ReportService2010.asmx";  
  
      CatalogItem[] items;  
  
      try  
      {  
         // Need the ID property of items. Normally, you would already have   
         // this stored somewhere.  
         items = rs.ListChildren("/AdventureWorks Sample Reports", false);  
  
         // Set the item namespace header to be GUID-based  
         rs.ItemNamespaceHeaderValue = new ItemNamespaceHeader();  
         rs.ItemNamespaceHeaderValue.ItemNamespace = ItemNamespaceEnum.GUIDBased;  
  
         // Call GetProperties with item ID.  
         if (items != null)  
         {  
            foreach( CatalogItem item in items)  
            {  
               Property[] properties = rs.GetProperties(item.ID, null);  
               foreach (Property property in properties)  
               {  
                  Console.WriteLine(property.Name + ": " + property.Value);  
               }  
               Console.WriteLine();  
            }  
         }  
      }  
  
      catch (Exception e)  
      {  
         Console.WriteLine(e.Message);  
      }  
   }  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [기술 참조&#40;SSRS&#41;](../../reporting-services/technical-reference-ssrs.md)   
 [Reporting Services SOAP 헤더 사용](../../reporting-services/report-server-web-service-net-framework-soap-headers/using-reporting-services-soap-headers.md)  
  
  

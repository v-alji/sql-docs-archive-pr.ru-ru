---
title: Использование интерфейса IDeliveryReportServerInformation для модуля доставки | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- IDeliveryReportServerInformation interface
- delivery extensions [Reporting Services], retrieving report server information
ms.assetid: adbce647-18f3-470c-8114-42f8bcc95dc2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 52e137d1a866305ec6435a4940fe98448bce5778
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669294"
---
# <a name="using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension"></a>Использование интерфейса IDeliveryReportServerInformation в модуле доставки
  В интерфейсе <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> доступно несколько свойств, с помощью которых можно получить сведения о сервере отчетов. Эти сведения моно использовать для доставки уведомлений и отчетов. Во время реализации класса модуля доставки реализуется свойство <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A>, требуемое интерфейсом <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>. Свойство <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A> возвращает объект, который реализует интерфейс <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation>. Из этого объекта можно получить список модулей подготовки отчетов, которые в данный момент поддерживаются сервером отчетов.  
  
 Следующий `for` цикл можно использовать для хранения списка модулей подготовки отчетов, доступных в настоящее время на сервере отчетов в объекте **ArrayList** .  
  
```vb  
Dim renderFormats As New ArrayList()  
Dim e As Microsoft.ReportingServices.Interfaces.Extension  
For Each e In  ReportServerInformation.RenderingExtension  
   If e.Visible Then  
      renderFormats.Add(e.Name)  
   End If  
Next e  
```  
  
```csharp  
ArrayList renderFormats = new ArrayList();  
foreach (Microsoft.ReportingServices.Interfaces.Extension e in ReportServerInformation.RenderingExtension)  
{   
   if (e.Visible)  
   {  
      renderFormats.Add(e.Name);  
   }  
}  
```  
  
 Дополнительные сведения об использовании интерфейса <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> см. в разделе [Использование интерфейса IDeliveryReportServerInformation для модуля доставки](using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension.md).  
  
## <a name="see-also"></a>См. также:  
 <xref:Microsoft.ReportingServices.Interfaces>   
 [Реализация модуля доставки](implementing-a-delivery-extension.md)   
 [Библиотека модулей служб Reporting Services](../reporting-services-extension-library.md)  
  
  

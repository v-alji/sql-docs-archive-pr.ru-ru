---
title: Пропуск значений для необязательных объектов веб-службы | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], omitted values
- XML Web service [Reporting Services], omitted values
- Report Server Web service, omitted values
- omitting values [Reporting Services]
ms.assetid: ceb68b8b-9214-4745-abc9-f47f33ecd6f7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3858f73e1b332acfa1a1bbc640007f6f0884abff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730134"
---
# <a name="omitting-values-for-optional-web-service-objects"></a><span data-ttu-id="bf257-102">Пропуск значений для необязательных объектов веб-службы</span><span class="sxs-lookup"><span data-stu-id="bf257-102">Omitting Values for Optional Web Service Objects</span></span>
  <span data-ttu-id="bf257-103">Свойства некоторых сложных типов веб-служб сервера отчетов имеют сопутствующее свойство, известное как свойство Specified.</span><span class="sxs-lookup"><span data-stu-id="bf257-103">Properties of several of the Report Server Web service complex types have an accompanying property known as the Specified property.</span></span> <span data-ttu-id="bf257-104">Имя этого свойства состоит из исходного имени свойства и присоединенного к нему слова «Specified».</span><span class="sxs-lookup"><span data-stu-id="bf257-104">The name of the property consists of the original property name with the word "Specified" appended to it.</span></span> <span data-ttu-id="bf257-105">Наличие этого свойства указывает на то, что значение исходного свойства может быть пропущено.</span><span class="sxs-lookup"><span data-stu-id="bf257-105">The presence of this property indicates that a value for the original property may sometimes be omitted.</span></span> <span data-ttu-id="bf257-106">Это прямой результат перевода с языка описания веб-служб (WSDL) в класс-посредник платформы [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf257-106">This is a direct result of the translation from the Web Service Description Language (WSDL) to a [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proxy class.</span></span> <span data-ttu-id="bf257-107">Например, свойство веб-службы <xref:ReportService2010.DataSourceDefinition.Enabled%2A> сложного типа <xref:ReportService2010.DataSourceDefinition> имеет сопутствующее свойство с именем <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf257-107">For example, the Web service property <xref:ReportService2010.DataSourceDefinition.Enabled%2A> of the complex type <xref:ReportService2010.DataSourceDefinition> has an accompanying property named <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A>.</span></span> <span data-ttu-id="bf257-108">Если при построении приложения нежелательно задавать значение свойства <xref:ReportService2010.DataSourceDefinition.Enabled%2A>, то не нужно указывать значение для <xref:ReportService2010.DataSourceDefinition.Enabled%2A>. Будет использоваться значение по умолчанию `true`.</span><span class="sxs-lookup"><span data-stu-id="bf257-108">If you are building an application and do not want to set a value for the <xref:ReportService2010.DataSourceDefinition.Enabled%2A> property, you do not have to supply a value for <xref:ReportService2010.DataSourceDefinition.Enabled%2A>; the default value of `true` is used.</span></span> <span data-ttu-id="bf257-109">Однако все же нужно установить для свойства <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="bf257-109">However, you still need to set <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> to `false`.</span></span> <span data-ttu-id="bf257-110">Если для свойства <xref:ReportService2010.DataSourceDefinition.Enabled%2A> задается значение, необходимо для свойства <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> задать значение, равное `true`.</span><span class="sxs-lookup"><span data-stu-id="bf257-110">If you supply a value for the <xref:ReportService2010.DataSourceDefinition.Enabled%2A> property, you need to set <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> equal to `true`.</span></span> <span data-ttu-id="bf257-111">Это касается свойств, доступных для записи.</span><span class="sxs-lookup"><span data-stu-id="bf257-111">This is the case for writable properties.</span></span> <span data-ttu-id="bf257-112">Для свойств, доступных только для чтения, не требуется предпринимать каких-либо действий.</span><span class="sxs-lookup"><span data-stu-id="bf257-112">For read-only properties, you do not need to take any action.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bf257-113">Ошибка в указании свойства с помощью вышеприведенной методики может привести к непредсказуемому поведению веб-службы.</span><span class="sxs-lookup"><span data-stu-id="bf257-113">Failure to specify a property using the above-mentioned technique can result in unpredictable Web service behavior.</span></span>  
  
 <span data-ttu-id="bf257-114">Типы данных, которые обычно нуждаются в обработке дополнительного указанного свойства, — это `Boolean` , `DateTime` и `Enumeration` .</span><span class="sxs-lookup"><span data-stu-id="bf257-114">The data types that usually require you to handle the additional Specified property are `Boolean`, `DateTime`, and `Enumeration`.</span></span>  
  
 <span data-ttu-id="bf257-115">Пример см. в описании метода <xref:ReportService2010.ReportingService2010.CreateDataSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf257-115">For an example, see <xref:ReportService2010.ReportingService2010.CreateDataSource%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf257-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="bf257-116">See Also</span></span>  
 <span data-ttu-id="bf257-117">[Создание приложений с помощью веб-службы и .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="bf257-117">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="bf257-118">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="bf257-118">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  

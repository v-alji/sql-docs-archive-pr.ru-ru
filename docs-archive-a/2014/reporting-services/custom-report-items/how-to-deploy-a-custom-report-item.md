---
title: Руководство. Развертывание пользовательского элемента отчета | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, deploying
ms.assetid: 80e97b0d-e355-4240-aebd-08cbc84089ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 66519610526478caadeb41b48c9823414e88d5d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750531"
---
# <a name="how-to-deploy-a-custom-report-item"></a><span data-ttu-id="495dd-102">Руководство. Развертывание пользовательского элемента отчета</span><span class="sxs-lookup"><span data-stu-id="495dd-102">How to: Deploy a Custom Report Item</span></span>
  <span data-ttu-id="495dd-103">Чтобы развернуть пользовательский элемент отчета в службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], нужно изменить файлы конфигурации сервера отчетов и скопировать сборки времени разработки и времени выполнения в соответствующие папки приложений для конструктора отчетов и сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="495dd-103">To deploy a custom report item in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must modify the report server configuration files and copy the design-time and run-time component assemblies into the appropriate application folders for both Report Designer and the report server.</span></span>  
  
### <a name="to-deploy-a-custom-report-item"></a><span data-ttu-id="495dd-104">Развертывание пользовательского элемента отчета</span><span class="sxs-lookup"><span data-stu-id="495dd-104">To deploy a custom report item</span></span>  
  
1.  <span data-ttu-id="495dd-105">Произведите редактирование файла Rsreportdesigner.config, настроив компоненты времени разработки и компоненты времени выполнения, принадлежащие пользовательскому элементу отчета, для использования в конструкторе. </span><span class="sxs-lookup"><span data-stu-id="495dd-105">Edit the Rsreportdesigner.config file to configure the custom report item run-time and design-time components for use in the designer.</span></span> <span data-ttu-id="495dd-106">Следует заметить, что запись `ReportItemName` должна соответствовать атрибуту `CustomReportItemAttribute`, используемому в классе `CustomReportItemDesigner`.</span><span class="sxs-lookup"><span data-stu-id="495dd-106">Note that the `ReportItemName` entry must match the `CustomReportItemAttribute` attribute used in your `CustomReportItemDesigner` class.</span></span> <span data-ttu-id="495dd-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="495dd-107">For example:</span></span>  
  
    ```  
    <ReportItems>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsCRI,PolygonsCRI"/>  
    </ReportItems>  
    <ReportItemDesigner>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsDesigner, PolygonsDesigner" />  
    </ReportItemDesigner>  
    <ReportItemConverter>  
       <Converter Source="Chart" Target="Polygons" Type="PolygonsCRI.PolygonsConverter, PolygonsDesigner" />  
    </ReportItemConverter>  
    ```  
  
2.  <span data-ttu-id="495dd-108">Произведите редактирование файла Rsreportdesigner.config, зарегистрировав компонент времени выполнения пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="495dd-108">Edit the Rsreportserver.config file to register the custom report item run-time component.</span></span> <span data-ttu-id="495dd-109">Пример:</span><span class="sxs-lookup"><span data-stu-id="495dd-109">For example:</span></span>  
  
    ```  
    <ReportItems>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsCRI,PolygonsCRI"/>  
    </ReportItems>  
    ```  
  
3.  <span data-ttu-id="495dd-110">Отредактируйте файл Rsssrvpolicy.config, добавив запись `CodeGroup`, предоставляющую соответствующие разрешения для пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="495dd-110">Edit the Rsssrvpolicy.config file to add a `CodeGroup` that grants the proper permissions to the custom report item.</span></span> <span data-ttu-id="495dd-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="495dd-111">For example:</span></span>  
  
    ```  
    <CodeGroup   
       class="UnionCodeGroup"   
       version="1"   
       PermissionSetName="FullTrust"  
       Description="This code group grants MyCustomReportItem.dll FullTrust permission. ">  
       <IMembershipCondition   
          class="UrlMembershipCondition"  
          version="1"  
       Url="C:\Program Files\Microsoft SQL Server\ MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin\MyCustomReportItem.dll" />  
    </CodeGroup>  
    ```  
  
4.  <span data-ttu-id="495dd-112">Скопируйте динамическую библиотеку компонента времени выполнения пользовательского элемента отчета в каталоги %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies и \Program Files\Microsoft SQL Server\MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="495dd-112">Copy the custom report item run-time component DLL to the %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies and \Program Files\Microsoft SQL Server\MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin directories.</span></span>  
  
5.  <span data-ttu-id="495dd-113">Скопируйте динамическую библиотеку компонента времени разработки пользовательского элемента отчета в каталог %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="495dd-113">Copy the custom report item design-time component DLL to the %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="495dd-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="495dd-114">See Also</span></span>  
 <span data-ttu-id="495dd-115">[Файлы конфигурации служб Reporting Services](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="495dd-115">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="495dd-116">Библиотеки классов пользовательского элемента отчета</span><span class="sxs-lookup"><span data-stu-id="495dd-116">Custom Report Item Class Libraries</span></span>](custom-report-item-class-libraries.md)  
  
  

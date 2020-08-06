---
title: Включение интеграции служб Data Quality Services со службами Master Data Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: ab32938d-a80e-4106-80d4-94b2de3d67dc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8d2fa25254cae2a129b6e08ff657d92af4ff9455
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657831"
---
# <a name="enable-data-quality-services-integration-with-master-data-services"></a><span data-ttu-id="83b6e-102">Включение интеграции служб Data Quality Services со службами Master Data Services</span><span class="sxs-lookup"><span data-stu-id="83b6e-102">Enable Data Quality Services Integration with Master Data Services</span></span>
  <span data-ttu-id="83b6e-103">В службах [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]соответствующие функциональные возможности обеспечиваются службами Data Quality Services.</span><span class="sxs-lookup"><span data-stu-id="83b6e-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], matching functionality is provided by Data Quality Services (DQS).</span></span> <span data-ttu-id="83b6e-104">Для того чтобы использовать эти функции, их следует активировать.</span><span class="sxs-lookup"><span data-stu-id="83b6e-104">This functionality must be enabled to be used.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="83b6e-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="83b6e-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="83b6e-106">Веб-приложение и база данных служб [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] должны существовать.</span><span class="sxs-lookup"><span data-stu-id="83b6e-106">A [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web application and database must exist.</span></span>  
  
-   <span data-ttu-id="83b6e-107">Компонент служб Data Quality Services и клиент DQS должны быть установлены на том же экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , на котором размещена база данных служб MDS.</span><span class="sxs-lookup"><span data-stu-id="83b6e-107">The Data Quality Services feature and the Data Quality Client must be installed on the same [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that hosts the MDS database.</span></span> <span data-ttu-id="83b6e-108">Дополнительные сведения см. в разделе [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span><span class="sxs-lookup"><span data-stu-id="83b6e-108">For more information, see [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span></span>  
  
### <a name="to-enable-data-quality-services-integration"></a><span data-ttu-id="83b6e-109">Включение интеграции служб Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="83b6e-109">To enable Data Quality Services integration</span></span>  
  
1.  <span data-ttu-id="83b6e-110">Откройте среду [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83b6e-110">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="83b6e-111">На панели слева щелкните элемент **Веб-конфигурация**.</span><span class="sxs-lookup"><span data-stu-id="83b6e-111">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="83b6e-112">На странице **Веб-конфигурация** выберите веб-сайт и веб-приложение.</span><span class="sxs-lookup"><span data-stu-id="83b6e-112">On the **Web Configuration** page, select the website and web application.</span></span>  
  
4.  <span data-ttu-id="83b6e-113">В разделе **Включение интеграции DQS** выберите пункт **Включить интеграцию со службами Data Quality Services**.</span><span class="sxs-lookup"><span data-stu-id="83b6e-113">In the **Enable DQS Integration** section, click **Enable integration with Data Quality Services**.</span></span>  
  
5.  <span data-ttu-id="83b6e-114">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="83b6e-114">On the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b6e-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="83b6e-115">See Also</span></span>  
 <span data-ttu-id="83b6e-116">[Сопоставление качества данных в надстройка MDS для Excel](../microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="83b6e-116">[Data Quality Matching in the MDS Add-in for Excel](../microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="83b6e-117">[надстройка Master Data Services для Microsoft Excel](../microsoft-excel-add-in/master-data-services-add-in-for-microsoft-excel.md) </span><span class="sxs-lookup"><span data-stu-id="83b6e-117">[Master Data Services Add-in for Microsoft Excel](../microsoft-excel-add-in/master-data-services-add-in-for-microsoft-excel.md) </span></span>  
 [<span data-ttu-id="83b6e-118">Установка служб Master Data Services</span><span class="sxs-lookup"><span data-stu-id="83b6e-118">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  

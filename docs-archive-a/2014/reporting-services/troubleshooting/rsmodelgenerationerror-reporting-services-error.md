---
title: rsModelGenerationError — ошибка служб Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsModelGenerationError
ms.assetid: 3a0ad63f-87f9-4ca1-b0c2-c85fa991634a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 713de57f0f2957983966f8ef0345bb374c311781
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664676"
---
# <a name="rsmodelgenerationerror---reporting-services-error"></a><span data-ttu-id="bd344-102">rsModelGenerationError - Ошибка службы Reporting Services</span><span class="sxs-lookup"><span data-stu-id="bd344-102">rsModelGenerationError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="bd344-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="bd344-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd344-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="bd344-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="bd344-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="bd344-105">Event ID</span></span>|<span data-ttu-id="bd344-106">rsRenderingError</span><span class="sxs-lookup"><span data-stu-id="bd344-106">rsRenderingError</span></span>|  
|<span data-ttu-id="bd344-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="bd344-107">Event Source</span></span>|<span data-ttu-id="bd344-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="bd344-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="bd344-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="bd344-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="bd344-110">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="bd344-110">Message Text</span></span>|<span data-ttu-id="bd344-111">Во время построения модели произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="bd344-111">An error occurred while generating model.</span></span> <span data-ttu-id="bd344-112">(rsModelGenerationError) (ReportingServicesLibrary) %1</span><span class="sxs-lookup"><span data-stu-id="bd344-112">(rsModelGenerationError) (ReportingServicesLibrary) %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bd344-113">Объяснение</span><span class="sxs-lookup"><span data-stu-id="bd344-113">Explanation</span></span>  
 <span data-ttu-id="bd344-114">Невозможно сформировать модель отчета.</span><span class="sxs-lookup"><span data-stu-id="bd344-114">The report model could not be generated.</span></span> <span data-ttu-id="bd344-115">В [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]2005 с пакетом обновления 1 (SP1) и ранее эта ошибка обычно происходит в том случае, если объекту System.Data.DataSet не удается обработать таблицу или связь в схеме базы данных, например когда для одного и того же столбца таблицы определены два внешних ключа.</span><span class="sxs-lookup"><span data-stu-id="bd344-115">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]2005 SP1 and earlier versions, this error is most likely displayed when the System.Data.DataSet object cannot handle a table or relationship within the database schema, such as when, for example, two foreign keys are defined on the same column within a table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bd344-116">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="bd344-116">User Action</span></span>  
 <span data-ttu-id="bd344-117">Для определения причины ошибки просмотрите файлы журналов сервера отчетов, расположенные в папке \Microsoft SQL Server\\<SQL Server Instance\>\Reporting Services\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="bd344-117">To determine the specific reason that caused this message to appear, review the report server log files, which are located at \Microsoft SQL Server\\<SQL Server Instance\>\Reporting Services\LogFiles.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="bd344-118">Только для внутреннего использования</span><span class="sxs-lookup"><span data-stu-id="bd344-118">Internal-Only</span></span>  
  

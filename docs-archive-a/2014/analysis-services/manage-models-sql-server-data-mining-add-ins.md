---
title: Управление моделями (SQL Server надстройки интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, importing
- mining models, deleting
- mining models, managing
- mining models, training
- mining models, processing
- mining models, exporting
ms.assetid: c11380f0-7c24-4668-9cdf-9c53e4aff665
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5f4b5961ec79bb949bf7fa5f53a980f066e81379
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666851"
---
# <a name="manage-models-sql-server-data-mining-add-ins"></a><span data-ttu-id="7f36e-102">Управление моделями (надстройки интеллектуального анализа данных SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f36e-102">Manage Models (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="7f36e-103">![Кнопка «Управление моделями» на ленте «Интеллектуальный анализ данных»](media/dmc-manage.gif "Кнопка «Управление моделями» на ленте «Интеллектуальный анализ данных»")</span><span class="sxs-lookup"><span data-stu-id="7f36e-103">![Manage Models button, Data Mining ribbon](media/dmc-manage.gif "Manage Models button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="7f36e-104">Диалоговое окно **Управление моделями** позволяет взаимодействовать с существующими моделями интеллектуального анализа данных и структурами интеллектуального анализа данных, хранящимися на сервере, к [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] которому в данный момент установлено соединение.</span><span class="sxs-lookup"><span data-stu-id="7f36e-104">The **Manage Models** dialog box enables you to interact with existing mining models and mining structures that are stored in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server to which you are currently connected.</span></span> <span data-ttu-id="7f36e-105">Также можно просматривать временные структуры и модели, которые были созданы в течение текущего сеанса, и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="7f36e-105">You can also view and manage temporary structures and models that have been created during the current session.</span></span> <span data-ttu-id="7f36e-106">При использовании моделей и структур сеанса, хранящихся на сервере, они отображаются в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="7f36e-106">If you have used both session models and models stored on a server, both are visible in the dialog box.</span></span>  
  
## <a name="using-the-manage-models-wizard"></a><span data-ttu-id="7f36e-107">Использование мастера «Управление моделями»</span><span class="sxs-lookup"><span data-stu-id="7f36e-107">Using the Manage Models Wizard</span></span>  
 <span data-ttu-id="7f36e-108">При нажатии кнопки **Управление моделями**открывается диалоговое окно **Управление структурами и моделями интеллектуального анализа** данных, предоставляя доступ к следующим функциональным возможностям для управления существующими моделями и структурами интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="7f36e-108">When you click **Manage Models**, the **Manage Mining Structures and Models** dialog box opens, providing access to the following functionality for managing existing data mining models and structures:</span></span>  
  
-   <span data-ttu-id="7f36e-109">Переименование модели и структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7f36e-109">Rename a mining model or structure</span></span>  
  
-   <span data-ttu-id="7f36e-110">Удаление модели и структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7f36e-110">Delete a mining model or structure</span></span>  
  
-   <span data-ttu-id="7f36e-111">Очистка модели и структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7f36e-111">Clear a mining model or structure</span></span>  
  
-   <span data-ttu-id="7f36e-112">Обработка структуры интеллектуального анализа данных с использованием новых или существующих данных.</span><span class="sxs-lookup"><span data-stu-id="7f36e-112">Process a mining structure, using either new or existing data</span></span>  
  
-   <span data-ttu-id="7f36e-113">Экспорт или импорт модели или структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7f36e-113">Export or import a mining model or structure</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f36e-114">Создать запросы или модели в этом диалоговом окне нельзя.</span><span class="sxs-lookup"><span data-stu-id="7f36e-114">You cannot create queries or models by using this dialog box.</span></span> <span data-ttu-id="7f36e-115">Чтобы создать новую структуру интеллектуального анализа данных, используйте один из мастеров, представленных в клиенте интеллектуального анализа данных для Excel, или используйте **Расширенный редактор запросов интеллектуального анализа**.</span><span class="sxs-lookup"><span data-stu-id="7f36e-115">To create a new mining structure, use one of the wizards provided in the Data Mining Client for Excel, or use the **Data Mining Query Advanced Editor**.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="7f36e-116">Требования</span><span class="sxs-lookup"><span data-stu-id="7f36e-116">Requirements</span></span>  
 <span data-ttu-id="7f36e-117">Чтобы управлять моделями интеллектуального анализа данных, необходимо создать соединение с экземпляром служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f36e-117">To manage data mining models, you must first create a connection to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="7f36e-118">Соединение требуется даже в случае работы с моделями сеанса, хранящимися во временном файле.</span><span class="sxs-lookup"><span data-stu-id="7f36e-118">A connection is required even if you are working with session models stored in a temporary file.</span></span> <span data-ttu-id="7f36e-119">Дополнительные сведения о создании или изменении подключения см. в разделе [Подключение к источнику данных &#40;клиент интеллектуального анализа данных для Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="7f36e-119">For more information about how to create or change a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="7f36e-120">Если экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], к которому имеется подключение, не содержит никаких моделей и структур интеллектуального анализа данных, их можно создать с помощью мастеров и других средств этой надстройки.</span><span class="sxs-lookup"><span data-stu-id="7f36e-120">If the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you connect to does not contain any existing data mining structures or data mining models, you can create them by using the wizards and other tools provided by this add-in.</span></span> <span data-ttu-id="7f36e-121">Можно также создавать новые модели с помощью **модели интеллектуального анализа данных Расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="7f36e-121">You can also create new models by using the **Data Mining Model Advanced Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f36e-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f36e-122">See Also</span></span>  
 <span data-ttu-id="7f36e-123">[Документирование моделей интеллектуального анализа &#40;надстройки интеллектуального анализа данных для Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="7f36e-123">[Documenting Mining Models &#40;Data Mining Add-ins for Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="7f36e-124">Развертывание и масштабирование моделей интеллектуального анализа &#40;надстройки интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="7f36e-124">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)   

  

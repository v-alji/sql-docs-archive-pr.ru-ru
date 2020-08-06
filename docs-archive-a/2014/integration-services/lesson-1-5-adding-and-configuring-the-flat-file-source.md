---
title: Шаг 5. Добавление и настройка источника неструктурированных файлов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5c95ce51-e0fe-4fc5-95eb-2945929f2b13
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 504cfb4bc722627eb8ee70ec1f2c562cef8f1f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664347"
---
# <a name="step-5-adding-and-configuring-the-flat-file-source"></a><span data-ttu-id="e6d8d-102">Шаг 5. Добавление и настройка источника неструктурированных файлов</span><span class="sxs-lookup"><span data-stu-id="e6d8d-102">Step 5: Adding and Configuring the Flat File Source</span></span>
  <span data-ttu-id="e6d8d-103">В этой задаче рассматривается добавление к пакету и настройка источника неструктурированных файлов.</span><span class="sxs-lookup"><span data-stu-id="e6d8d-103">In this task, you will add and configure a Flat File source to your package.</span></span> <span data-ttu-id="e6d8d-104">Источник неструктурированных файлов представляет собой компонент потока данных, использующий метаданные, определенные диспетчером соединений с  неструктурированными файлами для описания формата и структуры данных, извлекаемых из неструктурированного файла в процессе преобразования.</span><span class="sxs-lookup"><span data-stu-id="e6d8d-104">A Flat File source is a data flow component that uses metadata defined by a Flat File connection manager to specify the format and structure of the data to be extracted from the flat file by a transform process.</span></span> <span data-ttu-id="e6d8d-105">Источник неструктурированных файлов можно настроить для получения данных из единичного неструктурированного файла путем определения формата этого файла, который предоставляется диспетчером соединений с неструктурированными файлами.</span><span class="sxs-lookup"><span data-stu-id="e6d8d-105">The Flat File source can be configured to extract data from a single flat file by using the file format definition provided by the Flat File connection manager.</span></span>  
  
 <span data-ttu-id="e6d8d-106">В этом учебнике будет настроен источник «Неструктурированный файл» для использования `Sample Flat File Source Data` созданного ранее диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="e6d8d-106">For this tutorial, you will configure the Flat File source to use the `Sample Flat File Source Data` connection manager that you previously created.</span></span>  
  
### <a name="to-add-a-flat-file-source-component"></a><span data-ttu-id="e6d8d-107">Добавление компонента источника неструктурированных файлов</span><span class="sxs-lookup"><span data-stu-id="e6d8d-107">To add a Flat File Source component</span></span>  
  
1.  <span data-ttu-id="e6d8d-108">Откройте конструктор **потока данных** , дважды щелкнув `Extract Sample Currency Data` задачу потока данных или перейдя на **вкладку Поток данных**.</span><span class="sxs-lookup"><span data-stu-id="e6d8d-108">Open the **Data Flow** designer, either by double-clicking the `Extract Sample Currency Data` data flow task or by clicking the **Data Flow tab**.</span></span>  
  
2.  <span data-ttu-id="e6d8d-109">В окне **Панель элементов служб SSIS**разверните элемент **Другие источники**и перетащите **Источник "Неструктурированный файл"** в область конструктора вкладки **Поток данных** .</span><span class="sxs-lookup"><span data-stu-id="e6d8d-109">In the **SSIS Toolbox**, expand **OtherSources**, and then drag a **Flat File Source** onto the design surface of the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="e6d8d-110">В области конструктора **поток данных** щелкните правой кнопкой мыши добавленный **источник неструктурированного файла**, выберите команду **Переименовать**и измените имя на `Extract Sample Currency Data` .</span><span class="sxs-lookup"><span data-stu-id="e6d8d-110">On the **Data Flow** design surface, right-click the newly added **Flat File Source**, click **Rename**, and change the name to `Extract Sample Currency Data`.</span></span>  
  
4.  <span data-ttu-id="e6d8d-111">Дважды щелкните источник неструктурированных файлов, чтобы открыть диалоговое окно «Редактор источника "Неструктурированный файл"».</span><span class="sxs-lookup"><span data-stu-id="e6d8d-111">Double-click the Flat File source to open the Flat File Source Editor dialog box.</span></span>  
  
5.  <span data-ttu-id="e6d8d-112">В поле **Диспетчер соединений с неструктурированными файлами** выберите `Sample Flat File Source Data` .</span><span class="sxs-lookup"><span data-stu-id="e6d8d-112">In the **Flat file connection manager** box, select `Sample Flat File Source Data`.</span></span>  
  
6.  <span data-ttu-id="e6d8d-113">Щелкните **Столбцы** и убедитесь в том, что имена столбцов заданы правильно.</span><span class="sxs-lookup"><span data-stu-id="e6d8d-113">Click **Columns** and verify that the names of the columns are correct.</span></span>  
  
7.  <span data-ttu-id="e6d8d-114">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e6d8d-114">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="e6d8d-115">Щелкните правой кнопкой мыши источник "Неструктурированный файл" и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e6d8d-115">Right-click the Flat File source and click **Properties**.</span></span>  
  
9. <span data-ttu-id="e6d8d-116">В окно свойств убедитесь, что `LocaleID` для свойства задано значение **английский (США)**.</span><span class="sxs-lookup"><span data-stu-id="e6d8d-116">In the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e6d8d-117">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="e6d8d-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e6d8d-118">Шаг 6. Добавление и настройка преобразований «Уточняющий запрос»</span><span class="sxs-lookup"><span data-stu-id="e6d8d-118">Step 6: Adding and Configuring the Lookup Transformations</span></span>](lesson-1-6-adding-and-configuring-the-lookup-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="e6d8d-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6d8d-119">See Also</span></span>  
 <span data-ttu-id="e6d8d-120">[Источник «Неструктурированный файл»](data-flow/flat-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="e6d8d-120">[Flat File Source](data-flow/flat-file-source.md) </span></span>  
 [<span data-ttu-id="e6d8d-121">Редактор диспетчера соединений с неструктурированными файлами (страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="e6d8d-121">Flat File Connection Manager Editor &#40;General Page&#41;</span></span>](general-page-of-integration-services-designers-options.md)  
  
  

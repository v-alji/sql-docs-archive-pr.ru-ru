---
title: Шаг 4. Добавление задачи потока данных в пакет | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 96af3073-8f11-4444-b934-fe8613a2d084
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4fda1de99e9fcaa683f9063e2feb1b71886a5cd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664352"
---
# <a name="step-4-adding-a-data-flow-task-to-the-package"></a><span data-ttu-id="f8ab3-102">Этап 4. Добавление задачи потока данных в пакет</span><span class="sxs-lookup"><span data-stu-id="f8ab3-102">Step 4: Adding a Data Flow Task to the Package</span></span>
  <span data-ttu-id="f8ab3-103">После того как были созданы диспетчеры соединений для исходных и целевых данных, предстоит добавить в пакет задачу потока данных.</span><span class="sxs-lookup"><span data-stu-id="f8ab3-103">After you have created the connection managers for the source and destination data, the next task is to add a Data Flow task to your package.</span></span> <span data-ttu-id="f8ab3-104">Задача потока данных включает в себя подсистему обработки потока данных, которая осуществляет передачу данных между источниками и назначениями, а также преобразует, очищает и изменяет данные при их перемещении.</span><span class="sxs-lookup"><span data-stu-id="f8ab3-104">The Data Flow task encapsulates the data flow engine that moves data between sources and destinations, and provides the functionality for transforming, cleaning, and modifying data as it is moved.</span></span> <span data-ttu-id="f8ab3-105">В задаче потока данных сосредоточена большая часть работы в процессе извлечения, преобразования и загрузки.</span><span class="sxs-lookup"><span data-stu-id="f8ab3-105">The Data Flow task is where most of the work of an extract, transform, and load (ETL) process occurs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="f8ab3-106">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]разделяет поток данных от потока управления.</span><span class="sxs-lookup"><span data-stu-id="f8ab3-106">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] separates data flow from control flow.</span></span>  
  
### <a name="to-add-a-data-flow-task"></a><span data-ttu-id="f8ab3-107">Добавление задачи потока данных</span><span class="sxs-lookup"><span data-stu-id="f8ab3-107">To add a Data Flow task</span></span>  
  
1.  <span data-ttu-id="f8ab3-108">Перейдите на вкладку **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="f8ab3-108">Click the **Control Flow** tab.</span></span>  
  
2.  <span data-ttu-id="f8ab3-109">В окне **Панель элементов служб SSIS**разверните элемент **Избранное**и перетащите элемент **Задача потока данных** в область конструктора вкладки **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="f8ab3-109">In the **SSIS Toolbox**, expand **Favorites**, and drag a **Data Flow Task** onto the design surfaceof the **Control Flow** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f8ab3-110">Если область элементов служб SSIS недоступна, выберите в главном меню "Службы SSIS", а затем "Область элементов SSIS".</span><span class="sxs-lookup"><span data-stu-id="f8ab3-110">If the SSIS Toolbox isn't available, on the main menu select SSIS then SSIS Toolbox to display the SSIS Toolbox.</span></span>  
  
3.  <span data-ttu-id="f8ab3-111">В области конструктора **поток управления** щелкните правой кнопкой мыши только что добавленную **задачу потока данных**, выберите команду **Переименовать**и измените имя на `Extract Sample Currency Data` .</span><span class="sxs-lookup"><span data-stu-id="f8ab3-111">On the **Control Flow** design surface, right-click the newly added **Data Flow Task**, click **Rename**, and change the name to `Extract Sample Currency Data`.</span></span>  
  
     <span data-ttu-id="f8ab3-112">Рекомендуется давать уникальное имя каждому компоненту, добавляемому в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="f8ab3-112">It is good practice to provide unique names to all components that you add to a design surface.</span></span> <span data-ttu-id="f8ab3-113">Для удобства применения и обслуживания имена компонентов должны описывать их функции.</span><span class="sxs-lookup"><span data-stu-id="f8ab3-113">For ease of use and maintainability, the names should describe the function that each component performs.</span></span> <span data-ttu-id="f8ab3-114">Следование этим правилам именования обеспечивает самодокументируемость пакетов служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8ab3-114">Following these naming guidelines allows your [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to be self-documenting.</span></span> <span data-ttu-id="f8ab3-115">Другим способом документирования пакетов является использование примечаний.</span><span class="sxs-lookup"><span data-stu-id="f8ab3-115">Another way to document your packages is by using annotations.</span></span> <span data-ttu-id="f8ab3-116">Дополнительные сведения о заметках см. в разделе [Использование заметок в пакетах](use-annotations-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="f8ab3-116">For more information about annotations, see [Use Annotations in Packages](use-annotations-in-packages.md).</span></span>  
  
4.  <span data-ttu-id="f8ab3-117">Щелкните правой кнопкой мыши задачу потока данных, выберите пункт **Свойства**и в окно свойств убедитесь, что `LocaleID` свойство имеет значение **Английский (США)**.</span><span class="sxs-lookup"><span data-stu-id="f8ab3-117">Right-click the Data Flow task, click **Properties**, and in the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f8ab3-118">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="f8ab3-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f8ab3-119">Шаг 5. Добавление и настройка источника неструктурированных файлов</span><span class="sxs-lookup"><span data-stu-id="f8ab3-119">Step 5: Adding and Configuring the Flat File Source</span></span>](lesson-1-5-adding-and-configuring-the-flat-file-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="f8ab3-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="f8ab3-120">See Also</span></span>  
 [<span data-ttu-id="f8ab3-121">Задача потока данных</span><span class="sxs-lookup"><span data-stu-id="f8ab3-121">Data Flow Task</span></span>](control-flow/data-flow-task.md)  
  
  

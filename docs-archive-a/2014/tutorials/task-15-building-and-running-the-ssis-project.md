---
title: Задача 15. сборка и запуск проекта служб SSIS | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 13adf4e0-216a-4992-b13d-b7b1e1629e77
ms.author: lle
author: lrtoyou1223
ms.openlocfilehash: 2a008cd848c95b48e6e22798b6ef903942b4d656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734658"
---
# <a name="task-15-building-and-running-the-ssis-project"></a><span data-ttu-id="0ec15-102">Задача 15. Сборка и запуск проекта SSIS</span><span class="sxs-lookup"><span data-stu-id="0ec15-102">Task 15: Building and Running the SSIS Project</span></span>

  <span data-ttu-id="0ec15-103">В этой задаче вы создадите и выполните проект служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="0ec15-103">In this task, you build and run the SSIS project.</span></span> <span data-ttu-id="0ec15-104">Если на компьютере установлена 64-разрядная версия Excel 2010, следует присвоить параметру **Run64BitRuntime** значение **false** , чтобы источник Excel работал.</span><span class="sxs-lookup"><span data-stu-id="0ec15-104">If you have the 64-bit version of Excel 2010 installed on your computer, you should set the value of **Run64BitRuntime** to **False** for the Excel source to work.</span></span>  
  
1.  <span data-ttu-id="0ec15-105">В окне **Обозреватель решений** в меню выберите пункт **проект** и щелкните **Свойства CleanseAndCurateSuppliers**.</span><span class="sxs-lookup"><span data-stu-id="0ec15-105">In the **Solution Explorer** window, click **Project** on the menu, and click **CleanseAndCurateSuppliers Properties**.</span></span>  
  
2.  <span data-ttu-id="0ec15-106">В диалоговом окне **Свойства** разверните узел **Свойства конфигурации** слева и нажмите кнопку **Отладка**.</span><span class="sxs-lookup"><span data-stu-id="0ec15-106">In the **Properties** dialog box, expand **Configuration Properties** on left, and click **Debugging**.</span></span>  
  
3.  <span data-ttu-id="0ec15-107">Задайте **Run64BitRuntime** для Run64BitRuntime **значение false**.</span><span class="sxs-lookup"><span data-stu-id="0ec15-107">Set **Run64BitRuntime** to **False**.</span></span>  
  
     <span data-ttu-id="0ec15-108">![Свойства проекта CleanseAndCurateSuppliers](../../2014/tutorials/media/et-buildingandrunningthessisproject-01.jpg "Свойства проекта CleanseAndCurateSuppliers")</span><span class="sxs-lookup"><span data-stu-id="0ec15-108">![CleanseAndCurateSuppliers Project Properties](../../2014/tutorials/media/et-buildingandrunningthessisproject-01.jpg "CleanseAndCurateSuppliers Project Properties")</span></span>  
  
4.  <span data-ttu-id="0ec15-109">Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0ec15-109">Click **OK** to close the **Properties** dialog box.</span></span>  
  
5.  <span data-ttu-id="0ec15-110">Щелкните **Сборка** в строке меню и выберите **Сборка CleanseAndCurateSuppliers**.</span><span class="sxs-lookup"><span data-stu-id="0ec15-110">Click **Build** on menu bar and click **Build CleanseAndCurateSuppliers**.</span></span> <span data-ttu-id="0ec15-111">Убедитесь, что при построении не было ошибок.</span><span class="sxs-lookup"><span data-stu-id="0ec15-111">Make sure that there are no build errors.</span></span>  
  
6.  <span data-ttu-id="0ec15-112">Щелкните **Отладка** в строке меню и выберите **начать отладку**.</span><span class="sxs-lookup"><span data-stu-id="0ec15-112">Click **Debug** on the menu bar and click **Start Debugging**.</span></span>  
  
7.  <span data-ttu-id="0ec15-113">Проверьте сообщения в окне **ход выполнения** и убедитесь, что пакет успешно выполнен и завершил работу.</span><span class="sxs-lookup"><span data-stu-id="0ec15-113">Review messages in the **Progress** window and verify that package executed and ended successfully.</span></span>  
  
     <span data-ttu-id="0ec15-114">![Результаты из окна хода выполнения](../../2014/tutorials/media/et-buildingandrunningthessisproject-02.jpg "Результаты из окна хода выполнения")</span><span class="sxs-lookup"><span data-stu-id="0ec15-114">![Results from Progress Window](../../2014/tutorials/media/et-buildingandrunningthessisproject-02.jpg "Results from Progress Window")</span></span>  
  
     <span data-ttu-id="0ec15-115">![Окончательное состояние из окна хода выполнения](../../2014/tutorials/media/et-buildingandrunningthessisproject-03.jpg "Окончательное состояние из окна хода выполнения")</span><span class="sxs-lookup"><span data-stu-id="0ec15-115">![Final Status from Progress Window](../../2014/tutorials/media/et-buildingandrunningthessisproject-03.jpg "Final Status from Progress Window")</span></span>  
  
8.  <span data-ttu-id="0ec15-116">Щелкните **Отладка** в строке меню и нажмите кнопку " **Отключить отладку** ", чтобы отключить сеанс отладки.</span><span class="sxs-lookup"><span data-stu-id="0ec15-116">Click **Debug** on menu bar and click **Stop Debugging** to stop the debugging session.</span></span> <span data-ttu-id="0ec15-117">Если пакет вызывает ошибку, необходимо включить средства просмотра данных и посмотреть на потоки данных между компонентами.</span><span class="sxs-lookup"><span data-stu-id="0ec15-117">If the package fails, you should enable data viewers and see how the data flows between components.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="0ec15-118">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="0ec15-118">Next Step</span></span>  
 [<span data-ttu-id="0ec15-119">Задача 16. Проверка с помощью диспетчера основных данных</span><span class="sxs-lookup"><span data-stu-id="0ec15-119">Task 16: Verifying with Master Data Manager</span></span>](../../2014/tutorials/task-16-verifying-with-master-data-manager.md)  
  
  

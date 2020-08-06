---
title: Шаг 2. Создание поврежденного файла | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cd0b18dc-66c3-4d88-86ef-8e40cb660fae
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0dd5fbe942774192881489e9ea430672f9da5083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658889"
---
# <a name="step-2-creating-a-corrupted-file"></a><span data-ttu-id="26d49-102">Этап 2. Создание поврежденного файла</span><span class="sxs-lookup"><span data-stu-id="26d49-102">Step 2: Creating a Corrupted File</span></span>
  <span data-ttu-id="26d49-103">Для демонстрации настройки и обработки ошибок преобразования необходимо создать образец неструктурированного файла, который при обработке вызовет сбой в работе компонента.</span><span class="sxs-lookup"><span data-stu-id="26d49-103">In order to demonstrate the configuration and handling of transformation errors, you will have to create a sample flat file that when processed causes a component to fail.</span></span>  
  
 <span data-ttu-id="26d49-104">В этой задаче предстоит скопировать существующий образец неструктурированного файла.</span><span class="sxs-lookup"><span data-stu-id="26d49-104">In this task, you will create a copy of an existing sample flat file.</span></span> <span data-ttu-id="26d49-105">Затем предстоит открыть его в приложении «Блокнот» и изменить столбец **CurrencyID** таким образом, чтобы при поиске совпадений во время преобразования произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="26d49-105">You will then open the file in Notepad and edit the **CurrencyID** column to ensure that it will fail to produce a match during the transformations lookup.</span></span> <span data-ttu-id="26d49-106">При обработке нового файла произойдет сбой в преобразовании «Уточняющий запрос» для CurrencyKey, что приведет к ошибке в работе всего пакета.</span><span class="sxs-lookup"><span data-stu-id="26d49-106">When the new file is processed, the lookup failure will cause the Currency Key Lookup transformation to fail and therefore fail the rest of the package.</span></span> <span data-ttu-id="26d49-107">После создания поврежденного образца файла предстоит выполнить пакет, чтобы просмотреть его поведение при сбое.</span><span class="sxs-lookup"><span data-stu-id="26d49-107">After you have created the corrupted sample file, you will run the package to view the package failure.</span></span>  
  
### <a name="to-create-a-corrupted-sample-flat-file"></a><span data-ttu-id="26d49-108">Создание поврежденного образца неструктурированного файла</span><span class="sxs-lookup"><span data-stu-id="26d49-108">To create a corrupted sample flat file</span></span>  
  
1.  <span data-ttu-id="26d49-109">В приложении «Блокнот» или другом текстовом редакторе откройте файл Currency_VEB.txt.</span><span class="sxs-lookup"><span data-stu-id="26d49-109">In Notepad or any other text editor, open the Currency_VEB.txt file.</span></span>  
  
     <span data-ttu-id="26d49-110">Образцы данных включаются в пакеты занятий по службам SSIS.</span><span class="sxs-lookup"><span data-stu-id="26d49-110">The sample data is included with the SSIS Lesson packages.</span></span> <span data-ttu-id="26d49-111">Чтобы загрузить образцы данных и пакеты занятий выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="26d49-111">To download the sample data and the lesson packages, do the following.</span></span>  
  
    1.  <span data-ttu-id="26d49-112">Перейдите к разделу [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=267527).</span><span class="sxs-lookup"><span data-stu-id="26d49-112">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=267527).</span></span>  
  
    2.  <span data-ttu-id="26d49-113">Перейдите на вкладку **Downloads (загрузки** ).</span><span class="sxs-lookup"><span data-stu-id="26d49-113">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="26d49-114">Щелкните файл SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="26d49-114">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
2.  <span data-ttu-id="26d49-115">Используйте функцию поиска и замены текстового редактора, чтобы найти все экземпляры `VEB` и заменить их на `BAD` .</span><span class="sxs-lookup"><span data-stu-id="26d49-115">Use the text editor's find and replace feature to find all instances of `VEB` and replace them with `BAD`.</span></span>  
  
3.  <span data-ttu-id="26d49-116">В той же папке, что и другие образцы файлов данных, сохраните измененный файл как `Currency_BAD.txt` .</span><span class="sxs-lookup"><span data-stu-id="26d49-116">In the same folder as the other sample data files, save the modified file as `Currency_BAD.txt`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="26d49-117">Убедитесь, что `Currency_BAD.txt` файл сохранен в той же папке, что и другие образцы файлов данных.</span><span class="sxs-lookup"><span data-stu-id="26d49-117">Make sure that `Currency_BAD.txt` is saved the same folder as the other sample data files.</span></span>  
  
4.  <span data-ttu-id="26d49-118">Закройте текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="26d49-118">Close your text editor.</span></span>  
  
### <a name="to-verify-that-an-error-will-occur-during-run-time"></a><span data-ttu-id="26d49-119">Проверка факта возникновения ошибки во время выполнения</span><span class="sxs-lookup"><span data-stu-id="26d49-119">To verify that an error will occur during run time</span></span>  
  
1.  <span data-ttu-id="26d49-120">В меню **Отладка** выберите пункт **Начать отладку**.</span><span class="sxs-lookup"><span data-stu-id="26d49-120">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="26d49-121">При третьем проходе потока данных в преобразовании Lookup Currency Key будет предпринята попытка обработать файл Currency_BAD.txt, при этом произойдет ошибка преобразования.</span><span class="sxs-lookup"><span data-stu-id="26d49-121">On the third iteration of the data flow, the Lookup Currency Key transformation tries to process the Currency_BAD.txt file, and the transformation will fail.</span></span> <span data-ttu-id="26d49-122">Ошибка преобразования вызовет отказ работы всего пакета.</span><span class="sxs-lookup"><span data-stu-id="26d49-122">The failure of the transformation will cause the whole package to fail.</span></span>  
  
2.  <span data-ttu-id="26d49-123">В меню **Отладка** выберите пункт **Остановить отладку**.</span><span class="sxs-lookup"><span data-stu-id="26d49-123">On the **Debug** menu, click **Stop Debugging**.</span></span>  
  
3.  <span data-ttu-id="26d49-124">В области конструктора откройте вкладку **Результаты выполнения** .</span><span class="sxs-lookup"><span data-stu-id="26d49-124">On the design surface, click the **Execution Results** tab.</span></span>  
  
4.  <span data-ttu-id="26d49-125">Просмотрите журнал и убедитесь, что произошла следующая необработанная ошибка:</span><span class="sxs-lookup"><span data-stu-id="26d49-125">Browse through the log and verify that the following unhandled error occurred:</span></span>  
  
     `[Lookup Currency Key[27]] Error: Row yielded no match during lookup.`  
  
    > [!NOTE]  
    >  <span data-ttu-id="26d49-126">Число 27 представляет собой идентификатор компонента.</span><span class="sxs-lookup"><span data-stu-id="26d49-126">The number 27 is the ID of the component.</span></span> <span data-ttu-id="26d49-127">Это значение присваивается при создании потока данных, так что в пакете оно может отличаться от приведенного в учебнике.</span><span class="sxs-lookup"><span data-stu-id="26d49-127">This value is assigned when you build the data flow, and the value in your package may be different.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="26d49-128">Next Steps</span><span class="sxs-lookup"><span data-stu-id="26d49-128">Next Steps</span></span>  
 [<span data-ttu-id="26d49-129">Шаг 3. Добавление перенаправления потока ошибок</span><span class="sxs-lookup"><span data-stu-id="26d49-129">Step 3: Adding Error Flow Redirection</span></span>](lesson-4-3-adding-error-flow-redirection.md)  
  
  

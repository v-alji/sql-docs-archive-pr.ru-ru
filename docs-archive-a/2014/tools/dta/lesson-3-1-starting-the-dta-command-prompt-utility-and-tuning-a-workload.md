---
title: Начало работы с программой командной строки dta и настройка рабочей нагрузки | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], tutorials
ms.assetid: f34a5acf-1f3b-4484-a770-6470cb925ab0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4b2b1755a2ce8299556ab7d0ae14c89d3b2c8554
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727646"
---
# <a name="starting-the-dta-command-prompt-utility-and-tuning-a-workload"></a><span data-ttu-id="de7e5-102">Начало работы с программой командной строки dta и настройка рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="de7e5-102">Starting the dta Command Prompt Utility and Tuning a Workload</span></span>
  <span data-ttu-id="de7e5-103"> Эта задача помогает запустить программу **dta**, просмотреть ее справку, а затем использовать эту программу для настройки рабочей нагрузки из командной строки.</span><span class="sxs-lookup"><span data-stu-id="de7e5-103">This task guides you through starting the **dta** utility, viewing its Help, and then using it to tune a workload from the command prompt.</span></span> <span data-ttu-id="de7e5-104">В нем используется рабочая нагрузка, MyScript. SQL, созданная для помощник по настройке ядра СУБДного графического интерфейса пользователя (GUI) для [настройки рабочей нагрузки](lesson-1-1-tuning-a-workload.md).</span><span class="sxs-lookup"><span data-stu-id="de7e5-104">It uses the workload, MyScript.sql, which you created for the Database Engine Tuning Advisor graphical user interface (GUI) practice [Tuning a Workload](lesson-1-1-tuning-a-workload.md).</span></span>  
  
 <span data-ttu-id="de7e5-105">В учебнике используется образец базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="de7e5-105">The tutorial uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="de7e5-106">В целях повышения безопасности образцы баз данных не установлены.</span><span class="sxs-lookup"><span data-stu-id="de7e5-106">For security reasons, the sample databases are not installed by default.</span></span> <span data-ttu-id="de7e5-107">Дополнительные сведения об установке образцов баз данных см. в статье [Установка образцов SQL Server и образцов баз данных](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="de7e5-107">To install the sample databases, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
 <span data-ttu-id="de7e5-108">В следующих задачах рассматривается открытие командной строки, запуск программы командной строки **dta** , просмотр справки по ее синтаксису, а также настройка простой рабочей нагрузки MyScript.sql, которая была создана в примере [Настройка рабочей нагрузки](lesson-1-1-tuning-a-workload.md).</span><span class="sxs-lookup"><span data-stu-id="de7e5-108">The following tasks guide you through opening a command prompt, starting the **dta** command prompt utility, viewing its syntax Help, and tuning a simple workload, MyScript.sql, which you created in [Tuning a Workload](lesson-1-1-tuning-a-workload.md).</span></span>  
  
### <a name="to-start-the-dta-command-prompt-utility-and-view-help"></a><span data-ttu-id="de7e5-109">Запуск программы командной строки dta и просмотр справки</span><span class="sxs-lookup"><span data-stu-id="de7e5-109">To start the dta command prompt utility and view Help</span></span>  
  
1.  <span data-ttu-id="de7e5-110">В меню **Пуск** наведите указатель на пункт **Все программы**, затем на пункт **Стандартные**и выберите пункт **Командная строка**.</span><span class="sxs-lookup"><span data-stu-id="de7e5-110">On the **Start** menu, point to **All Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="de7e5-111">В командной строке введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="de7e5-111">At the command prompt, type the following, and press ENTER:</span></span>  
  
    ```  
    dta -? | more  
    ```  
  
     <span data-ttu-id="de7e5-112">Часть `| more` этой команды является необязательной.</span><span class="sxs-lookup"><span data-stu-id="de7e5-112">The `| more` part of this command is optional.</span></span> <span data-ttu-id="de7e5-113">Однако ее использование позволит пролистывать справку по синтаксису этой программы.</span><span class="sxs-lookup"><span data-stu-id="de7e5-113">However, using it enables you to page through the syntax help for the utility.</span></span> <span data-ttu-id="de7e5-114">Нажимайте клавишу ВВОД, чтобы просматривать текст справки построчно, или клавишу ПРОБЕЛ, чтобы перелистывать текст справки по страницам.</span><span class="sxs-lookup"><span data-stu-id="de7e5-114">Press ENTER to advance the help text by the line, or press the SPACEBAR to advance it by the page.</span></span>  
  
### <a name="to-tune-a-simple-workload-by-using-the-dta-command-prompt-utility"></a><span data-ttu-id="de7e5-115">Настройка простой рабочей нагрузки с помощью программы командной строки dta</span><span class="sxs-lookup"><span data-stu-id="de7e5-115">To tune a simple workload by using the dta command prompt utility</span></span>  
  
1.  <span data-ttu-id="de7e5-116">В командной строке перейдите в каталог, где был сохранен файл MyScript.sql.</span><span class="sxs-lookup"><span data-stu-id="de7e5-116">At the command prompt, navigate to the directory where you have stored the MyScript.sql file.</span></span>  
  
2.  <span data-ttu-id="de7e5-117">В командной строке введите следующую команду и нажмите клавишу ВВОД, чтобы запустить команду и начать сеанс настройки (обратите внимание, что программа учитывает регистр в ходе синтаксического анализа команд):</span><span class="sxs-lookup"><span data-stu-id="de7e5-117">At the command prompt, type the following, and press ENTER to run the command and start the tuning session (note that the utility is case-sensitive when it parses commands):</span></span>  
  
    ```  
    dta -S YourServerName\YourSQLServerInstanceName -E -D AdventureWorks2012 -if MyScript.sql -s MySession2 -of MySession2OutputScript.sql -ox MySession2Output.xml -fa IDX_IV -fp NONE -fk NONE  
    ```  
  
     <span data-ttu-id="de7e5-118">где `-S` указывает имя сервера и экземпляр служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , на котором установлена база данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="de7e5-118">where `-S` specifies the name of your server and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance where the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database is installed.</span></span> <span data-ttu-id="de7e5-119">Параметр `-E` указывает, что требуется использовать доверительное соединение с экземпляром. Это целесообразно, если соединение устанавливается с учетной записью домена Windows.</span><span class="sxs-lookup"><span data-stu-id="de7e5-119">The setting `-E` specifies that you want to use a trusted connection to the instance, which is appropriate if you are connecting with a Windows domain account.</span></span> <span data-ttu-id="de7e5-120">Параметр `-D` указывает базу данных, которую нужно настроить, параметр `-if` указывает файл рабочей нагрузки, параметр `-s` указывает имя сеанса, параметр `-of` указывает файл, в который средство должно записать скрипт рекомендаций [!INCLUDE[tsql](../../includes/tsql-md.md)] , а параметр `-ox` указывает файл, в который средство должно записать рекомендации в формате XML.</span><span class="sxs-lookup"><span data-stu-id="de7e5-120">The setting `-D` specifies the database that you want to tune, `-if` specifies the workload file, `-s` specifies the session name, `-of` specifies the file to which you want the tool to write the [!INCLUDE[tsql](../../includes/tsql-md.md)] recommendations script, and `-ox` specifies the file to which you want the tool to write the recommendations in XML format.</span></span> <span data-ttu-id="de7e5-121">Последние три параметра управляют настройкой следующим образом: параметр `-fa IDX_IV` указывает, что помощник по настройке ядра СУБД должен добавлять только индексы (как кластеризованные, так и некластеризованные) и индексированные представления; параметр `-fp NONE` указывает, что в ходе анализа не должна учитываться стратегия секционирования; параметр `-fk NONE` указывает, что существующие в базе данных структуры физического проектирования не должны сохраняться при формировании рекомендаций помощником по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="de7e5-121">The last three switches specify tuning options as follows: `-fa IDX_IV` specifies that Database Engine Tuning Advisor should only consider adding indexes (both clustered and nonclustered) and indexed views; `-fp NONE` specifies that no partition strategy should be considered during analysis; and `-fk NONE` specifies that no existing physical design structures in the database must be kept when Database Engine Tuning Advisor makes its recommendations.</span></span>  
  
3.  <span data-ttu-id="de7e5-122">Закончив настройку рабочей нагрузки, помощник по настройке ядра СУБД выведет сообщение, свидетельствующее об успешном завершении сеанса настройки.</span><span class="sxs-lookup"><span data-stu-id="de7e5-122">After Database Engine Tuning Advisor finishes tuning the workload, it displays a message indicating that your tuning session completed successfully.</span></span> <span data-ttu-id="de7e5-123">Можно просмотреть результаты настройки, используя среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , чтобы открыть файлы MySession2OutputScript.sql и MySession2Output.xml.</span><span class="sxs-lookup"><span data-stu-id="de7e5-123">You can view the tuning results, by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to open the files MySession2OutputScript.sql and MySession2Output.xml.</span></span> <span data-ttu-id="de7e5-124">Кроме того, сеанс настройки MySession2 можно открыть в графическом интерфейсе помощника по настройке ядра СУБД и просмотреть его рекомендации и отчеты, что рассматривалось в разделах [Просмотр рекомендаций по настройке](lesson-1-2-viewing-tuning-recommendations.md) и [Просмотр отчетов настройки](lesson-1-3-viewing-tuning-reports.md).</span><span class="sxs-lookup"><span data-stu-id="de7e5-124">Alternatively, you can also open the MySession2 tuning session in the Database Engine Tuning Advisor GUI and view its recommendations and reports in the same way that you did in [Viewing Tuning Recommendations](lesson-1-2-viewing-tuning-recommendations.md) and [Viewing Tuning Reports](lesson-1-3-viewing-tuning-reports.md).</span></span>  
  
## <a name="summary"></a><span data-ttu-id="de7e5-125">Итоги</span><span class="sxs-lookup"><span data-stu-id="de7e5-125">Summary</span></span>  
 <span data-ttu-id="de7e5-126">Завершена настройка простой рабочей нагрузки в командной строке с помощью программы **dta** .</span><span class="sxs-lookup"><span data-stu-id="de7e5-126">You have completed tuning a simple workload from the command prompt by using the **dta** utility.</span></span> <span data-ttu-id="de7e5-127">Это средство предоставляет также множество других возможностей настройки.</span><span class="sxs-lookup"><span data-stu-id="de7e5-127">This tool provides many other tuning options.</span></span> <span data-ttu-id="de7e5-128">Дополнительные сведения см. в справке средства (**dta -?**) и в разделе справки [dta, программа](dta-utility.md) .</span><span class="sxs-lookup"><span data-stu-id="de7e5-128">Refer to the tool Help (**dta -?**) and the reference topic [dta Utility](dta-utility.md) for more information.</span></span>  
  
## <a name="after-you-finish-this-tutorial"></a><span data-ttu-id="de7e5-129">После завершения работы с этим учебником</span><span class="sxs-lookup"><span data-stu-id="de7e5-129">After You Finish This Tutorial</span></span>  
 <span data-ttu-id="de7e5-130">Выполнив задания этого учебника, изучите следующие разделы, чтобы получить дополнительные сведения о помощнике по настройке ядра СУБД:</span><span class="sxs-lookup"><span data-stu-id="de7e5-130">After you finish the lessons in this tutorial, refer to the following topics for more information about Database Engine Tuning Advisor:</span></span>  
  
-   <span data-ttu-id="de7e5-131">В статье[Database Engine Tuning Advisor](../../relational-databases/performance/database-engine-tuning-advisor.md) описывается выполнение задач с использованием этого средства.</span><span class="sxs-lookup"><span data-stu-id="de7e5-131">[Database Engine Tuning Advisor](../../relational-databases/performance/database-engine-tuning-advisor.md) for descriptions of how to perform tasks with this tool.</span></span>  
  
-   <span data-ttu-id="de7e5-132">[dta Utility](dta-utility.md) — справочный материал по программе командной строки и дополнительному XML-файлу, который вы можете использовать для управления ее работой.</span><span class="sxs-lookup"><span data-stu-id="de7e5-132">[dta Utility](dta-utility.md) for reference material on the command prompt utility and the optional XML file you can use to control the operation of the utility.</span></span>  
  
 <span data-ttu-id="de7e5-133">Чтобы вернуться к началу учебника, воспользуйтесь ссылкой [Учебник. Помощник по настройке ядра СУБД](tutorial-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="de7e5-133">To return to the start of the tutorial, see [Tutorial: Database Engine Tuning Advisor](tutorial-database-engine-tuning-advisor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de7e5-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="de7e5-134">See Also</span></span>  
 [<span data-ttu-id="de7e5-135">Учебники по компоненту ядра СУБД</span><span class="sxs-lookup"><span data-stu-id="de7e5-135">Database Engine Tutorials</span></span>](../../relational-databases/database-engine-tutorials.md)  
  
  
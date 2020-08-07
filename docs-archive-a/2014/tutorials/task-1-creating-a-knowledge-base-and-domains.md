---
title: Задача 1. Создание базы знаний и доменов | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 7d74a60b-8933-4038-bcbb-4e9dcc4f70e9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce1b22e3d677e831a1d518dacc1267ad0e6be236
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731246"
---
# <a name="task-1-creating-a-knowledge-base-and-domains"></a><span data-ttu-id="dbbfa-102">Задача 1. Создание базы знаний и доменов</span><span class="sxs-lookup"><span data-stu-id="dbbfa-102">Task 1: Creating a Knowledge Base and Domains</span></span>
  <span data-ttu-id="dbbfa-103">В этой задаче вы создадите базу знаний **поставщиков** и создадите домены, которые будут использоваться для очистки данных и сопоставления данных для удаления дубликатов.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-103">In this task, you create the **Suppliers** knowledge base and create domains that is used for cleansing data and matching data to remove duplicates.</span></span>  
  
1.  <span data-ttu-id="dbbfa-104">Запустите **Data Quality Client**.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-104">Launch **Data Quality Client**.</span></span> <span data-ttu-id="dbbfa-105">В меню **Пуск**последовательно выберите **пункты все программы**, **Microsoft SQL Server 2012**, **службы Data Quality Services**и щелкните **Data Quality Client**.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-105">Click **Start**, point to **All Programs**, click **Microsoft SQL Server 2012**, click **Data Quality Services**, and then click **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="dbbfa-106">В диалоговом окне **соединение с сервером** выберите экземпляр сервера базы данных, на котором установлено DQS, и нажмите кнопку **подключить**.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-106">In the **Connect to Server** dialog box, select the database server instance on which the DQS is installed, and click **Connect**.</span></span>  
  
     <span data-ttu-id="dbbfa-107">![Диалоговое окно «соединение с сервером»](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-01.jpg "Диалоговое окно «Подключение к серверу»")</span><span class="sxs-lookup"><span data-stu-id="dbbfa-107">![Connect to Server Dialog Box](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-01.jpg "Connect to Server Dialog Box")</span></span>  
  
3.  <span data-ttu-id="dbbfa-108">На домашней странице Data Quality Client в области **Управление базой знаний** щелкните **Новая база знаний**.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-108">In the Data Quality Client home page, in the **Knowledge Base Management** pane, click **New Knowledge Base**.</span></span>  
  
     <span data-ttu-id="dbbfa-109">![Управление базами знаний — новая база знаний](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-02.jpg "Управление базами знаний — новая база знаний")</span><span class="sxs-lookup"><span data-stu-id="dbbfa-109">![Knowledge Base Management - New KB](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-02.jpg "Knowledge Base Management - New KB")</span></span>  
  
4.  <span data-ttu-id="dbbfa-110">Введите **поставщики** для **имени** базы знаний.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-110">Enter **Suppliers** for **Name** of the knowledge base.</span></span>  
  
     <span data-ttu-id="dbbfa-111">![Новая база знаний — управление доменом](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-03.jpg "Новая база знаний — управление доменом")</span><span class="sxs-lookup"><span data-stu-id="dbbfa-111">![New Knowledge Base - Domain Management](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-03.jpg "New Knowledge Base - Domain Management")</span></span>  
  
5.  <span data-ttu-id="dbbfa-112">Убедитесь, что для параметра **создать базу знаний из** поля установлено значение **нет** , так как вы создаете базу знаний **поставщики** с нуля.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-112">Confirm that **Create Knowledge Base from** field is set to **None** since you are creating the **Suppliers** knowledge base from scratch.</span></span>  
  
6.  <span data-ttu-id="dbbfa-113">Убедитесь, что для **действия** выбрано **Управление доменами** , и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-113">Confirm that **Domain Management** is selected for the **Activity** and click **Next**.</span></span> <span data-ttu-id="dbbfa-114">Действие «Управление доменами» позволяет создавать домены в базе знаний и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-114">The Domain Management activity lets you create and manage domains in the knowledge base.</span></span>  
  
7.  <span data-ttu-id="dbbfa-115">В окне " **Управление доменами** " нажмите кнопку **создать домен** на панели инструментов, чтобы создать домен.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-115">In the **Domain Management** window, click **Create a domain** toolbar button to create a domain.</span></span>  
  
     <span data-ttu-id="dbbfa-116">![Кнопка панели инструментов «Создание домена»](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-04.jpg "Кнопка панели инструментов «Создание домена»")</span><span class="sxs-lookup"><span data-stu-id="dbbfa-116">![Create Domain Toolbar Button](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-04.jpg "Create Domain Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="dbbfa-117">В диалоговом окне **Создание домена** введите **идентификатор поставщика** в поле **доменное имя**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-117">In the **Create Domain** dialog box, type **Supplier ID** for the **Domain Name**, and click **OK**.</span></span>  
  
     <span data-ttu-id="dbbfa-118">![Диалоговое окно «Создание домена»](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-05.jpg "Диалоговое окно «Создание домена»")</span><span class="sxs-lookup"><span data-stu-id="dbbfa-118">![Create Domain Dialog Box](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-05.jpg "Create Domain Dialog Box")</span></span>  
  
9. <span data-ttu-id="dbbfa-119">Повторите предыдущий шаг, чтобы создать следующие домены со всеми значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-119">Repeat previous step to create the following domains with all the default settings.</span></span> <span data-ttu-id="dbbfa-120">Чтобы упростить учебник, необходимо задать **тип данных** для всех доменов в виде **строки**.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-120">To keep the tutorial simple, you set the **Data Type** of all the domains as **String**.</span></span> <span data-ttu-id="dbbfa-121">Также допускаются типы данных: Integer, Decimal и Date.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-121">The other allowed data types are: Integer, Decimal, and Date.</span></span> <span data-ttu-id="dbbfa-122">Если выбран параметр **использовать ведущие значения** (по умолчанию), все синонимы заменяются ведущим значением группы синонимов в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-122">When the **Use Leading Values** option is selected (default), all synonyms are replaced with the leading value of the synonym group in the output.</span></span> <span data-ttu-id="dbbfa-123">Параметр **нормализации строк** (по умолчанию) удаляет все специальные символы в значениях домена.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-123">Setting **Normalize String** option (default) removes any special characters in the domain values.</span></span> <span data-ttu-id="dbbfa-124">Параметр **Формат вывода в** позволяет выбрать форматирование, применяемое при выводе значений данных в домене.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-124">The **Format Output to** option lets you select the formatting that is applied when the data values in the domain are output.</span></span> <span data-ttu-id="dbbfa-125">Выберите **включить средство проверки орфографии** (по умолчанию) для запуска средства проверки орфографии во всех строковых значениях при заполнении домена.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-125">Select **Enable Speller** (default) to run Speller on all string values when populating the domain.</span></span> <span data-ttu-id="dbbfa-126">**Языковой параметр указывает** языковую версию средства **проверки орфографии** , которую необходимо применить.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-126">The **Language** setting specifies which language version of the **Speller** you want to apply.</span></span> <span data-ttu-id="dbbfa-127">Выберите **Отключить алгоритмы синтаксических ошибок** для заполнения домена без проверки строковых значений на наличие синтаксических ошибок.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-127">Select **Disable Syntax Error Algorithms** to populate the domain without checking string values for syntax errors.</span></span> <span data-ttu-id="dbbfa-128">Дополнительные сведения см. в разделе [Создание домена](https://msdn.microsoft.com/library/hh510401.aspx) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="dbbfa-128">See [Create a Domain](https://msdn.microsoft.com/library/hh510401.aspx) topic in the MSDN library for more details.</span></span>  
  
    -   <span data-ttu-id="dbbfa-129">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="dbbfa-129">Supplier Name</span></span>  
  
    -   <span data-ttu-id="dbbfa-130">Контактный адрес электронной почты</span><span class="sxs-lookup"><span data-stu-id="dbbfa-130">Contact Email</span></span>  
  
    -   <span data-ttu-id="dbbfa-131">Строка адреса</span><span class="sxs-lookup"><span data-stu-id="dbbfa-131">Address Line</span></span>  
  
    -   <span data-ttu-id="dbbfa-132">Город</span><span class="sxs-lookup"><span data-stu-id="dbbfa-132">City</span></span>  
  
    -   <span data-ttu-id="dbbfa-133">Состояние</span><span class="sxs-lookup"><span data-stu-id="dbbfa-133">State</span></span>  
  
    -   <span data-ttu-id="dbbfa-134">Страна или регион</span><span class="sxs-lookup"><span data-stu-id="dbbfa-134">Country</span></span>  
  
    -   <span data-ttu-id="dbbfa-135">Почтовый индекс</span><span class="sxs-lookup"><span data-stu-id="dbbfa-135">Zip</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="dbbfa-136">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="dbbfa-136">Next Step</span></span>  
 [<span data-ttu-id="dbbfa-137">Задача 2. Добавление значений домена вручную</span><span class="sxs-lookup"><span data-stu-id="dbbfa-137">Task 2: Adding Domain Values Manually</span></span>](../../2014/tutorials/task-2-adding-domain-values-manually.md)  
  
  

---
title: Сравнение реплицируемых таблиц для поиска различий (программирование репликации) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- tablediff utility
- comparing replicated tables
ms.assetid: cd253a17-0c85-42b4-912c-690169ebe799
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0d804c7d4ac9cc54fa144b7054c6032663b76c0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750800"
---
# <a name="compare-replicated-tables-for-differences-replication-programming"></a><span data-ttu-id="259dc-102">сравнить реплицируемые таблицы на предмет различий (программирование репликации)</span><span class="sxs-lookup"><span data-stu-id="259dc-102">Compare Replicated Tables for Differences (Replication Programming)</span></span>
  <span data-ttu-id="259dc-103">Проверка статей используется для определения того, совпадают ли опубликованные данные в статьях таблицы на издателе с данными  на подписчике. В результате могут быть выявлены расхождения.</span><span class="sxs-lookup"><span data-stu-id="259dc-103">Article validation is used to determine if published data for table articles at the Publisher and Subscriber are not identical, which can indicate non-convergence.</span></span> <span data-ttu-id="259dc-104">Дополнительные сведения см. в статье [Проверка реплицированных данных](../validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="259dc-104">For more information, see [Validate Replicated Data](../validate-data-at-the-subscriber.md).</span></span> <span data-ttu-id="259dc-105">Однако проверка дает только сведения о том, есть расхождение или нет. Никаких подробностей о расхождении данных в исходной таблице и целевой таблице не сообщается.</span><span class="sxs-lookup"><span data-stu-id="259dc-105">However, validation only returns pass or fail information and does not provide any information about what is different between the source and destination tables.</span></span> <span data-ttu-id="259dc-106">Программа командной строки **tablediff** возвращает подробные сведения о расхождениях в двух таблицах и даже может создать скрипт [!INCLUDE[tsql](../../../includes/tsql-md.md)] для приведения подписки в соответствие с данными на издателе.</span><span class="sxs-lookup"><span data-stu-id="259dc-106">The **tablediff** command prompt utility returns detailed difference information between two tables and can even generate a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script to bring a subscription into convergence with data at the Publisher.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="259dc-107">Программа **tablediff** поддерживается только для серверов [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="259dc-107">The **tablediff** utility is only supported for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] servers.</span></span>  
  
### <a name="to-compare-replicated-tables-for-differences-using-tablediff"></a><span data-ttu-id="259dc-108">Поиск различий в реплицированных таблицах с помощью средства tablediff</span><span class="sxs-lookup"><span data-stu-id="259dc-108">To compare replicated tables for differences using tablediff</span></span>  
  
1.  <span data-ttu-id="259dc-109">Запустите средство [tablediff Utility](../../../tools/tablediff-utility.md)из командной строки любого сервера в топологии репликации.</span><span class="sxs-lookup"><span data-stu-id="259dc-109">From the command prompt at any server in a replication topology, run the [tablediff Utility](../../../tools/tablediff-utility.md).</span></span> <span data-ttu-id="259dc-110">Укажите значения следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="259dc-110">Specify the following parameters:</span></span>  
  
    -   <span data-ttu-id="259dc-111">**-sourceserver** — имя сервера, данные на котором считаются верными (обычно это издатель).</span><span class="sxs-lookup"><span data-stu-id="259dc-111">**-sourceserver** - name of the server on which the data is known to be correct, usually the Publisher.</span></span>  
  
    -   <span data-ttu-id="259dc-112">**-sourcedatabase** — имя базы данных, содержащей правильные данные.</span><span class="sxs-lookup"><span data-stu-id="259dc-112">**-sourcedatabase** - name of the database containing the correct data.</span></span>  
  
    -   <span data-ttu-id="259dc-113">**-sourcetable** — имя исходной таблицы для сравниваемой статьи.</span><span class="sxs-lookup"><span data-stu-id="259dc-113">**-sourcetable** - name of the source table for the article being compared.</span></span>  
  
    -   <span data-ttu-id="259dc-114">**-sourceschema** — владелец схемы исходной таблицы, если не используется схема по умолчанию (необязательно).</span><span class="sxs-lookup"><span data-stu-id="259dc-114">(Optional) **-sourceschema** - schema owner of the source table, if not the default schema.</span></span>  
  
    -   <span data-ttu-id="259dc-115">**-sourceuser** и **-sourcepassword** , если для подключения к издателю используется проверка подлинности SQL Server (необязательно).</span><span class="sxs-lookup"><span data-stu-id="259dc-115">(Optional) **-sourceuser** and **-sourcepassword** when using SQL Server Authentication to connect to the Publisher.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="259dc-116">По возможности используйте аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="259dc-116">When possible, use Windows Authentication.</span></span> <span data-ttu-id="259dc-117">При необходимости использования проверки подлинности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] предлагайте пользователям вводить учетные данные во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="259dc-117">If you must use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="259dc-118">В случае необходимости хранения учетных данных в файле скрипта этот файл следует защищать во избежание несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="259dc-118">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
    -   <span data-ttu-id="259dc-119">**-destinationserver** — имя сервера, данные которого сравниваются (обычно подписчик).</span><span class="sxs-lookup"><span data-stu-id="259dc-119">**-destinationserver** - name of the server on which the data is being compared, usually a Subscriber.</span></span>  
  
    -   <span data-ttu-id="259dc-120">**-destinationdatabase** — имя сравниваемой базы данных.</span><span class="sxs-lookup"><span data-stu-id="259dc-120">**-destinationdatabase** - name of a the database being compared.</span></span>  
  
    -   <span data-ttu-id="259dc-121">**-destinationdatabase** — имя сравниваемой таблицы.</span><span class="sxs-lookup"><span data-stu-id="259dc-121">**-destinationtable** - name of the table being compared.</span></span>  
  
    -   <span data-ttu-id="259dc-122">**-sourceschema** — владелец схемы исходной таблицы, если не используется схема по умолчанию (необязательно).</span><span class="sxs-lookup"><span data-stu-id="259dc-122">(Optional) **-destinationschema** - schema owner of the destination table, if not the default schema.</span></span>  
  
    -   <span data-ttu-id="259dc-123">**-destinationuser** и **-destinationpassword** , если для подключения к подписчику используется проверка подлинности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (необязательно).</span><span class="sxs-lookup"><span data-stu-id="259dc-123">(Optional) **-destinationuser** and **-destinationpassword** when using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication to connect to the Subscriber.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="259dc-124">По возможности используйте аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="259dc-124">When possible, use Windows Authentication.</span></span> <span data-ttu-id="259dc-125">При необходимости использования проверки подлинности [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] предлагайте пользователям вводить учетные данные во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="259dc-125">If you must use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="259dc-126">В случае необходимости хранения учетных данных в файле скрипта этот файл следует защищать во избежание несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="259dc-126">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
    -   <span data-ttu-id="259dc-127">Используйте **-c** для сравнения по столбцам (необязательно).</span><span class="sxs-lookup"><span data-stu-id="259dc-127">(Optional) Use **-c** to do a column-level comparison.</span></span>  
  
    -   <span data-ttu-id="259dc-128">Используйте **-q** для быстрого сравнения количества строк и схемы (необязательно).</span><span class="sxs-lookup"><span data-stu-id="259dc-128">(Optional) Use **-q** to do a fast, row count- and schema-only comparison.</span></span>  
  
    -   <span data-ttu-id="259dc-129">Укажите имя файла и путь для **-o** для записи результатов в файл (необязательно).</span><span class="sxs-lookup"><span data-stu-id="259dc-129">(Optional) Specify a file name and path for **-o** to output the results to a file.</span></span>  
  
    -   <span data-ttu-id="259dc-130">Укажите таблицу в базе данных подписки, куда должны вставляться результаты для **-et**(необязательно).</span><span class="sxs-lookup"><span data-stu-id="259dc-130">(Optional) Specify a table in the subscription database into which to insert results for **-et**.</span></span> <span data-ttu-id="259dc-131">Если таблица уже существует, задайте **-dt** , чтобы сначала удалить таблицу.</span><span class="sxs-lookup"><span data-stu-id="259dc-131">If the table already exists, specify **-dt** to first drop the table.</span></span>  
  
    -   <span data-ttu-id="259dc-132">Используйте **-f** , чтобы создать файл [!INCLUDE[tsql](../../../includes/tsql-md.md)] для исправления данных на подписчике и приведения их в соответствие с данными на издателе (необязательно).</span><span class="sxs-lookup"><span data-stu-id="259dc-132">(Optional) Use **-f** to generate a [!INCLUDE[tsql](../../../includes/tsql-md.md)] file to fix data at the Subscriber so that it matches data at the Publisher.</span></span> <span data-ttu-id="259dc-133">Используйте **-df** для определения количества инструкций [!INCLUDE[tsql](../../../includes/tsql-md.md)] в каждом файле.</span><span class="sxs-lookup"><span data-stu-id="259dc-133">Use **-df** to specify the number of [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements in each file.</span></span>  
  
    -   <span data-ttu-id="259dc-134">Используйте **-rc** и **-ri** для определения количества попыток повтора операции и интервала повторных попыток (необязательно).</span><span class="sxs-lookup"><span data-stu-id="259dc-134">(Optional) Use **-rc** and **-ri** to specify the number of times to retry an operation and the retry interval.</span></span>  
  
    -   <span data-ttu-id="259dc-135">Используйте **-strict** для строгого сравнения схем исходной и целевой таблиц (необязательно).</span><span class="sxs-lookup"><span data-stu-id="259dc-135">(Optional) Use **-strict** to enforce strict schema comparison between source and destination tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="259dc-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="259dc-136">See Also</span></span>  
 [<span data-ttu-id="259dc-137">Проверка данных на подписчике</span><span class="sxs-lookup"><span data-stu-id="259dc-137">Validate Data at the Subscriber</span></span>](../validate-data-at-the-subscriber.md)  
  
  

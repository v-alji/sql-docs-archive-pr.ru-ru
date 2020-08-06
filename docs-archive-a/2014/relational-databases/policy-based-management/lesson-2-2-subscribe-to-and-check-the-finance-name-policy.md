---
title: Подписка на политику имен базы данных Finance и проверка обновлений | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 126b4c4c-2a1c-4701-a0ad-8de23fbd7306
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2bfe6f463d03fe8b95f000dc6f34dc0718a7729f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655105"
---
# <a name="subscribe-to-and-check-the-finance-name-policy"></a><span data-ttu-id="9ceea-102">Подписка на политику имен финансов и ее проверка</span><span class="sxs-lookup"><span data-stu-id="9ceea-102">Subscribe to and Check the Finance Name Policy</span></span>
  <span data-ttu-id="9ceea-103">В этой задаче будет произведена настройка по подписке базы данных Finance к категории политики финансов.</span><span class="sxs-lookup"><span data-stu-id="9ceea-103">In this task, you will configure the Finance database to subscribe to the Finance policy category.</span></span> <span data-ttu-id="9ceea-104">Затем будет протестирована политика имен финансов.</span><span class="sxs-lookup"><span data-stu-id="9ceea-104">Then, you will test the Finance Name policy.</span></span>  
  
### <a name="to-subscribe-to-the-finance-policy-category"></a><span data-ttu-id="9ceea-105">Подписка на категорию политик «Finance»</span><span class="sxs-lookup"><span data-stu-id="9ceea-105">To subscribe to the Finance policy category</span></span>  
  
1.  <span data-ttu-id="9ceea-106">В обозревателе объектов разверните узел **базы данных**, щелкните правой кнопкой мыши `Finance` , наведите указатель на пункт **политики**и выберите пункт **категории**.</span><span class="sxs-lookup"><span data-stu-id="9ceea-106">In Object Explorer, expand **Databases**, right-click `Finance`, point to **Policies**, and then click **Categories**.</span></span>  
  
2.  <span data-ttu-id="9ceea-107">Установите флажок **подписки** для `Finance` категории.</span><span class="sxs-lookup"><span data-stu-id="9ceea-107">Select the **Subscribed** checkbox for the `Finance` category.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-test-the-enforcement-of-the-finance-name-policy"></a><span data-ttu-id="9ceea-108">Тестирование принудительного применения политики имен финансов</span><span class="sxs-lookup"><span data-stu-id="9ceea-108">To test the enforcement of the Finance Name policy</span></span>  
  
1.  <span data-ttu-id="9ceea-109">В среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]откройте окно запроса.</span><span class="sxs-lookup"><span data-stu-id="9ceea-109">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a query window.</span></span> <span data-ttu-id="9ceea-110">Выполните приведенные ниже инструкции, которые попытаются создать таблицу, нарушающую политику **Имена финансов** .</span><span class="sxs-lookup"><span data-stu-id="9ceea-110">Execute the following statements that try to create a table that violates the **Finance Name** policy.</span></span> <span data-ttu-id="9ceea-111">Таблица нарушает политику, так как ее имя не начинается с букв **fintbl**.</span><span class="sxs-lookup"><span data-stu-id="9ceea-111">The table violates the policy because the table name does not begin with the letters **fintbl**.</span></span>  
  
    ```  
    USE Finance ;  
    GO  
    CREATE TABLE NewTable  
    (Col1 int) ;  
    GO  
  
    ```  
  
     <span data-ttu-id="9ceea-112">Обратите внимание, что политика предотвращает создание таблицы и возвращает информационное сообщение, содержащее имя политики.</span><span class="sxs-lookup"><span data-stu-id="9ceea-112">Notice that the policy prevents the table from being created and returns an informational message that provides the policy name.</span></span>  
  
2.  <span data-ttu-id="9ceea-113">Для предоставления достоверного имени измените код, как указано ниже, и снова запустите инструкцию.</span><span class="sxs-lookup"><span data-stu-id="9ceea-113">To provide a valid name, modify the code as follows and run the statement again.</span></span>  
  
    ```  
    USE Finance ;  
    GO  
    CREATE TABLE fintblNewTable  
    (Col1 int) ;  
    GO  
  
    ```  
  
     <span data-ttu-id="9ceea-114">В это время создается таблица.</span><span class="sxs-lookup"><span data-stu-id="9ceea-114">This time, the table is created.</span></span>  
  
### <a name="to-apply-the-policy-to-the-whole-server"></a><span data-ttu-id="9ceea-115">Применение политики ко всему серверу</span><span class="sxs-lookup"><span data-stu-id="9ceea-115">To apply the policy to the whole server</span></span>  
  
1.  <span data-ttu-id="9ceea-116">В данный момент на категорию политики финансов подписана только база данных Finance.</span><span class="sxs-lookup"><span data-stu-id="9ceea-116">Currently, only the Finance database subscribes to the Finance policy category.</span></span> <span data-ttu-id="9ceea-117">В большинстве случаев легче применить категорию политики ко всему серверу.</span><span class="sxs-lookup"><span data-stu-id="9ceea-117">In many cases, it is easier to apply the policy category to the whole server.</span></span> <span data-ttu-id="9ceea-118">В обозревателе объектов разверните узел **Управление**, щелкните правой кнопкой мыши узел **Управление политиками**и выберите пункт **Управление категориями**.</span><span class="sxs-lookup"><span data-stu-id="9ceea-118">In Object Explorer, expand **Management**, right-click **Policy Management**, and then click **Manage Categories**.</span></span>  
  
2.  <span data-ttu-id="9ceea-119">Найдите категорию Finance в диалоговом окне **Управление категориями политик** и установите флажок **Сделать подписки базы данных обязательными** для категории Finance.</span><span class="sxs-lookup"><span data-stu-id="9ceea-119">In the **Manage Policy Categories** dialog box, locate the Finance category, and select the **Mandate Database Subscriptions** checkbox for the Finance category.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)] <span data-ttu-id="9ceea-120">Теперь категория Finance применяется ко всем базам данных, но созданное условие ограничивает политику имен финансов для базы данных Finance.</span><span class="sxs-lookup"><span data-stu-id="9ceea-120">Now the Finance category applies to all databases, but the condition that you have created restricts the Finance Name policy to the Finance database.</span></span> <span data-ttu-id="9ceea-121">Это показывает то, как используются сложные сочетания условий для целевых политик для их правильного применения к нескольким серверам.</span><span class="sxs-lookup"><span data-stu-id="9ceea-121">This shows how you can use complex combinations of conditions to target policies in ways that will apply correctly on many servers.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="9ceea-122">Итоги</span><span class="sxs-lookup"><span data-stu-id="9ceea-122">Summary</span></span>  
 <span data-ttu-id="9ceea-123">В этом учебнике показано создание условий управления на основе политик, политик и групп политик, а также применение фильтров и проверка соответствия целей управления на основе политик.</span><span class="sxs-lookup"><span data-stu-id="9ceea-123">This tutorial has shown you how to create Policy-Based Management conditions, policies and policy groups, and how to apply filters and check the compliance of Policy-Based Management targets.</span></span>  
  
## <a name="next"></a><span data-ttu-id="9ceea-124">Следующая</span><span class="sxs-lookup"><span data-stu-id="9ceea-124">Next</span></span>  
 <span data-ttu-id="9ceea-125">Данный учебник завершен.</span><span class="sxs-lookup"><span data-stu-id="9ceea-125">This tutorial is finished.</span></span> <span data-ttu-id="9ceea-126">Чтобы вернуться к началу, щелкните ссылку [Учебник. Администрирование серверов с помощью управления на основе политик](tutorial-administering-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="9ceea-126">To return to the start, click [Tutorial: Administering Servers by Using Policy-Based Management](tutorial-administering-servers-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="9ceea-127">Список учебников см. в [руководствах по SQL Server 2014](../../tutorials/tutorials-for-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="9ceea-127">For a list of tutorials, see [Tutorials for SQL Server 2014](../../tutorials/tutorials-for-sql-server-2014.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ceea-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="9ceea-128">See Also</span></span>  
 [<span data-ttu-id="9ceea-129">Администрирование серверов с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="9ceea-129">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  

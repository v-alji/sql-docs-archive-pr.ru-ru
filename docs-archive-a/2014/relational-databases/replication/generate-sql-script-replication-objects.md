---
title: Диалоговое окно "Формирование скрипта SQL" (объекты репликации) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.generatesqlscript.f1
helpviewer_keywords:
- Generate SQL Script dialog box
ms.assetid: b7ccc34e-1c22-44b8-8eb5-f6423af3164e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 31a4b318eb3a4c0e5d9f79f43efdcf97c42957f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655601"
---
# <a name="generate-sql-script-replication-objects"></a><span data-ttu-id="a4b8c-102">Диалоговое окно «Формирование скрипта SQL» (объекты репликации)</span><span class="sxs-lookup"><span data-stu-id="a4b8c-102">Generate SQL Script (Replication Objects)</span></span>
  <span data-ttu-id="a4b8c-103">Скрипт репликации содержит системные хранимые процедуры [!INCLUDE[tsql](../../includes/tsql-md.md)] , необходимые для реализации используемых в скрипте компонентов репликации, например публикации или подписки.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-103">A replication script contains the [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures necessary to implement the replication components scripted, such as a publication or subscription.</span></span> <span data-ttu-id="a4b8c-104">Все компоненты репликации в топологии должны использоваться в скриптах как часть плана аварийного восстановления, а скрипты могут также использоваться для автоматизации повторяющихся задач.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-104">All replication components in a topology should be scripted as part of a disaster recovery plan, and scripts can also be used to automate repetitive tasks.</span></span> <span data-ttu-id="a4b8c-105">Для использования в сценарии объектов репликации она предоставляет два диалоговых окна.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-105">Replication offers two dialog boxes for scripting replication objects:</span></span>  
  
-   <span data-ttu-id="a4b8c-106">**Формирование скрипта SQL**, доступ к которому осуществляется из контекстного меню папки **Репликация** и всех ее вложенных папок в среде [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4b8c-106">**Generate SQL Script**, which is available from the context menu of the **Replication** folder and all subfolders in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="a4b8c-107">С помощью этого диалогового окна в скрипт можно помещать все объекты репликации экземпляра [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4b8c-107">This dialog box allows you to script all replication objects on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="a4b8c-108">**Формирование скрипта SQL \<ObjectName>** , доступ к которому осуществляется из контекстного меню публикаций и подписок.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-108">**Generate SQL Script \<ObjectName>**, which is available from the context menu for publications and subscriptions.</span></span> <span data-ttu-id="a4b8c-109">С помощью этого диалогового окна в скрипт можно помещать отдельные объекты.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-109">This dialog box allows you to script individual objects.</span></span>  
  
 <span data-ttu-id="a4b8c-110">Эти диалоговые окна позволяют формировать скрипты с объектами на одном экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], не осуществляют соединения с другими экземплярами для использования в скриптах связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-110">These dialog boxes script objects on a single instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; they do not connect to other instances to script related objects.</span></span>  
  
## <a name="generate-sql-script-options"></a><span data-ttu-id="a4b8c-111">Параметры диалогового окна «Формирование скрипта SQL»</span><span class="sxs-lookup"><span data-stu-id="a4b8c-111">Generate SQL Script Options</span></span>  
 <span data-ttu-id="a4b8c-112">**Свойства распространителя**</span><span class="sxs-lookup"><span data-stu-id="a4b8c-112">**Distributor properties**</span></span>  
 <span data-ttu-id="a4b8c-113">Выберите для написания хранимых процедур, осуществляющих включение или отключение распространителя, добавление или удаление издателей, связанных с распространителем, создание или удаление базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-113">Select to script stored procedures to: enable or disable the Distributor; add or drop Publishers associated with the Distributor; and create or drop the distribution database.</span></span>  
  
 <span data-ttu-id="a4b8c-114">**Публикации в следующих источниках данных**</span><span class="sxs-lookup"><span data-stu-id="a4b8c-114">**Publications in the following data sources**</span></span>  
 <span data-ttu-id="a4b8c-115">Выберите для написания хранимых процедур, осуществляющих включение или отключение публикаций, создание или удаление публикаций, статей, принудительных подписок и заданий репликации.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-115">Select to script stored procedures to: enable or disable publishing; and create or drop publications, articles, push subscriptions, and replication jobs.</span></span>  
  
 <span data-ttu-id="a4b8c-116">**Подписки в следующих источниках данных**</span><span class="sxs-lookup"><span data-stu-id="a4b8c-116">**Subscriptions in the following data sources**</span></span>  
 <span data-ttu-id="a4b8c-117">Выберите этот пункт для написания хранимых процедур, осуществляющих создание или удаление подписок по запросу и заданий репликации.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-117">Select to script stored procedures to create or drop pull subscriptions and replication jobs.</span></span>  
  
 <span data-ttu-id="a4b8c-118">**Для создания или включения компонентов** и **Для удаления или отключения компонентов**</span><span class="sxs-lookup"><span data-stu-id="a4b8c-118">**To create or enable the components** and **To drop or disable the components**</span></span>  
 <span data-ttu-id="a4b8c-119">Указывает, должен ли скрипт включать команды для создания или удаления объектов репликации.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-119">Specify whether the script should include commands for creating or dropping a replication object.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="a4b8c-120">рекомендует использовать это диалоговое окно для создания набора скриптов, осуществляющих включение и отключение компонентов.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-120">recommends that you use the dialog box to create a set of scripts for enabling and disabling components.</span></span>  
  
 <span data-ttu-id="a4b8c-121">**Задания репликации**</span><span class="sxs-lookup"><span data-stu-id="a4b8c-121">**Replication jobs**</span></span>  
 <span data-ttu-id="a4b8c-122">Выберите этот пункт для создания скриптов с заданиями репликации в дополнение к вызовам хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-122">Select to script replication jobs in addition to stored procedure calls.</span></span> <span data-ttu-id="a4b8c-123">Этот параметр доступен только в случае, если сценарий создается на распространителе.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-123">This option is available only when scripting from a Distributor.</span></span>  
  
 <span data-ttu-id="a4b8c-124">При выполнении хранимых процедур репликации создаются необходимые задания, поэтому нет необходимости выбирать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-124">Replication stored procedures create the necessary jobs when they are executed, so it is not required to select this option.</span></span> <span data-ttu-id="a4b8c-125">Однако может быть полезным записывать создаваемые задания в случаях, если возникает необходимость повторного создания отдельных заданий.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-125">However, it can be useful to have a record of the jobs created in case an individual job must be recreated.</span></span>  
  
## <a name="generate-sql-script-objectname-options"></a><span data-ttu-id="a4b8c-126">Параметры диалогового окна "Формирование скрипта SQL \<ObjectName>"</span><span class="sxs-lookup"><span data-stu-id="a4b8c-126">Generate SQL Script \<ObjectName> Options</span></span>  
 <span data-ttu-id="a4b8c-127">**Для создания или включения компонентов** и **Для удаления или отключения компонентов**</span><span class="sxs-lookup"><span data-stu-id="a4b8c-127">**To create or enable the components** and **To drop or disable the components**</span></span>  
 <span data-ttu-id="a4b8c-128">Указывает, должен ли скрипт включать команды для создания или удаления объектов репликации.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-128">Specify whether the script should include commands for creating or dropping a replication object.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="a4b8c-129">рекомендует использовать это диалоговое окно для создания набора скриптов, осуществляющих включение и отключение компонентов.</span><span class="sxs-lookup"><span data-stu-id="a4b8c-129">recommends that you use the dialog box, creating a set of scripts for enabling and disabling components.</span></span>  
  
 <span data-ttu-id="a4b8c-130">**Задания репликации**</span><span class="sxs-lookup"><span data-stu-id="a4b8c-130">**Replication jobs**</span></span>  
 <span data-ttu-id="a4b8c-131">Этот параметр доступен только из диалогового окна **Формирование скрипта SQL** .</span><span class="sxs-lookup"><span data-stu-id="a4b8c-131">This option is available only from the **Generate SQL Script** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4b8c-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="a4b8c-132">See Also</span></span>  
 [<span data-ttu-id="a4b8c-133">Создание скриптов репликации</span><span class="sxs-lookup"><span data-stu-id="a4b8c-133">Scripting Replication</span></span>](scripting-replication.md)  
  
  

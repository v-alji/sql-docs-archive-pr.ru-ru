---
title: Свойства базы данных (страница "Отслеживание изменений") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.changetracking.f1
ms.assetid: 9b929640-bc62-449b-9b06-b5a77b8cf372
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4107f81ef4cdf19df60d4a70d8e79007f2c9270c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734137"
---
# <a name="database-properties-changetracking-page"></a><span data-ttu-id="619b4-102">Свойства базы данных (страница «Отслеживание изменений»)</span><span class="sxs-lookup"><span data-stu-id="619b4-102">Database Properties (ChangeTracking Page)</span></span>
  <span data-ttu-id="619b4-103">Эта страница позволяет просмотреть или изменить параметры отслеживания изменений для выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="619b4-103">Use this page to view or modify change tracking settings for the selected database.</span></span> <span data-ttu-id="619b4-104">Дополнительные сведения о параметрах, доступных на этой странице, см. в разделе [Включение и отключение отслеживания изменений (SQL Server)](../track-changes/enable-and-disable-change-tracking-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="619b4-104">For more information about the options available on this page, see [Enable and Disable Change Tracking &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="619b4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="619b4-105">Options</span></span>  
 <span data-ttu-id="619b4-106">**Отслеживание изменений**</span><span class="sxs-lookup"><span data-stu-id="619b4-106">**Change Tracking**</span></span>  
 <span data-ttu-id="619b4-107">Используйте этот параметр, чтобы включить или отключить отслеживание изменений для базы данных.</span><span class="sxs-lookup"><span data-stu-id="619b4-107">Use to enable or disable change tracking for the database.</span></span>  
  
 <span data-ttu-id="619b4-108">Чтобы включить отслеживание изменений, необходимо иметь разрешение на изменение базы данных.</span><span class="sxs-lookup"><span data-stu-id="619b4-108">To enable change tracking, you must have permission to modify the database.</span></span>  
  
 <span data-ttu-id="619b4-109">Значение **True** задает параметр базы данных, позволяющий включить отслеживание изменений для отдельных таблиц.</span><span class="sxs-lookup"><span data-stu-id="619b4-109">Setting the value to **True** sets a database option that allows change tracking to be enabled on individual tables.</span></span>  
  
 <span data-ttu-id="619b4-110">Можно также настроить отслеживание изменений с помощью инструкции [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="619b4-110">You can also configure change tracking by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
 <span data-ttu-id="619b4-111">**Срок хранения**</span><span class="sxs-lookup"><span data-stu-id="619b4-111">**Retention Period**</span></span>  
 <span data-ttu-id="619b4-112">Указывает минимальный срок хранения данных отслеживания изменений в базе данных.</span><span class="sxs-lookup"><span data-stu-id="619b4-112">Specifies the minimum period for keeping change track information in the database.</span></span> <span data-ttu-id="619b4-113">Данные удаляются только в случае, если параметр **Автоматическая очистка**имеет значение **True**.</span><span class="sxs-lookup"><span data-stu-id="619b4-113">Data is removed only if the **Auto Clean-Up**value is **True**.</span></span>  
  
 <span data-ttu-id="619b4-114">Значение по умолчанию — 2.</span><span class="sxs-lookup"><span data-stu-id="619b4-114">The default value is 2.</span></span>  
  
 <span data-ttu-id="619b4-115">**Единицы измерения срока хранения**</span><span class="sxs-lookup"><span data-stu-id="619b4-115">**Retention Period Units**</span></span>  
 <span data-ttu-id="619b4-116">Указывает единицы изменения для значения параметра «Срок хранения».</span><span class="sxs-lookup"><span data-stu-id="619b4-116">Specifies the units for the Retention Period value.</span></span> <span data-ttu-id="619b4-117">Может быть выбрано одно из следующих значений: **Дней**, **Часов**или **Минут**.</span><span class="sxs-lookup"><span data-stu-id="619b4-117">You can select **Days**, **Hours**, or **Minutes**.</span></span> <span data-ttu-id="619b4-118">Значение по умолчанию — **Дней**.</span><span class="sxs-lookup"><span data-stu-id="619b4-118">The default value is **Days**.</span></span>  
  
 <span data-ttu-id="619b4-119">Минимальный срок хранения составляет 1 минуту.</span><span class="sxs-lookup"><span data-stu-id="619b4-119">The minimum retention period is 1 minute.</span></span> <span data-ttu-id="619b4-120">Максимальный срок хранения не предусмотрен.</span><span class="sxs-lookup"><span data-stu-id="619b4-120">There is no maximum retention period.</span></span>  
  
 <span data-ttu-id="619b4-121">**Автоматическая очистка**</span><span class="sxs-lookup"><span data-stu-id="619b4-121">**Auto Clean-Up**</span></span>  
 <span data-ttu-id="619b4-122">Указывает, производится ли автоматическое удаление данных отслеживания изменений по истечении заданного срока хранения.</span><span class="sxs-lookup"><span data-stu-id="619b4-122">Indicates whether change tracking information is automatically removed after the specified retention period.</span></span>  
  
 <span data-ttu-id="619b4-123">Если параметр **Автоматическая очистка** включен, то любой ранее заданный срок хранения сбрасывается в значение по умолчанию — 2 дня.</span><span class="sxs-lookup"><span data-stu-id="619b4-123">Enabling **Auto Clean-Up** resets any previous custom retention period to the default retention period of 2 days.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="619b4-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="619b4-124">See Also</span></span>  
 <span data-ttu-id="619b4-125">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="619b4-125">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="619b4-126">CREATE DATABASE (SQL Server Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="619b4-126">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  

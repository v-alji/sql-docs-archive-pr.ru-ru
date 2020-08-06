---
title: Значения функции HOST_NAME Values | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.hostnamevalue.f1
ms.assetid: 21548f08-2910-4a55-baac-b911ba9afaf1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 67d01df05c8d56fd435eb0ee1b42ba2da6a312ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655598"
---
# <a name="host_name-values"></a><span data-ttu-id="f79dc-102">Значения функции HOST_NAME</span><span class="sxs-lookup"><span data-stu-id="f79dc-102">HOST_NAME Values</span></span>
  <span data-ttu-id="f79dc-103">Публикации слиянием с параметризованными фильтрами используют функции SUSER_SNAME() или HOST_NAME() для фильтрации данных.</span><span class="sxs-lookup"><span data-stu-id="f79dc-103">Merge publications with parameterized filters use the SUSER_SNAME() function and/or the HOST_NAME() function to filter data.</span></span> <span data-ttu-id="f79dc-104">Функция задается в мастере создания публикаций или диалоговом окне **Свойства публикации** .</span><span class="sxs-lookup"><span data-stu-id="f79dc-104">The function is specified in the New Publication Wizard or the **Publication Properties** dialog box.</span></span>  
  
 <span data-ttu-id="f79dc-105">По умолчанию функция HOST_NAME() возвращает имя компьютера, подключающегося к издателю.</span><span class="sxs-lookup"><span data-stu-id="f79dc-105">By default, the HOST_NAME() function returns the name of the computer connecting to the Publisher.</span></span> <span data-ttu-id="f79dc-106">При использовании параметризованных фильтров принято заменять это значение, указав новое значение на данной странице мастера.</span><span class="sxs-lookup"><span data-stu-id="f79dc-106">When using parameterized filters, it is common to override this value by supplying a value on this page of the wizard.</span></span> <span data-ttu-id="f79dc-107">В этом случае функция HOST_NAME() будет возвращать указанное значение вместо имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="f79dc-107">The HOST_NAME() function then returns the value you specify rather than the name of the computer.</span></span> <span data-ttu-id="f79dc-108">Дополнительные сведения см. в главе "Переопределение значения функции HOST_NAME()" в статье [Параметризованные фильтры строк](merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="f79dc-108">For more information, see the "Overriding the HOST_NAME() Value" section of [Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f79dc-109">Если переопределить функцию HOST_NAME(), все вызовы этой функции будут возвращать указанное значение.</span><span class="sxs-lookup"><span data-stu-id="f79dc-109">If you override HOST_NAME(), all calls to the HOST_NAME() function will return the value you specify.</span></span> <span data-ttu-id="f79dc-110">Убедитесь, что другие приложения не зависят от того, возвращает ли функция HOST_NAME() имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="f79dc-110">Ensure that other applications are not depending on HOST_NAME() returning the computer name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f79dc-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="f79dc-111">Options</span></span>  
 <span data-ttu-id="f79dc-112">**Свойства подписки**</span><span class="sxs-lookup"><span data-stu-id="f79dc-112">**Subscription properties**</span></span>  
 <span data-ttu-id="f79dc-113">Введите значения для каждого подписчика в столбце **Значение HOST_NAME** или оставьте значение по умолчанию, которое соответствует имени компьютера подписчика.</span><span class="sxs-lookup"><span data-stu-id="f79dc-113">Enter a value for each Subscriber in the **HOST_NAME Value** column or accept the default, which is the name of the Subscriber computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f79dc-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="f79dc-114">See Also</span></span>  
 <span data-ttu-id="f79dc-115">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="f79dc-115">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="f79dc-116">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="f79dc-116">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="f79dc-117">[Просмотр и изменение свойств подписки по запросу](view-and-modify-pull-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f79dc-117">[View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md) </span></span>  
 <span data-ttu-id="f79dc-118">[Просмотр и изменение свойств принудительной подписки](view-and-modify-push-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f79dc-118">[View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) </span></span>  
 <span data-ttu-id="f79dc-119">[HOST_NAME (Transact-SQL)](/sql/t-sql/functions/host-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f79dc-119">[HOST_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/host-name-transact-sql) </span></span>  
 [<span data-ttu-id="f79dc-120">Подписка на публикации</span><span class="sxs-lookup"><span data-stu-id="f79dc-120">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  

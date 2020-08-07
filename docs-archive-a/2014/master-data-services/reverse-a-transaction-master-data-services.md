---
title: Отмена транзакции (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Master Data Services], reversing
ms.assetid: 6f7c3f07-0f64-4283-8c9c-93facd00a046
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fb5b1b0932b65b1d6f8fe7b1bc842836e21aaca6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730770"
---
# <a name="reverse-a-transaction-master-data-services"></a><span data-ttu-id="34ee4-102">Отмена транзакции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="34ee4-102">Reverse a Transaction (Master Data Services)</span></span>
  <span data-ttu-id="34ee4-103">В службах [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]администратор может обратить транзакцию, когда необходимо отменить действие.</span><span class="sxs-lookup"><span data-stu-id="34ee4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], administrators can reverse a transaction when an action needs to be undone.</span></span> <span data-ttu-id="34ee4-104">Примеры транзакций: изменения значений атрибутов, перемещение иерархий, удаление элементов.</span><span class="sxs-lookup"><span data-stu-id="34ee4-104">Examples of transactions are attribute value changes, hierarchy moves, or member deletions.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="34ee4-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="34ee4-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="34ee4-106">необходимо иметь разрешение на доступ к функциональной области **Управление версиями** ;</span><span class="sxs-lookup"><span data-stu-id="34ee4-106">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="34ee4-107">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="34ee4-107">You must be a model administrator.</span></span> <span data-ttu-id="34ee4-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="34ee4-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-reverse-a-transaction"></a><span data-ttu-id="34ee4-109">Отмена транзакции</span><span class="sxs-lookup"><span data-stu-id="34ee4-109">To reverse a transaction</span></span>  
  
1.  <span data-ttu-id="34ee4-110">На домашней странице [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] нажмите **Управление версиями**.</span><span class="sxs-lookup"><span data-stu-id="34ee4-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="34ee4-111">В строке меню выберите пункт **Транзакции**.</span><span class="sxs-lookup"><span data-stu-id="34ee4-111">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="34ee4-112">На странице **Транзакции** выберите модель в списке **Модель** .</span><span class="sxs-lookup"><span data-stu-id="34ee4-112">On the **Transactions** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="34ee4-113">Выберите версию из списка **Версия** .</span><span class="sxs-lookup"><span data-stu-id="34ee4-113">From the **Version** list, select a version.</span></span>  
  
5.  <span data-ttu-id="34ee4-114">Щелкните в сетке строку транзакции, которую необходимо отменить.</span><span class="sxs-lookup"><span data-stu-id="34ee4-114">Click the row in the grid for the transaction you want to reverse.</span></span>  
  
6.  <span data-ttu-id="34ee4-115">Нажмите кнопку **Отменить транзакцию**.</span><span class="sxs-lookup"><span data-stu-id="34ee4-115">Click **Reverse Transaction**.</span></span>  
  
7.  <span data-ttu-id="34ee4-116">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="34ee4-116">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="34ee4-117">В сетку добавляется еще одна транзакция, соответствующая отмененной транзакции.</span><span class="sxs-lookup"><span data-stu-id="34ee4-117">Another transaction is added to the grid to record the reversed transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34ee4-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="34ee4-118">See Also</span></span>  
 <span data-ttu-id="34ee4-119">[Master Data Services &#40;транзакций&#41;](../../2014/master-data-services/transactions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="34ee4-119">[Transactions &#40;Master Data Services&#41;](../../2014/master-data-services/transactions-master-data-services.md) </span></span>  
 [<span data-ttu-id="34ee4-120">Повторная активация элемента или коллекции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="34ee4-120">Reactivate a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md)  
  
  

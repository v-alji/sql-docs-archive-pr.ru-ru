---
title: Добавление заметки для транзакции (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- annotations [Master Data Services], for transactions
ms.assetid: f5a6b2ca-56de-4e42-9da8-fba0ac3e8d92
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c384f4241d0ddcd78fd8942fe28da8c0b5b1e77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734234"
---
# <a name="annotate-a-transaction-master-data-services"></a><span data-ttu-id="aa23e-102">Добавление заметки для транзакции (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="aa23e-102">Annotate a Transaction (Master Data Services)</span></span>
  <span data-ttu-id="aa23e-103">Службы [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]позволяют добавить к транзакции заметку, если необходимо предоставление дополнительных сведений о транзакции для архивных целей.</span><span class="sxs-lookup"><span data-stu-id="aa23e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], annotate a transaction when you want to provide supporting details about the transaction for historical purposes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa23e-104">Заметки нельзя удалить.</span><span class="sxs-lookup"><span data-stu-id="aa23e-104">You cannot delete annotations.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aa23e-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="aa23e-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="aa23e-106">Для добавления заметок к созданным транзакциям необходимы права на доступ к функциональной области **Браузер** и как минимум разрешение **Обновление** на объект модели, к которому добавляется заметка.</span><span class="sxs-lookup"><span data-stu-id="aa23e-106">To annotate transactions that you created, you must have permission to access the **Explorer** functional area, and have a minimum of **Update** permission to the model object you want to annotate.</span></span>  
  
-   <span data-ttu-id="aa23e-107">Чтобы снабдить заметками транзакции всех пользователей, необходимо иметь разрешение на доступ к функциональной области **Управление версиями** и являться администратором модели.</span><span class="sxs-lookup"><span data-stu-id="aa23e-107">To annotate transactions for all users, you must have permission to access the **Version Management** functional area and be a model administrator.</span></span> <span data-ttu-id="aa23e-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="aa23e-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-annotate-a-transaction-in-explorer"></a><span data-ttu-id="aa23e-109">Добавление заметки к транзакции в браузере</span><span class="sxs-lookup"><span data-stu-id="aa23e-109">To annotate a transaction in Explorer</span></span>  
  
1.  <span data-ttu-id="aa23e-110">На домашней странице [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] выберите модель в списке **Модель** .</span><span class="sxs-lookup"><span data-stu-id="aa23e-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="aa23e-111">Выберите версию из списка **Версия** .</span><span class="sxs-lookup"><span data-stu-id="aa23e-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="aa23e-112">Нажмите кнопку **Браузер**.</span><span class="sxs-lookup"><span data-stu-id="aa23e-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="aa23e-113">На панели меню наведите указатель на пункт **Сущности** и выберите сущность, содержащую элемент с транзакцией, к которой необходимо добавить заметку.</span><span class="sxs-lookup"><span data-stu-id="aa23e-113">From the menu bar, point to **Entities** and click the entity that contains the member with a transaction you want to annotate.</span></span>  
  
5.  <span data-ttu-id="aa23e-114">На сетке щелкните строку элемента.</span><span class="sxs-lookup"><span data-stu-id="aa23e-114">In the grid, click the row of the member.</span></span>  
  
6.  <span data-ttu-id="aa23e-115">Нажмите кнопку **Просмотреть транзакции**.</span><span class="sxs-lookup"><span data-stu-id="aa23e-115">Click **View Transactions**.</span></span>  
  
7.  <span data-ttu-id="aa23e-116">В диалоговом окне **Просмотр транзакций** выберите транзакцию, к которой необходимо добавить заметку.</span><span class="sxs-lookup"><span data-stu-id="aa23e-116">In the **View Transactions** dialog box, click the transaction you want to annotate.</span></span>  
  
8.  <span data-ttu-id="aa23e-117">Введите заметку в поле в нижней части диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="aa23e-117">In the box at the bottom of the dialog box, type your annotation.</span></span>  
  
9. <span data-ttu-id="aa23e-118">Нажмите кнопку **Добавить заметку**.</span><span class="sxs-lookup"><span data-stu-id="aa23e-118">Click **Add Annotation**.</span></span> <span data-ttu-id="aa23e-119">Заметка отображается на панели **Заметки** .</span><span class="sxs-lookup"><span data-stu-id="aa23e-119">The annotation is displayed in the **Annotations** pane.</span></span>  
  
### <a name="to-annotate-a-transaction-in-version-management-administrators-only"></a><span data-ttu-id="aa23e-120">Добавление заметки к транзакции в управлении версиями (только администраторы)</span><span class="sxs-lookup"><span data-stu-id="aa23e-120">To annotate a transaction in Version Management (administrators only)</span></span>  
  
1.  <span data-ttu-id="aa23e-121">На домашней странице [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] нажмите **Управление версиями**.</span><span class="sxs-lookup"><span data-stu-id="aa23e-121">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="aa23e-122">В строке меню выберите пункт **Транзакции**.</span><span class="sxs-lookup"><span data-stu-id="aa23e-122">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="aa23e-123">На панели **Транзакции** щелкните строку в сетке, соответствующую транзакции, которую необходимо снабдить заметкой.</span><span class="sxs-lookup"><span data-stu-id="aa23e-123">In the **Transactions** pane, click the row in the grid for the transaction you want to annotate.</span></span>  
  
4.  <span data-ttu-id="aa23e-124">На панели **Заметки транзакции** в поле **Заметка** введите заметку.</span><span class="sxs-lookup"><span data-stu-id="aa23e-124">In the **Transaction Annotations** pane, in the **Annotation** box, type your annotation.</span></span>  
  
5.  <span data-ttu-id="aa23e-125">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="aa23e-125">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa23e-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="aa23e-126">See Also</span></span>  
 <span data-ttu-id="aa23e-127">[Заметки &#40;Master Data Services&#41;](../../2014/master-data-services/annotations-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="aa23e-127">[Annotations &#40;Master Data Services&#41;](../../2014/master-data-services/annotations-master-data-services.md) </span></span>  
 [<span data-ttu-id="aa23e-128">Транзакции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="aa23e-128">Transactions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/transactions-master-data-services.md)  
  
  

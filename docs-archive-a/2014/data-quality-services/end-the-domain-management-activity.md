---
title: Завершение действия по управлению доменами | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: ab6505ad-3090-453b-bb01-58435e7fa7c0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c776674a369bfae8c7da6fa0deabfbd932029570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732045"
---
# <a name="end-the-domain-management-activity"></a><span data-ttu-id="93707-102">Завершение операции по управлению доменами</span><span class="sxs-lookup"><span data-stu-id="93707-102">End the Domain Management Activity</span></span>
  <span data-ttu-id="93707-103">В этом разделе описывается завершение, закрытие и отмена операции управления доменами в службах [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="93707-103">This topic describes how to complete, close, or cancel the domain management activity in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="93707-104">Управление доменами выполняется не в мастере, поэтому описанные ниже элементы управления можно использовать на любых страницах в категории управления доменами.</span><span class="sxs-lookup"><span data-stu-id="93707-104">Domain management is not performed by a wizard, so the controls described below can used from any of the pages of the domain management activity.</span></span>  
  
## <a name="end-domain-management"></a><span data-ttu-id="93707-105">Окончание управления доменами</span><span class="sxs-lookup"><span data-stu-id="93707-105">End Domain Management</span></span>  
 <span data-ttu-id="93707-106">**Готово**</span><span class="sxs-lookup"><span data-stu-id="93707-106">**Finish**</span></span>  
 <span data-ttu-id="93707-107">Щелкните, чтобы завершить управление доменами</span><span class="sxs-lookup"><span data-stu-id="93707-107">Click to complete domain management.</span></span> <span data-ttu-id="93707-108">Открывается всплывающее окно, позволяющее выбрать одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="93707-108">A popup will be displayed enabling you to do the following:</span></span>  
  
-   <span data-ttu-id="93707-109">**Да — опубликовать базу знаний и выйти**: база знаний будет опубликована и доступна для использования текущим пользователем или другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="93707-109">**Yes - Publish the knowledge base and exit**: The knowledge base will be published for the current user or others to use.</span></span> <span data-ttu-id="93707-110">База знаний не будет заблокирована, ее состояние (в таблице баз знаний) будет пустым. Будут доступны как операция управления доменами, так и операция обнаружения набора знаний.</span><span class="sxs-lookup"><span data-stu-id="93707-110">The knowledge base will not be locked, the state of the knowledge base (in the knowledge base table) will be set to empty, and both the Domain Management and Knowledge Discovery activities will be available.</span></span> <span data-ttu-id="93707-111">Пользователь возвращается на экран открытия базы знаний.</span><span class="sxs-lookup"><span data-stu-id="93707-111">You will be returned to the Open Knowledge Base screen.</span></span>  
  
-   <span data-ttu-id="93707-112">**Нет — сохранить работу в базе знаний и выйти**: ваша работа будет сохранена, база знаний останется заблокированной, а состояние базы знаний будет установлено в "работает".</span><span class="sxs-lookup"><span data-stu-id="93707-112">**No - Save the work on the knowledge base and exit**: Your work will be saved, the knowledge base will remained locked, and the state of the knowledge base will be set to In work.</span></span> <span data-ttu-id="93707-113">Будут доступны как операция управления доменами, так и операция обнаружения знаний.</span><span class="sxs-lookup"><span data-stu-id="93707-113">Both the Domain Management and Knowledge Discovery activities will be available.</span></span> <span data-ttu-id="93707-114">Выполняется возврат на домашнюю страницу.</span><span class="sxs-lookup"><span data-stu-id="93707-114">You will be returned to the home page.</span></span>  
  
-   <span data-ttu-id="93707-115">**Отмена — Оставайтесь на текущем экране**: всплывающее окно будет закрыто, и вы вернетесь на экран Управление доменами.</span><span class="sxs-lookup"><span data-stu-id="93707-115">**Cancel - Stay on the current screen**: The popup will be closed and you will be returned to the Domain Management screen.</span></span>  
  
 <span data-ttu-id="93707-116">**Отмена**</span><span class="sxs-lookup"><span data-stu-id="93707-116">**Cancel**</span></span>  
 <span data-ttu-id="93707-117">Щелкните, чтобы прекратить операции управления доменами, отменить результаты работы и вернуться на домашнюю страницу служб DQS.</span><span class="sxs-lookup"><span data-stu-id="93707-117">Click to terminate the Domain Management activity, losing your work, and return to the DQS home page.</span></span>  
  
 <span data-ttu-id="93707-118">**Закрыть**</span><span class="sxs-lookup"><span data-stu-id="93707-118">**Close**</span></span>  
 <span data-ttu-id="93707-119">Щелкните, чтобы сохранить результаты работы и вернуться на домашнюю страницу DQS.</span><span class="sxs-lookup"><span data-stu-id="93707-119">Click to save your work, and return to the DQS home page.</span></span> <span data-ttu-id="93707-120">База знаний будет заблокирована, и в таблице баз знаний в окне **Открытие базы знаний** будет отображено для этой базы знаний состояние **Управление доменами**.</span><span class="sxs-lookup"><span data-stu-id="93707-120">The knowledge base will be locked, and the state of the knowledge base in the knowledge base table in the **Open Knowledge Base** screen will be **Domain Management**.</span></span> <span data-ttu-id="93707-121">После нажатия кнопки **Закрыть**для выполнения операции обнаружения знаний придется вернуться на экран **Управление доменами** , нажать кнопку **Готово**, а затем либо кнопку **Да** для публикации базы знаний, либо кнопку **Нет** , чтобы сохранить работу в базе знаний и выйти.</span><span class="sxs-lookup"><span data-stu-id="93707-121">After clicking **Close**, to perform the Knowledge Discovery activity, you would have to return to the **Domain Management** screen, click **Finish**, and then click either **Yes** to publish the knowledge base or **No** to save the work on the knowledge base and exit.</span></span>  <span data-ttu-id="93707-122">Дополнительные сведения об открытии заблокированной базы знаний см. в разделе [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="93707-122">For more information on opening a locked knowledge base, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
  

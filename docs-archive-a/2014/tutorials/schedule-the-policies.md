---
title: Планирование политик | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 59417a54-55f1-4468-ba41-368aa852c2d4
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 1bce1b9d650606e9485899c34c72ca6b27a72dae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735609"
---
# <a name="schedule-the-policies"></a><span data-ttu-id="bb716-102">Планирование политик</span><span class="sxs-lookup"><span data-stu-id="bb716-102">Schedule the Policies</span></span>
  <span data-ttu-id="bb716-103">В этой задаче будет осуществлено планирование рекомендованных политик, импортированных в предыдущей задаче.</span><span class="sxs-lookup"><span data-stu-id="bb716-103">In this task, you will schedule the best practices policies that you imported in the previous task.</span></span>  
  
### <a name="to-schedule-the-best-practices-policies"></a><span data-ttu-id="bb716-104">Планирование рекомендованных политик</span><span class="sxs-lookup"><span data-stu-id="bb716-104">To schedule the best practices policies</span></span>  
  
1.  <span data-ttu-id="bb716-105">В обозревателе объектов разверните узел **Управление**, разверните **Управление политиками**, **разверните узел политики,** щелкните правой кнопкой мыши политику рекомендаций и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="bb716-105">In Object Explorer, expand **Management**, expand **Policy Management**, expand **Policies**, right-click a best practices policy, and then click **Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb716-106">В качестве альтернативы можно легко увидеть, какие политики связаны с рекомендациями, а также отсортировать рекомендации по категориям, раскройте узел **Управление**, разверните **Управление политиками**, а затем щелкните **политики**.</span><span class="sxs-lookup"><span data-stu-id="bb716-106">As an alternative, to easily see which policies are associated with best practices and to sort the best practices categories, expand **Management**, expand **Policy Management**, and then click **Policies**.</span></span> <span data-ttu-id="bb716-107">В меню **Вид** выберите **Сведения об обозревателе объектов**.</span><span class="sxs-lookup"><span data-stu-id="bb716-107">On the **View** menu, click **Object Explorer Details**.</span></span> <span data-ttu-id="bb716-108">В области **Подробности обозревателя объектов** щелкните заголовок **категории** , чтобы отсортировать политики по категориям.</span><span class="sxs-lookup"><span data-stu-id="bb716-108">In the **Object Explorer Details** pane, click the **Category** heading to sort the policies by category.</span></span> <span data-ttu-id="bb716-109">Рекомендуемые политики имеют префиксные **рекомендации корпорации Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="bb716-109">The best practices policies have the prefix **Microsoft Best Practices**.</span></span> <span data-ttu-id="bb716-110">Щелкните правой кнопкой мыши политику, которую требуется настроить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="bb716-110">Right-click the policy that you want to configure, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="bb716-111">На странице **Общие** диалогового окна **Открытие политики** в списке **режим оценки** выберите значение **по расписанию**.</span><span class="sxs-lookup"><span data-stu-id="bb716-111">On the **General** page of the **Open Policy** dialog box, in the **Evaluation Mode** list, click **On schedule**.</span></span>  
  
3.  <span data-ttu-id="bb716-112">Нажмите кнопку **выбрать** рядом с полем **Расписание** , чтобы указать существующее расписание, или нажмите кнопку **создать** , чтобы создать новое расписание.</span><span class="sxs-lookup"><span data-stu-id="bb716-112">Next to the **Schedule** box, click **Pick** to specify an existing schedule, or click **New** to create a new schedule.</span></span>  
  
4.  <span data-ttu-id="bb716-113">После настройки расписания можно установить флажок **включено** в верхней части страницы, чтобы включить запланированную политику.</span><span class="sxs-lookup"><span data-stu-id="bb716-113">After you have configured a schedule, you can select the **Enabled** check box near the top of the page to enable the scheduled policy.</span></span>  
  
5.  <span data-ttu-id="bb716-114">Повторяйте шаги от 1 до 4 для каждой политики, которую необходимо запланировать.</span><span class="sxs-lookup"><span data-stu-id="bb716-114">Repeats steps 1 through 4 for each policy that you want to schedule.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb716-115">Чтобы просмотреть результаты вычисления после запуска запланированной политики, откройте журнал политик на целевом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="bb716-115">To view the evaluation results after a scheduled policy runs, open the Policy History log on the target instance.</span></span> <span data-ttu-id="bb716-116">Чтобы открыть журнал, щелкните правой кнопкой мыши элемент **Управление политиками**и выберите пункт **Просмотр журнала**.</span><span class="sxs-lookup"><span data-stu-id="bb716-116">To open the log, right-click **Policy Management**, and then click **View History**.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="bb716-117">Итоги</span><span class="sxs-lookup"><span data-stu-id="bb716-117">Summary</span></span>  
 <span data-ttu-id="bb716-118">Тем самым была выполнена настройка запланированных политик на выполнение в единственном экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb716-118">You configured scheduled policies to run on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bb716-119">Если необходимо развернуть запланированные политики на нескольких экземплярах, перейдите к следующей задаче в этом учебнике.</span><span class="sxs-lookup"><span data-stu-id="bb716-119">If you want to deploy scheduled policies to multiple instances, continue to the next task in this tutorial.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bb716-120">Next Steps</span><span class="sxs-lookup"><span data-stu-id="bb716-120">Next Steps</span></span>  
 [<span data-ttu-id="bb716-121">Развертывание запланированных политик на нескольких экзмплярах</span><span class="sxs-lookup"><span data-stu-id="bb716-121">Deploy Scheduled Policies to Multiple Instances</span></span>](../../2014/tutorials/deploy-scheduled-policies-to-multiple-instances.md)  
  
  

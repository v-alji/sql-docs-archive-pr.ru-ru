---
title: Настройка сервера для выполнения политики "Отключено по умолчанию" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 41c3022d-ab13-443e-ac64-ba1d64584f79
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c0842a30b7d0bbcd1b01ee9e98ed1ed9a74f0f35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655681"
---
# <a name="configure-a-server-to-run-the-off-by-default-policy"></a><span data-ttu-id="f9e03-102">Настройка сервера для выполнения политики «Отключено по умолчанию»</span><span class="sxs-lookup"><span data-stu-id="f9e03-102">Configure a Server to Run the Off By Default Policy</span></span>
  <span data-ttu-id="f9e03-103">Теперь есть политика с именем «Отключено по умолчанию».</span><span class="sxs-lookup"><span data-stu-id="f9e03-103">Now you have a policy named Off By Default.</span></span> <span data-ttu-id="f9e03-104">В этой задаче производится проверка сервера на соответствие требованиям политики «Отключено по умолчанию».</span><span class="sxs-lookup"><span data-stu-id="f9e03-104">In this task, you will check to see whether your server complies with the requirements of this policy.</span></span>  
  
### <a name="to-run-the-off-by-default-policy"></a><span data-ttu-id="f9e03-105">Запуск политики «Отключено по умолчанию»</span><span class="sxs-lookup"><span data-stu-id="f9e03-105">To run the Off By Default policy</span></span>  
  
1.  <span data-ttu-id="f9e03-106">В обозревателе объектов щелкните правой кнопкой мыши экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], наведите указатель на пункт **Политики**и выберите пункт **Вычислить**.</span><span class="sxs-lookup"><span data-stu-id="f9e03-106">In Object Explorer, right-click your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], point to **Policies**, and then click **Evaluate**.</span></span>  
  
2.  <span data-ttu-id="f9e03-107">В диалоговом окне **Выполнить политики** можно выбрать политики из другого экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или из файла.</span><span class="sxs-lookup"><span data-stu-id="f9e03-107">In the **Evaluate Policies** dialog box you can select policies from another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or from a file.</span></span> <span data-ttu-id="f9e03-108">На этом шаге оставьте **Источник** , в качестве которого выбран ваш экземпляр [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9e03-108">For this step, leave **Source** set to your instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="f9e03-109">В разделе **Политики** выберите политику **Отключено по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="f9e03-109">In the **Policies** section, select the **Off By Default** policy.</span></span>  
  
4.  <span data-ttu-id="f9e03-110">Для просмотра соответствия сервера политике нажмите **Вычислить**.</span><span class="sxs-lookup"><span data-stu-id="f9e03-110">To see whether the server is in compliance with the policy, click **Evaluate**.</span></span>  
  
5.  <span data-ttu-id="f9e03-111">При соответствии компонента **политике в области** Результаты [!INCLUDE[ssDE](../../includes/ssde-md.md)] отобразится зеленый круг с галочкой.</span><span class="sxs-lookup"><span data-stu-id="f9e03-111">In the **Results** area, you will see a green circle with a check mark if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] complies with the policy.</span></span> <span data-ttu-id="f9e03-112">Если компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] не соответствует политике, отобразится красный круг со знаком «X».</span><span class="sxs-lookup"><span data-stu-id="f9e03-112">You will see a red circle with an X if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not comply with the policy.</span></span>  
  
6.  <span data-ttu-id="f9e03-113">В области **Данные целевого объекта** при возникновении ошибки дополнительные сведения можно просмотреть в столбце **Сообщение** .</span><span class="sxs-lookup"><span data-stu-id="f9e03-113">In the **Target Details** area, you will see additional information in the **Message** column if an error occurs.</span></span> <span data-ttu-id="f9e03-114">Для просмотра отчета, содержащего результаты проверки каждого свойства аспекта, в столбце **Сообщение** нажмите **Просмотреть** .</span><span class="sxs-lookup"><span data-stu-id="f9e03-114">In the **Message** column, click **View** to see a report that contains the results of the check for each facet property that was checked.</span></span>  
  
7.  <span data-ttu-id="f9e03-115">Описание политики отобразится в нижней части страницы, и в разделе **Дополнительная справка** будет показана гиперссылка, настроенная для политики.</span><span class="sxs-lookup"><span data-stu-id="f9e03-115">The policy description is displayed at the bottom of the page, and the **Additional help** section displays the hyperlink that you have configured for the policy.</span></span> <span data-ttu-id="f9e03-116">Для открытия веб-страницы, указанной при создании политики, щелкните сообщение гиперссылки.</span><span class="sxs-lookup"><span data-stu-id="f9e03-116">Click the message hyperlink to open the Web page that you specified when you created the policy.</span></span>  
  
8.  <span data-ttu-id="f9e03-117">Закройте браузер и диалоговое окно **Подробный просмотр результатов** .</span><span class="sxs-lookup"><span data-stu-id="f9e03-117">Close the browser, and then close the **Results Detailed View** dialog box.</span></span>  
  
9. <span data-ttu-id="f9e03-118">Если требуется отключить компонент Database Mail при несоответствии сервера политике, нажмите кнопку **Применить** на странице **Результаты вычислений** .</span><span class="sxs-lookup"><span data-stu-id="f9e03-118">If the server is out of compliance and you want to disable Database Mail, click **Apply** in the **Evaluation Results** page.</span></span>  
  
10. <span data-ttu-id="f9e03-119">Закройте диалоговые окна **Подробный просмотр результатов** и **Вычисление политик** .</span><span class="sxs-lookup"><span data-stu-id="f9e03-119">Close both the **Results Detailed View** and the **Evaluate Policies** dialog boxes.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="f9e03-120">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="f9e03-120">Next Lesson</span></span>  
 [<span data-ttu-id="f9e03-121">Урок 2. Создание и применение политики стандартов именования</span><span class="sxs-lookup"><span data-stu-id="f9e03-121">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
  
  

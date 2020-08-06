---
title: Создание политики, отключенной по умолчанию | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 98fde3c5-297c-4d95-981e-95700bbf5ccd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 16d0893c155627a41149263b5ce7b21a4a217b74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655682"
---
# <a name="create-the-off-by-default-policy"></a><span data-ttu-id="b31a2-102">Создание политики, отключенной по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b31a2-102">Create the Off By Default Policy</span></span>
  <span data-ttu-id="b31a2-103">В этой задаче создается условие с именем «Mail Off», основанное на аспекте «Настройка контактной зоны».</span><span class="sxs-lookup"><span data-stu-id="b31a2-103">This task creates a condition named Mail Off that is based on the Surface Area Configuration facet.</span></span> <span data-ttu-id="b31a2-104">Затем создается политика с именем «Отключена по умолчанию».</span><span class="sxs-lookup"><span data-stu-id="b31a2-104">Then, it creates a policy named Off By Default.</span></span>  
  
### <a name="to-create-the-mail-off-condition"></a><span data-ttu-id="b31a2-105">Создание условия «Mail Off»</span><span class="sxs-lookup"><span data-stu-id="b31a2-105">To create the Mail Off condition</span></span>  
  
1.  <span data-ttu-id="b31a2-106">В обозревателе объектов последовательно разверните узлы **Управление**, **Управление политиками**и **Аспекты**, щелкните правой кнопкой мыши аспект **Настройка контактной зоны**и выберите пункт **Создать условие**.</span><span class="sxs-lookup"><span data-stu-id="b31a2-106">In Object Explorer, expand **Management**, expand **Policy Management**, expand **Facets**, right-click **Surface Area Configuration**, and then click **New Condition**.</span></span>  
  
2.  <span data-ttu-id="b31a2-107">В диалоговом окне **Создание нового условия** в поле **Имя** введите **Почта отключена**.</span><span class="sxs-lookup"><span data-stu-id="b31a2-107">In the **Create New Condition** dialog box, in the **Name** box, type **Mail Off**.</span></span>  
  
3.  <span data-ttu-id="b31a2-108">В окне **Аспект** подтвердите выбор аспекта **Настройка контактной зоны** .</span><span class="sxs-lookup"><span data-stu-id="b31a2-108">In the **Facet** box, confirm that **Surface Area Configuration** facet is selected.</span></span>  
  
4.  <span data-ttu-id="b31a2-109">В области **выражение** в поле **поле** выберите \*\* \@ DatabaseMailEnabled\*\*, в поле **оператор** выберите **=** , а в списке **значение** выберите **false**.</span><span class="sxs-lookup"><span data-stu-id="b31a2-109">In the **Expression** area, in the **Field** box, select **\@DatabaseMailEnabled**, in the **Operator** box select **=**, and in the **Value** select **False**.</span></span>  
  
5.  <span data-ttu-id="b31a2-110">Для создания условия введите его описание на странице **Описание** и нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="b31a2-110">On the **Description** page, type a description of the condition, and then click **OK** to create the condition.</span></span>  
  
### <a name="to-create-the-off-by-default-policy"></a><span data-ttu-id="b31a2-111">Создание политики, отключенной по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b31a2-111">To create the Off By Default policy</span></span>  
  
1.  <span data-ttu-id="b31a2-112">В обозревателе объектов щелкните правой кнопкой мыши папку **Настройка контактной зоны**и выберите в контекстном меню пункт **Создать политику**.</span><span class="sxs-lookup"><span data-stu-id="b31a2-112">In Object Explorer, right-click **Surface Area Configuration**, and then click **New Policy**.</span></span>  
  
2.  <span data-ttu-id="b31a2-113">В диалоговом окне **Создание новой политики** в поле **Имя** введите **Отключена по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="b31a2-113">In the **Create New Policy** dialog box, in the **Name** box, type **Off By Default**.</span></span>  
  
3.  <span data-ttu-id="b31a2-114">Не устанавливайте флажок **Включена** .</span><span class="sxs-lookup"><span data-stu-id="b31a2-114">Leave the **Enabled** checkbox unchecked.</span></span> <span data-ttu-id="b31a2-115">Флажок **Включена** применяется к автоматическим политикам, а данная политика будет выполняться по запросу.</span><span class="sxs-lookup"><span data-stu-id="b31a2-115">The **Enabled** checkbox applies to automated policies, and this policy will be executed on demand.</span></span>  
  
4.  <span data-ttu-id="b31a2-116">Прокрутите список флажков **Проверить условие** вниз до области **Настройка контактной зоны** и выберите **Почта отключена** в качестве условия для проверки.</span><span class="sxs-lookup"><span data-stu-id="b31a2-116">In the **Check condition** checkbox, scroll down to the **Surface Area Configuration** area, and then select **Mail Off** as the condition to check.</span></span>  
  
5.  <span data-ttu-id="b31a2-117">Поле **Применить к** будет пустым, так как это политика уровня сервера.</span><span class="sxs-lookup"><span data-stu-id="b31a2-117">The **Against targets** box will be blank because this is a server-scoped policy.</span></span>  
  
6.  <span data-ttu-id="b31a2-118">В списке флажков **Режим оценки** в качестве режима вычисления выберите **По запросу** .</span><span class="sxs-lookup"><span data-stu-id="b31a2-118">In the **Evaluation Mode** checkbox, select **On demand** as the evaluation mode.</span></span>  
  
7.  <span data-ttu-id="b31a2-119">В поле **Ограничение сервера** выберите пункт **Нет**.</span><span class="sxs-lookup"><span data-stu-id="b31a2-119">In the **Server restriction** checkbox, select **None**.</span></span>  
  
8.  <span data-ttu-id="b31a2-120">На странице **Описание** введите описание политики.</span><span class="sxs-lookup"><span data-stu-id="b31a2-120">On the **Description** page, type a description of the policy.</span></span>  
  
9. <span data-ttu-id="b31a2-121">В области **Гиперссылка на дополнительную справку** вы можете указать ссылку на веб-страницу для политик.</span><span class="sxs-lookup"><span data-stu-id="b31a2-121">You can provide a hyperlink to a Web page for your policies in the **Additional help hyperlink** area.</span></span> <span data-ttu-id="b31a2-122">В окне **Отображаемый текст** введите текст, который будет иметь эта гиперссылка.</span><span class="sxs-lookup"><span data-stu-id="b31a2-122">In the **Text to display** box, type the text that will appear for the hyperlink.</span></span>  
  
10. <span data-ttu-id="b31a2-123">В окне **Адрес** введите гиперссылку на страницу справки, например домашнюю страницу ИТ-отдела компании.</span><span class="sxs-lookup"><span data-stu-id="b31a2-123">In the **Address** box, type a hyperlink to a Help page, such as the home page for the IT department of your company.</span></span>  
  
11. <span data-ttu-id="b31a2-124">Для проверки адреса открытия веб-страницы нажмите **Проверить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="b31a2-124">To confirm the address by opening the Web page, click **Test Link**.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b31a2-125">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="b31a2-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b31a2-126">Настройка сервера для выполнения политики «Отключено по умолчанию»</span><span class="sxs-lookup"><span data-stu-id="b31a2-126">Configure a Server to Run the Off By Default Policy</span></span>](lesson-1-2-configure-a-server-to-run-the-off-by-default-policy.md)  
  
  

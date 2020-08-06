---
title: Создание соединения семантической модели бизнес-аналитики с книгой PowerPivot | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b2e3f97f-18a8-42b6-9030-b4f818afc3b9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7ea4ddcc38328acc6ff8cfb5387b13056b689a24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666797"
---
# <a name="create-a-bi-semantic-model-connection-to-a-powerpivot-workbook"></a><span data-ttu-id="f7da2-102">Создание соединения семантической модели бизнес-аналитики с книгой PowerPivot</span><span class="sxs-lookup"><span data-stu-id="f7da2-102">Create a BI Semantic Model Connection to a PowerPivot Workbook</span></span>
  <span data-ttu-id="f7da2-103">Сведения, приведенные в этом разделе, помогут настроить соединение семантической модели бизнес-аналитики, которое перенаправляет на книгу PowerPivot в той же ферме.</span><span class="sxs-lookup"><span data-stu-id="f7da2-103">Use the information in this topic to set up a BI semantic model connection that redirects to a PowerPivot workbook in the same farm.</span></span>  
  
 <span data-ttu-id="f7da2-104">После создания соединения семантической модели бизнес-аналитики и настройки разрешений SharePoint это соединение можно использовать в качестве источника данных для отчетов Excel или [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f7da2-104">After you create a BI semantic model connection and configure SharePoint permissions, you can use it as a data source for Excel or [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span>  
  
 <span data-ttu-id="f7da2-105">Этот раздел включает следующие подразделы:</span><span class="sxs-lookup"><span data-stu-id="f7da2-105">This topic includes the following sections.</span></span> <span data-ttu-id="f7da2-106">Выполните задачи в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="f7da2-106">Perform each task in the order given.</span></span>  
  
 [<span data-ttu-id="f7da2-107">Проверка предварительных требований</span><span class="sxs-lookup"><span data-stu-id="f7da2-107">Review Prerequisites</span></span>](#bkmk_prereq)  
  
 [<span data-ttu-id="f7da2-108">Создание подключения</span><span class="sxs-lookup"><span data-stu-id="f7da2-108">Create a Connection</span></span>](#bkmk_create)  
  
 [<span data-ttu-id="f7da2-109">Настройка разрешений SharePoint для соединения семантической модели бизнес-аналитики</span><span class="sxs-lookup"><span data-stu-id="f7da2-109">Configure SharePoint Permissions on the BI Semantic Model Connection</span></span>](#bkmk_permissions)  
  
 [<span data-ttu-id="f7da2-110">Настройка разрешений SharePoint для книги</span><span class="sxs-lookup"><span data-stu-id="f7da2-110">Configure SharePoint Permissions on the Workbook</span></span>](#bkmk_userdb)  
  
 [<span data-ttu-id="f7da2-111">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="f7da2-111">Next Steps</span></span>](#bkmk_next)  
  
##  <a name="review-prerequisites"></a><a name="bkmk_prereq"></a><span data-ttu-id="f7da2-112">Проверка предварительных требований</span><span class="sxs-lookup"><span data-stu-id="f7da2-112">Review Prerequisites</span></span>  
 <span data-ttu-id="f7da2-113">Для создания файла соединения семантической модели бизнес-аналитики требуется разрешение «Участие» или выше.</span><span class="sxs-lookup"><span data-stu-id="f7da2-113">You must have Contribute permissions or above to create a BI semantic model connection file.</span></span>  
  
 <span data-ttu-id="f7da2-114">Необходима библиотека, поддерживающая тип содержимого соединения семантической модели бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="f7da2-114">You must have a library that supports the BI semantic model connection content type.</span></span> <span data-ttu-id="f7da2-115">Дополнительные сведения см. в разделе [Добавление типа содержимого соединения семантической модели бизнес-аналитики в библиотеку &#40;PowerPivot для SharePoint&#41;](add-bi-semantic-model-connection-content-type-to-library.md).</span><span class="sxs-lookup"><span data-stu-id="f7da2-115">For more information, see [Add a BI Semantic Model Connection Content Type to a Library &#40;PowerPivot for SharePoint&#41;](add-bi-semantic-model-connection-content-type-to-library.md).</span></span>  
  
 <span data-ttu-id="f7da2-116">Необходимо указать URL-адрес книги PowerPivot, для которой настраивается соединение семантической модели бизнес-аналитики (например, http://adventure-works/shared Documents/myworkbook.xlsx).</span><span class="sxs-lookup"><span data-stu-id="f7da2-116">You must know the URL of the PowerPivot workbook for which you are setting up a BI semantic model connection (for example, http://adventure-works/shared documents/myworkbook.xlsx).</span></span> <span data-ttu-id="f7da2-117">Книга должна находиться в той же ферме.</span><span class="sxs-lookup"><span data-stu-id="f7da2-117">The workbook must be in the same farm.</span></span>  
  
 <span data-ttu-id="f7da2-118">Все компьютеры и пользователи, участвующие в последовательности соединения, должны относиться к одному домену или находиться в доверенном домене (двустороннее доверие).</span><span class="sxs-lookup"><span data-stu-id="f7da2-118">All computers and users that participate in the connection sequence must be in the same domain or trusted domain (two-way trust).</span></span>  
  
##  <a name="create-a-connection"></a><a name="bkmk_create"></a><span data-ttu-id="f7da2-119">Создание подключения</span><span class="sxs-lookup"><span data-stu-id="f7da2-119">Create a Connection</span></span>  
  
1.  <span data-ttu-id="f7da2-120">В библиотеке, в которой будет размещаться соединение семантической модели бизнес-аналитики, нажмите кнопку **Документы** на ленте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f7da2-120">In the library that will contain the BI semantic model connection, click **Documents** on the SharePoint ribbon.</span></span> <span data-ttu-id="f7da2-121">Щелкните стрелку вниз на кнопке "Новый документ" и выберите **Файл соединения BISM** , чтобы открыть страницу "Создание соединения BISM".</span><span class="sxs-lookup"><span data-stu-id="f7da2-121">Click the down arrow on New Document, and select **BISM Connection File** to open the New BI Semantic Model Connection page.</span></span>  
  
     <span data-ttu-id="f7da2-122">![Подменю «Создать документ» в библиотеке SharePoint](../media/ssas-bismconnection-new.gif "Подменю «Создать документ» в библиотеке SharePoint")</span><span class="sxs-lookup"><span data-stu-id="f7da2-122">![New Document submenu in a SharePoint library](../media/ssas-bismconnection-new.gif "New Document submenu in a SharePoint library")</span></span>  
  
2.  <span data-ttu-id="f7da2-123">Задайте для свойства **сервера** URL-адрес SharePoint книги PowerPivot (например, \*\* http://mysharepoint/shared Documents/myWorkbook.xlsx\*\*.</span><span class="sxs-lookup"><span data-stu-id="f7da2-123">Set the **Server** property to the SharePoint URL of the PowerPivot workbook (for example, **http://mysharepoint/shared documents/myWorkbook.xlsx**.</span></span> <span data-ttu-id="f7da2-124">При развертывании PowerPivot для SharePoint данные могут быть загружены на любой сервер в ферме.</span><span class="sxs-lookup"><span data-stu-id="f7da2-124">In a PowerPivot for SharePoint deployment, data can be loaded on any server in the farm.</span></span> <span data-ttu-id="f7da2-125">По этой причине в соединениях с источниками данных PowerPivot указывается только путь к рабочей книге.</span><span class="sxs-lookup"><span data-stu-id="f7da2-125">For this reason, data source connections to PowerPivot data specify just the path to the workbook.</span></span> <span data-ttu-id="f7da2-126">Системная служба PowerPivot определяет, какой сервер загружает данные.</span><span class="sxs-lookup"><span data-stu-id="f7da2-126">The PowerPivot System Service determines which server loads the data.</span></span>  
  
     <span data-ttu-id="f7da2-127">Не используйте свойство **базы данных** . Он не используется при указании расположения книги PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="f7da2-127">Do not use the **Database** property; it is not used when specifying the location of a PowerPivot workbook.</span></span>  
  
     <span data-ttu-id="f7da2-128">Страница должна выглядеть примерно так, как на следующей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="f7da2-128">Your page should look similar to the following illustration.</span></span>  
  
     <span data-ttu-id="f7da2-129">![Страница соединения BISM, на которой показан URL-адрес книги](../media/ssas-bismconnection-ppvtds.gif "Страница соединения BISM, на которой показан URL-адрес книги")</span><span class="sxs-lookup"><span data-stu-id="f7da2-129">![BISM connection page showing URL to workbook](../media/ssas-bismconnection-ppvtds.gif "BISM connection page showing URL to workbook")</span></span>  
  
     <span data-ttu-id="f7da2-130">(Необязательно.) При наличии разрешений SharePoint для книги выполняется дополнительная проверка, что позволяет убедиться в правильности расположения.</span><span class="sxs-lookup"><span data-stu-id="f7da2-130">Optionally, if you have SharePoint permissions to the workbook, an extra validation step is performed, ensuring that the location is valid.</span></span> <span data-ttu-id="f7da2-131">Если разрешения на доступ к данным нет, предоставляется возможность сохранить соединение семантической модели бизнес-аналитики без проверки.</span><span class="sxs-lookup"><span data-stu-id="f7da2-131">If you do not have permission to access the data, you are given the option of saving the BI semantic model connection without the validation response.</span></span>  
  
##  <a name="configure-sharepoint-permissions-on-the-bi-semantic-model-connection"></a><a name="bkmk_permissions"></a><span data-ttu-id="f7da2-132">Настройка разрешений SharePoint для соединения семантической модели бизнес-аналитики</span><span class="sxs-lookup"><span data-stu-id="f7da2-132">Configure SharePoint Permissions on the BI Semantic Model Connection</span></span>  
 <span data-ttu-id="f7da2-133">Для использования соединения семантической модели бизнес-аналитики в качестве источника данных для книги Excel или отчета служб Reporting Services необходимо разрешение **Чтение** для элемента соединения семантической модели бизнес-аналитики в библиотеке SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f7da2-133">Ability to use a BI semantic model connection as a data source for an Excel workbook or Reporting Services report requires **Read** permissions on the BI semantic model connection item in a SharePoint library.</span></span> <span data-ttu-id="f7da2-134">Уровень разрешения "Чтение" включает разрешение **Открытие элементов** , которое позволяет загружать сведения о соединении семантической модели бизнес-аналитики в приложение Excel для рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="f7da2-134">The Read permission level includes the **Open Items** permission that enables downloading BI semantic model connection information to an Excel desktop application.</span></span>  
  
 <span data-ttu-id="f7da2-135">В SharePoint имеется несколько способов предоставления разрешений.</span><span class="sxs-lookup"><span data-stu-id="f7da2-135">There are several ways to grant permissions in SharePoint.</span></span> <span data-ttu-id="f7da2-136">В следующей процедуре описывается создание новой группы с именем **Пользователи BISM** , которая получает уровень разрешений **Чтение** .</span><span class="sxs-lookup"><span data-stu-id="f7da2-136">The following instructions explain how to create a new group called **BISM Users** that have the **Read** permission level.</span></span>  
  
 <span data-ttu-id="f7da2-137">Изменять разрешения могут только владельцы сайтов.</span><span class="sxs-lookup"><span data-stu-id="f7da2-137">You must be a site owner to change permissions.</span></span>  
  
1.  <span data-ttu-id="f7da2-138">В разделе "Действия сайта" щелкните **Разрешения сайта**.</span><span class="sxs-lookup"><span data-stu-id="f7da2-138">In Site Actions, click **Site Permissions**.</span></span>  
  
2.  <span data-ttu-id="f7da2-139">Щелкните **Создать группу** и укажите для новой группы имя **Пользователи BISM**.</span><span class="sxs-lookup"><span data-stu-id="f7da2-139">Click **Create Group** and name the new group **BISM Users**.</span></span>  
  
3.  <span data-ttu-id="f7da2-140">Выберите уровень разрешений **Чтение** и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f7da2-140">Choose the **Read** permission level and click **Create**.</span></span>  
  
4.  <span data-ttu-id="f7da2-141">Выберите **Пользователи BISM** в поле "Пользователи и группы".</span><span class="sxs-lookup"><span data-stu-id="f7da2-141">Select **BISM Users** in People and Groups.</span></span>  
  
5.  <span data-ttu-id="f7da2-142">Наведите указатель мыши на пункт "Создать", выберите **Добавить пользователей**и добавьте учетные записи пользователей или групп.</span><span class="sxs-lookup"><span data-stu-id="f7da2-142">Point to New, click **Add Users**, and then add user or group accounts.</span></span>  
  
     <span data-ttu-id="f7da2-143">Теперь у этих пользователей и групп будет разрешение «Чтение» для всего сайта, включая все библиотеки и списки, которые наследуют разрешения на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="f7da2-143">These users and groups will now have Read permissions throughout the site, including all libraries and lists that inherit permissions from the site level.</span></span> <span data-ttu-id="f7da2-144">Если эти разрешения оказываются слишком большими, можно удалить данную группу из определенных библиотек, списков или элементов.</span><span class="sxs-lookup"><span data-stu-id="f7da2-144">If these permissions are too high, you can selectively remove this group from specific libraries, lists, or items.</span></span>  
  
 <span data-ttu-id="f7da2-145">Чтобы выборочно удалить разрешения на уровне элемента, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f7da2-145">To selectively remove permissions at the item level, do the following:</span></span>  
  
1.  <span data-ttu-id="f7da2-146">Выберите документ в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="f7da2-146">In a library, select a document.</span></span> <span data-ttu-id="f7da2-147">Нажмите правую кнопку со стрелкой вниз и выберите пункт **Управление разрешениями**.</span><span class="sxs-lookup"><span data-stu-id="f7da2-147">Click the right down arrow and then click **Manage Permissions**.</span></span>  
  
2.  <span data-ttu-id="f7da2-148">По умолчанию элемент наследует разрешения.</span><span class="sxs-lookup"><span data-stu-id="f7da2-148">By default, an item inherits permissions.</span></span> <span data-ttu-id="f7da2-149">Чтобы изменить разрешения для отдельных документов в этой библиотеке, нажмите кнопку **Прекратить наследование разрешений**.</span><span class="sxs-lookup"><span data-stu-id="f7da2-149">To change the permissions of individual documents in this library, click **Stop Inheriting Permissions**.</span></span>  
  
3.  <span data-ttu-id="f7da2-150">Установите флажок для группы **Пользователи BISM**.</span><span class="sxs-lookup"><span data-stu-id="f7da2-150">Select the checkbox next to **BISM Users**.</span></span>  
  
4.  <span data-ttu-id="f7da2-151">Нажмите кнопку **Удалить разрешения пользователя**.</span><span class="sxs-lookup"><span data-stu-id="f7da2-151">Click **Remove User Permissions**.</span></span>  
  
##  <a name="configure-sharepoint-permissions-on-the-workbook"></a><a name="bkmk_userdb"></a><span data-ttu-id="f7da2-152">Настройка разрешений SharePoint для книги</span><span class="sxs-lookup"><span data-stu-id="f7da2-152">Configure SharePoint Permissions on the Workbook</span></span>  
 <span data-ttu-id="f7da2-153">При использовании базы данных PowerPivot в книге Excel разрешения SharePoint для книги Excel определяют доступ к данным через соединение семантической модели бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="f7da2-153">If you are using a PowerPivot database inside an Excel workbook, the SharePoint permissions on the Excel workbook determine data access via the BI semantic model connection.</span></span> <span data-ttu-id="f7da2-154">Все пользователи, обращающиеся к книге, должны иметь применительно к ней разрешения «Чтение» для ее использования в качестве внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="f7da2-154">All users who access the workbook must have Read permissions on the workbook in order to use it as an external data source.</span></span>  
  
 <span data-ttu-id="f7da2-155">Если группа **Пользователи BISM** создана с помощью вышеописанной процедуры, учетные записи пользователей и групп, входящих в группу **Пользователи BISM** , получают достаточные разрешения для книги и файла подключения семантической модели бизнес-аналитики при условии, что в книге используются унаследованные разрешения.</span><span class="sxs-lookup"><span data-stu-id="f7da2-155">If you created a **BISM Users** group using the instructions in the previous section, user and group accounts that are members of **BISM Users** will have sufficient permission on the workbook as well as the BI semantic model connection file, assuming the workbook uses inherited permissions.</span></span>  
  
##  <a name="next-steps"></a><a name="bkmk_next"></a> <span data-ttu-id="f7da2-156">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="f7da2-156">Next Steps</span></span>  
 <span data-ttu-id="f7da2-157">После создания и обеспечения безопасности соединения семантической модели бизнес-аналитики его можно указать в качестве источника данных.</span><span class="sxs-lookup"><span data-stu-id="f7da2-157">After you create and secure a BI semantic model connection, you can specify it as a data source.</span></span> <span data-ttu-id="f7da2-158">Дополнительные сведения см. в разделе [Использование соединения семантической модели бизнес-аналитики в службах Excel или Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="f7da2-158">For more information, see [Use a BI Semantic Model Connection in Excel or Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7da2-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="f7da2-159">See Also</span></span>  
 <span data-ttu-id="f7da2-160">[Соединение семантической модели бизнес-аналитики PowerPivot &#40;. BISM&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span><span class="sxs-lookup"><span data-stu-id="f7da2-160">[PowerPivot BI Semantic Model Connection &#40;.bism&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span></span>  
 <span data-ttu-id="f7da2-161">[Использование соединения семантической модели бизнес-аналитики в Excel или Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="f7da2-161">[Use a BI Semantic Model Connection in Excel or Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md) </span></span>  
 [<span data-ttu-id="f7da2-162">Create a BI Semantic Model Connection to a Tabular Model Database</span><span class="sxs-lookup"><span data-stu-id="f7da2-162">Create a BI Semantic Model Connection to a Tabular Model Database</span></span>](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md)  
  
  

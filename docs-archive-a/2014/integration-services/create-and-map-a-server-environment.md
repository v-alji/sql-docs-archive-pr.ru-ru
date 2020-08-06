---
title: Создание и сопоставьте серверную среду | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isenvprop.variables.f1
- sql12.ssis.ssms.iscreateenv.f1
- sql12.ssis.ssms.isenvprop.permissions.f1
- sql12.ssis.ssms.isenvprop.general.f1
ms.assetid: b1cbb697-713f-48e4-b234-b23724d87451
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9331b5078effb562931f45c48bd8ff975c1d1998
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658325"
---
# <a name="create-and-map-a-server-environment"></a><span data-ttu-id="26a91-102">Создание и сопоставление серверной среды</span><span class="sxs-lookup"><span data-stu-id="26a91-102">Create and Map a Server Environment</span></span>
  <span data-ttu-id="26a91-103">Вы создаете серверную среду, которая должна указывать значения среды выполнения для пакетов, которые содержатся в проекте, развернутом на сервере [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26a91-103">You create a server environment to specify runtime values for packages contained in a project you've deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="26a91-104">Можно сопоставить переменные среды с параметрами для определенного пакета, для пакетов точки входа или для всех пакетов в данном проекте.</span><span class="sxs-lookup"><span data-stu-id="26a91-104">You can then map the environment variables to parameters, for a specific package, for entry-point packages, or for all the packages in a given project.</span></span> <span data-ttu-id="26a91-105">Пакет точки входа — обычно родительский пакет, который выполняет дочерний пакет.</span><span class="sxs-lookup"><span data-stu-id="26a91-105">An entry-point package is typically a parent package that executes a child package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="26a91-106">Для данного выполнения пакет может выполняться только со значениями, содержащимися в односерверной среде.</span><span class="sxs-lookup"><span data-stu-id="26a91-106">For a given execution, a package can execute only with the values contained in a single server environment.</span></span>  
  
 <span data-ttu-id="26a91-107">У представлений можно запрашивать список серверных сред, ссылок на среды и переменных сред.</span><span class="sxs-lookup"><span data-stu-id="26a91-107">You can query views for a list of server environments, environment references, and environment variables.</span></span> <span data-ttu-id="26a91-108">Также можно вызывать хранимые процедуры для добавления, удаления и изменения сред, ссылок на среды и переменных сред.</span><span class="sxs-lookup"><span data-stu-id="26a91-108">You can also call stored to add, delete, and modify environments, environment references, and environment variables.</span></span> <span data-ttu-id="26a91-109">Дополнительные сведения см. в разделе **Серверные среды, переменные сервера и ссылки на серверные среды** в [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="26a91-109">For more information, see the **Server Environments, Server Variables and Server Environment References** section in [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
### <a name="to-create-and-use-a-server-environment"></a><span data-ttu-id="26a91-110">Создание и использование серверной среды</span><span class="sxs-lookup"><span data-stu-id="26a91-110">To create and use a server environment</span></span>  
  
1.  <span data-ttu-id="26a91-111">В [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] среде разверните узел каталоги> **SSISDB** в обозревателе объектов и выберите папку **среды** проекта, для которой требуется создать среду.</span><span class="sxs-lookup"><span data-stu-id="26a91-111">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], expand the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Catalogs> **SSISDB** node in Object Explorer, and locate the **Environments** folder of the project for which you want to create an environment.</span></span>  
  
2.  <span data-ttu-id="26a91-112">Щелкните правой кнопкой мыши папку **Среды** и выберите команду **Создать среду**.</span><span class="sxs-lookup"><span data-stu-id="26a91-112">Right-click the **Environments** folder, and then click **Create Environment**.</span></span>  
  
3.  <span data-ttu-id="26a91-113">Введите имя для среды и, при желании, описание, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="26a91-113">Type a name for the environment and optionally a description, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="26a91-114">Щелкните правой кнопкой мыши новую среду и выберите команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="26a91-114">Right-click the new environment and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="26a91-115">На странице **Переменные** выполните следующие действия, чтобы добавить переменную.</span><span class="sxs-lookup"><span data-stu-id="26a91-115">On the **Variables** page, do the following to add a variable.</span></span>  
  
    1.  <span data-ttu-id="26a91-116">Выберите **Тип** переменной.</span><span class="sxs-lookup"><span data-stu-id="26a91-116">Select the **Type** for the variable.</span></span> <span data-ttu-id="26a91-117">Имя переменной **не** обязательно должно совпадать с именем параметра проекта, сопоставленного с переменной.</span><span class="sxs-lookup"><span data-stu-id="26a91-117">The name of the variable **does not** need to match the name of the project parameter that you map to the variable.</span></span>  
  
    2.  <span data-ttu-id="26a91-118">Введите необязательное **Описание** для переменной.</span><span class="sxs-lookup"><span data-stu-id="26a91-118">Enter an optional **Description** for the variable.</span></span>  
  
    3.  <span data-ttu-id="26a91-119">Введите **Значение** переменной среды.</span><span class="sxs-lookup"><span data-stu-id="26a91-119">Enter the **Value** for the environment variable.</span></span>  
  
         <span data-ttu-id="26a91-120">Сведения о правилах для имен переменных сред см. в разделе **Переменная среды** в [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="26a91-120">For information about the rules for environment variable names, see the **Environment Variable** section in [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
    4.  <span data-ttu-id="26a91-121">Укажите, содержит ли переменная конфиденциальное значение, установив или сняв флажок **Конфиденциально** .</span><span class="sxs-lookup"><span data-stu-id="26a91-121">Indicate whether the variable contains sensitive value, by selecting or clearing the **Sensitive** checkbox.</span></span>  
  
         <span data-ttu-id="26a91-122">Если флажок **Конфиденциально**установлен, значение переменной не отображается в поле **Значение** .</span><span class="sxs-lookup"><span data-stu-id="26a91-122">If you select **Sensitive**, the variable value does not display in the **Value** field.</span></span>  
  
         <span data-ttu-id="26a91-123">Конфиденциальные значения шифруются в каталоге SSISDB.</span><span class="sxs-lookup"><span data-stu-id="26a91-123">Sensitive values are encrypted in the SSISDB catalog.</span></span> <span data-ttu-id="26a91-124">Дополнительные сведения о шифровании см. в разделе [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="26a91-124">For more information about the encryption, see [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
6.  <span data-ttu-id="26a91-125">На странице **Разрешения** предоставьте или запретите соответствующие разрешения выбранным пользователям и ролям, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="26a91-125">On the **Permissions** page, grant or deny permissions for selected users and roles by doing the following.</span></span>  
  
    1.  <span data-ttu-id="26a91-126">Щелкните **Обзор**и выберите одного или нескольких пользователей и ролей в диалоговом окне **Обзор всех участников** .</span><span class="sxs-lookup"><span data-stu-id="26a91-126">Click **Browse**, and then select one or more users and roles in the **Browse All Principals** dialog box.</span></span>  
  
    2.  <span data-ttu-id="26a91-127">В области **Имена входа или роли** выберите пользователя или роль, которой будут предоставлены или запрещены разрешения.</span><span class="sxs-lookup"><span data-stu-id="26a91-127">In the **Logins or roles** area, select the user or role that you want to grant or deny permissions for.</span></span>  
  
    3.  <span data-ttu-id="26a91-128">В области **Явно** щелкните **Предоставить** или **Запретить** рядом с каждым разрешением.</span><span class="sxs-lookup"><span data-stu-id="26a91-128">In the **Explicit** area, click **Grant** or **Deny** next to each permission.</span></span>  
  
7.  <span data-ttu-id="26a91-129">Чтобы создать скрипт среды, щелкните **Скрипт**.</span><span class="sxs-lookup"><span data-stu-id="26a91-129">To script the environment, click **Script**.</span></span> <span data-ttu-id="26a91-130">По умолчанию скрипт открывает новое окно редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="26a91-130">By default, the script displays in a new Query Editor window.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="26a91-131">Кнопку **Скрипт** необходимо нажимать после внесения таких изменений в свойства среды, как добавление переменной, и перед тем как будет нажата кнопка **ОК** в диалоговом окне **Свойства среды**.</span><span class="sxs-lookup"><span data-stu-id="26a91-131">You need to click **Script** after you've made one or changes to the environment properties, such as adding a variable, and before you click **OK** in the **Environment Properties** dialog box.</span></span> <span data-ttu-id="26a91-132">В противном случае скрипт создан не будет.</span><span class="sxs-lookup"><span data-stu-id="26a91-132">Otherwise, a script is not generated.</span></span>  
  
8.  <span data-ttu-id="26a91-133">Чтобы сохранить изменения в свойствах среды, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="26a91-133">Click **OK** to save your changes to the environment properties.</span></span>  
  
9. <span data-ttu-id="26a91-134">В узле **SSISDB** в обозревателе объектов раскройте папку **Проекты** , щелкните правой кнопкой мыши проект и выберите команду **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="26a91-134">Under the **SSISDB** node in Object Explorer, expand the **Projects** folder, right-click the project, and then click **Configure**.</span></span>  
  
10. <span data-ttu-id="26a91-135">На странице **Ссылки** нажмите кнопку **Добавить** , чтобы добавить среду, а затем нажмите кнопку **ОК** , чтобы сохранить ссылку на среду.</span><span class="sxs-lookup"><span data-stu-id="26a91-135">On the **References** page, click **Add** to add an environment, and then click **OK** to save the reference to the environment.</span></span>  
  
11. <span data-ttu-id="26a91-136">Снова щелкните правой кнопкой мыши проект и выберите пункт **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="26a91-136">Right-click the project again, and then click **Configure**.</span></span>  
  
12. <span data-ttu-id="26a91-137">Для сопоставления переменной среды с параметром, добавленным в пакет во время разработки, или с параметром, созданным во время преобразования проекта [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] в модель развертывания проекта, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="26a91-137">To map the environment variable to a parameter that you added to the package at design-time or to a parameter that was generated when you converted the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the project deployment model, do the following.,</span></span>  
  
    1.  <span data-ttu-id="26a91-138">На вкладке **Параметры** на странице **Параметры** нажмите кнопку обзора рядом с полем **Значение** .</span><span class="sxs-lookup"><span data-stu-id="26a91-138">In the **Parameters** tab on the **Parameters** page, click the browse button next to the **Value** field.</span></span>  
  
    2.  <span data-ttu-id="26a91-139">Нажмите кнопку **Использовать переменную среды**, а затем выберите созданную переменную среды.</span><span class="sxs-lookup"><span data-stu-id="26a91-139">Click **Use environment variable**, and then select the environment variable you created.</span></span>  
  
13. <span data-ttu-id="26a91-140">Для сопоставления переменной среды со свойством диспетчера соединений выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="26a91-140">To map the environment variable to a connection manager property, do the following.</span></span> <span data-ttu-id="26a91-141">Параметры для свойств диспетчера соединений автоматически создаются на сервере служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="26a91-141">Parameters are automatically generated on the SSIS server for the connection manager properties.</span></span>  
  
    1.  <span data-ttu-id="26a91-142">На вкладке **Диспетчеры соединений** на странице **Параметры** нажмите кнопку обзора рядом с полем **Значение**.</span><span class="sxs-lookup"><span data-stu-id="26a91-142">In the **Connection Managers** tab on the **Parameters** page, click the browse button next to the **Value** field.</span></span>  
  
    2.  <span data-ttu-id="26a91-143">Нажмите кнопку **Использовать переменную среды**, а затем выберите созданную переменную среды.</span><span class="sxs-lookup"><span data-stu-id="26a91-143">Click **Use environment variable**, and then select the environment variable you created.</span></span>  
  
14. <span data-ttu-id="26a91-144">Нажмите кнопку **ОК** дважды для сохранения изменений.</span><span class="sxs-lookup"><span data-stu-id="26a91-144">Click **OK** twice to save your changes.</span></span>  
  
  

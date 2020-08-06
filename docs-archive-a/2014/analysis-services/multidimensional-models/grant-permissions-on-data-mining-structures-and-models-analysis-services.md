---
title: Предоставление разрешений структурам и моделям интеллектуального анализа данных (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.roledesignerdialog.miningmodels.f1
helpviewer_keywords:
- data mining [Analysis Services], security
- permissions [Analysis Services], mining models
- mining models [Analysis Services], security
- mining structures [Analysis Services], security
- permissions [Analysis Services], mining structures
- user access rights [Analysis Services], mining structures
- user access rights [Analysis Services], mining models
ms.assetid: a0008004-e2b7-47db-acad-5fe7e12b130f
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0db849551bdb38615f280b123c98f0e9d3053d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734509"
---
# <a name="grant-permissions-on-data-mining-structures-and-models-analysis-services"></a><span data-ttu-id="f7961-102">Предоставление разрешений структурам интеллектуального анализа данных и моделям интеллектуального анализа данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="f7961-102">Grant permissions on data mining structures and models (Analysis Services)</span></span>
  <span data-ttu-id="f7961-103">По умолчанию, только администратор сервера службы Analysis Services обладает разрешениями на просмотр интеллектуального анализа данных или моделей интеллектуального анализа данных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="f7961-103">By default, only an Analysis Services server administrator has permissions to view data mining structures or mining models in the database.</span></span> <span data-ttu-id="f7961-104">Следуйте инструкциям, приведенным ниже, для предоставления разрешений пользователям без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="f7961-104">Follow the instructions below to grant permissions to non-administrator users.</span></span>  
  
## <a name="set-permissions-to-access-a-mining-structure"></a><span data-ttu-id="f7961-105">Установка разрешений для доступа к интеллектуальному анализу данных</span><span class="sxs-lookup"><span data-stu-id="f7961-105">Set permissions to access a mining structure</span></span>  
  
1.  <span data-ttu-id="f7961-106">Подключитесь к Analysis Services в среде SSMS.</span><span class="sxs-lookup"><span data-stu-id="f7961-106">In SSMS, connect to Analysis Services.</span></span> <span data-ttu-id="f7961-107">Если вам нужны пошаговые инструкции, см. раздел [Подключение из клиентских приложений (службы Analysis Services)](../instances/connect-from-client-applications-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="f7961-107">See [Connect from client applications &#40;Analysis Services&#41;](../instances/connect-from-client-applications-analysis-services.md) if you need help with the steps.</span></span>  
  
2.  <span data-ttu-id="f7961-108">Откройте папку **Базы данных** и выберите базу данных в Обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="f7961-108">Open the **Databases** folder, and select a database in Object Explorer.</span></span>  
  
3.  <span data-ttu-id="f7961-109">Щелкните правой кнопкой мыши **Роли** и выберите **Создать роль**.</span><span class="sxs-lookup"><span data-stu-id="f7961-109">Right-click **Roles** and choose **New Role**.</span></span>  
  
4.  <span data-ttu-id="f7961-110">На странице Общие, введите название и, при необходимости, описание.</span><span class="sxs-lookup"><span data-stu-id="f7961-110">In the General page, enter a name, and optionally, a description.</span></span> <span data-ttu-id="f7961-111">Данная страница также содержит несколько разрешений базы данных, таких как Полный Доступ, Обработка Базы данных и Чтение Описания.</span><span class="sxs-lookup"><span data-stu-id="f7961-111">The page also contains several database permissions, such as Full Control, Process Database, and Read Definition.</span></span> <span data-ttu-id="f7961-112">Ни одно из этих разрешений не нужно для доступа к интеллектуальному анализу данных.</span><span class="sxs-lookup"><span data-stu-id="f7961-112">None of these permissions are needed for data mining access.</span></span> <span data-ttu-id="f7961-113">Дополнительные сведения о разрешениях баз данных см. в разделе [Предоставление разрешений базы данных (Analysis Services)](grant-database-permissions-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="f7961-113">See [Grant database permissions &#40;Analysis Services&#41;](grant-database-permissions-analysis-services.md) for more information about database permissions.</span></span>  
  
5.  <span data-ttu-id="f7961-114">На вкладке **Интеллектуальный анализ данных** выберите **Чтение** или **Чтение/Запись**  для каждого интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="f7961-114">In the **Mining Structure** pane, select **Read** or **Read/Write**  for each data mining structure.</span></span>  
  
6.  <span data-ttu-id="f7961-115">На вкладке **Членство** , введите учетные записи пользователя Windows и группы, которые подключаются к Analysis Services, используя данную роль.</span><span class="sxs-lookup"><span data-stu-id="f7961-115">In the **Membership** pane, enter the Windows user and group accounts that connect to Analysis Services using this role.</span></span>  
  
7.  <span data-ttu-id="f7961-116">Нажмите **ОК** для завершения процесса создания роли.</span><span class="sxs-lookup"><span data-stu-id="f7961-116">Click **OK** to finish creating the role.</span></span>  
  
## <a name="set-permissions-to-access-a-mining-model"></a><span data-ttu-id="f7961-117">Установка разрешений для доступа к модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="f7961-117">Set permissions to access a mining model</span></span>  
 <span data-ttu-id="f7961-118">Для модели интеллектуального анализа данных роль может иметь разрешения **Чтение** или **Чтение/Запись** , так же как разрешения **Детализация** и **Чтение определения** , которые позволяют просматривать базовые данные.</span><span class="sxs-lookup"><span data-stu-id="f7961-118">For a data mining model, a role can have either **Read** or **Read/Write** permissions, as well as **Drillthrough** and **Read Definition** permissions that allow viewing and browsing the underlying data.</span></span>  
  
 <span data-ttu-id="f7961-119">**Примечание** . Если включить детализацию как структуры, так и модели интеллектуального анализа данных, то любой пользователь, член роли с разрешениями детализации в модели и структуре интеллектуального анализа данных также видит столбцы в структуре, даже если эти столбцы не входят в модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="f7961-119">**Note** If you enable drillthrough on both the mining structure and the mining model, any user who is a member of a role that has drillthrough permissions on the mining model and the mining structure can also view columns in the mining structure, even if those columns are not included in the mining model.</span></span> <span data-ttu-id="f7961-120">Поэтому, чтобы защитить конфиденциальные сведения, необходимо настроить представление источника данных для маскирования персональных данных и разрешать доступ к детализации структуры интеллектуального анализа данных только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="f7961-120">Therefore, to protect sensitive information, you should set up the data source view to mask personal information, and allow drillthrough access on the mining structure only when necessary.</span></span>  
  
 <span data-ttu-id="f7961-121">Чтобы предоставить разрешения на чтение или на чтение и запись роли базы данных, пользователь должен быть членом роли сервера служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] или роли базы данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , которая обладает разрешениями «Полный контроль» (администратор).</span><span class="sxs-lookup"><span data-stu-id="f7961-121">To grant read or read/write permissions to a database role, a user must be a member of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server role or a member of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database role that has Full Control (Administrator) permissions.</span></span>  
  
1.  <span data-ttu-id="f7961-122">В [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] подключитесь к экземпляру служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , разверните узел **роли** для соответствующей базы данных в обозревателе объектов, а затем щелкните роль базы данных (или создайте новую роль базы данных).</span><span class="sxs-lookup"><span data-stu-id="f7961-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], expand **Roles** for the appropriate database in Object Explorer, and then click a database role (or create a new database role).</span></span>  
  
2.  <span data-ttu-id="f7961-123">На вкладке **Интеллектуальный анализ** поместите модель интеллектуального анализа в список **Модели интеллектуального анализа** , а затем выберите **Чтение**, **Чтение/Запись**, **Детализация**или **Навигация** для данной модели интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="f7961-123">In the **Mining Structure** pane, locate the mining model in the **Mining Models** list, and then select **Read**, **Read/Write**, **Drill Through**, or **Browse** for that mining model.</span></span>  
  
3.  <span data-ttu-id="f7961-124">На вкладке **Членство** , введите учетные записи пользователя Windows и группы, которые подключаются к Analysis Services, используя данную роль.</span><span class="sxs-lookup"><span data-stu-id="f7961-124">In the **Membership** pane, enter the Windows user and group accounts that connect to Analysis Services using this role.</span></span>  
  
4.  <span data-ttu-id="f7961-125">Нажмите **ОК** для завершения процесса создания роли.</span><span class="sxs-lookup"><span data-stu-id="f7961-125">Click **OK** to finish creating the role.</span></span>  
  
 <span data-ttu-id="f7961-126">Чтобы использовать источник данных в запросе детализации, применяющем предложение OPENQUERY расширения интеллектуального анализа данных, роль базы данных также должна иметь разрешения на чтение и запись в соответствующий объект источника данных.</span><span class="sxs-lookup"><span data-stu-id="f7961-126">To use a data source in a drillthrough query that uses the Data Mining Extensions (DMX) OPENQUERY clause, the database role also needs read/write permission on the appropriate data source object.</span></span> <span data-ttu-id="f7961-127">Дополнительные сведения см. в разделах [Предоставление разрешений объекту источника данных (службы Analysis Services)](grant-permissions-on-a-data-source-object-analysis-services.md) и [OPENQUERY (расширения интеллектуального анализа данных)](/sql/dmx/source-data-query-openquery).</span><span class="sxs-lookup"><span data-stu-id="f7961-127">For more information, see [Grant permissions on a data source object &#40;Analysis Services&#41;](grant-permissions-on-a-data-source-object-analysis-services.md) and [OPENQUERY &#40;DMX&#41;](/sql/dmx/source-data-query-openquery).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f7961-128">По умолчанию выдача запросов расширений интеллектуального анализа данных с использованием OPENROWSET отключена.</span><span class="sxs-lookup"><span data-stu-id="f7961-128">By default, the submission of DMX queries by using OPENROWSET is disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7961-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="f7961-129">See Also</span></span>  
 <span data-ttu-id="f7961-130">[Предоставление разрешений администратора сервера &#40;Analysis Services&#41;](../instances/grant-server-admin-rights-to-an-analysis-services-instance.md) </span><span class="sxs-lookup"><span data-stu-id="f7961-130">[Grant Server Administrator Permissions &#40;Analysis Services&#41;](../instances/grant-server-admin-rights-to-an-analysis-services-instance.md) </span></span>  
 <span data-ttu-id="f7961-131">[Предоставление разрешений куба или модели &#40;Analysis Services&#41;](grant-cube-or-model-permissions-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="f7961-131">[Grant cube or model permissions &#40;Analysis Services&#41;](grant-cube-or-model-permissions-analysis-services.md) </span></span>  
 <span data-ttu-id="f7961-132">[Предоставление настраиваемого доступа к данным измерения &#40;Analysis Services&#41;](grant-custom-access-to-dimension-data-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="f7961-132">[Grant custom access to dimension data &#40;Analysis Services&#41;](grant-custom-access-to-dimension-data-analysis-services.md) </span></span>  
 [<span data-ttu-id="f7961-133">Предоставление настраиваемого доступа к данным ячейки (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="f7961-133">Grant custom access to cell data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-cell-data-analysis-services.md)  
  
  

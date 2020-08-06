---
title: Соединение с сервером (страница "Дополнительные параметры соединения") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttoserver.options.registeredservers.f1
ms.assetid: ba34b01a-6289-4eb8-8341-fa3d9ec87b3f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5c6a23df6a6b9ea324d54fd270f5aa2269471ed8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669091"
---
# <a name="connect-to-server-additional-connection-parameters-page"></a><span data-ttu-id="8fb4f-102">Соединение с сервером (страница «Дополнительные параметры соединения»)</span><span class="sxs-lookup"><span data-stu-id="8fb4f-102">Connect to Server (Additional Connection Parameters Page)</span></span>
  <span data-ttu-id="8fb4f-103">В диалоговом окне **Подключение к** среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] наиболее широко применяемые значения в строке подключения представлены в виде параметров.</span><span class="sxs-lookup"><span data-stu-id="8fb4f-103">The **Connect to** dialog box of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] presents the most common connection string values as options.</span></span> <span data-ttu-id="8fb4f-104">С помощью страницы **Дополнительные параметры соединения** можно добавить дополнительные параметры соединения к строке подключения.</span><span class="sxs-lookup"><span data-stu-id="8fb4f-104">Use the **Additional Connection Parameters** page to add more connection parameters to the connection string.</span></span>  
  
-   <span data-ttu-id="8fb4f-105">Дополнительными параметрами соединения могут быть любые параметры соединения ODBC.</span><span class="sxs-lookup"><span data-stu-id="8fb4f-105">Additional connection parameters can be any ODBC connection parameter.</span></span>  
  
-   <span data-ttu-id="8fb4f-106">Дополнительные параметры соединения следует добавлять в формате **;параметр1=значение1;параметр2=значение2**.</span><span class="sxs-lookup"><span data-stu-id="8fb4f-106">Additional connection parameters should be added in the format **;parameter1=value1;parameter2=value2**.</span></span>  
  
-   <span data-ttu-id="8fb4f-107">Параметры, добавленные с помощью страницы **Дополнительные параметры соединения** , добавляются к параметрам, выбранным с помощью параметров диалогового окна **Подключение к** .</span><span class="sxs-lookup"><span data-stu-id="8fb4f-107">Parameters added using the **Additional Connection Parameters** page are added to the parameters selected using the **Connect to** dialog box options.</span></span>  
  
-   <span data-ttu-id="8fb4f-108">Последний экземпляр каждого заданного параметра переопределяет все предыдущие экземпляры этого параметра.</span><span class="sxs-lookup"><span data-stu-id="8fb4f-108">The last instance of each parameter provided overrides any previous instances of the parameter.</span></span> <span data-ttu-id="8fb4f-109">Параметры, добавленные с помощью окна **Дополнительные параметры соединения** , дополняют и заменяют параметры, заданные на вкладке **Имя входа** или **Свойства соединения** .</span><span class="sxs-lookup"><span data-stu-id="8fb4f-109">Parameters added using the **Additional Connection Parameters** page follow and replace the parameters provided in the **Login** or **Connection Properties** tabs.</span></span> <span data-ttu-id="8fb4f-110">Например, если на вкладке **Имя входа** параметру **Имя сервера** задано значение **SERVER1**, а на странице **Дополнительные параметры соединения** содержится параметр **;SERVER=SERVER2**, соединение будет установлено с **SERVER2**.</span><span class="sxs-lookup"><span data-stu-id="8fb4f-110">For example, if the **Login** tab provides **SERVER1** as the **Server name**, and the **Additional Connection Parameters** page contains **;SERVER=SERVER2**, the connection will be made to **SERVER2**.</span></span>  
  
-   <span data-ttu-id="8fb4f-111">Параметры, добавляемые с помощью страницы **Дополнительные параметры соединения** , всегда передаются в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="8fb4f-111">Parameters added using the **Additional Connection Parameters** page are always passed as plain text.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8fb4f-112">Не указывайте учетные данные и пароли для входа на странице **Дополнительные параметры соединения** .</span><span class="sxs-lookup"><span data-stu-id="8fb4f-112">Do not include login credentials and passwords in the **Additional Connection Parameters** page.</span></span> <span data-ttu-id="8fb4f-113">Они не будут зашифрованы при передаче по сети.</span><span class="sxs-lookup"><span data-stu-id="8fb4f-113">They will not be encrypted when they are passed across the network.</span></span> <span data-ttu-id="8fb4f-114">Вместо этого используйте вкладку **Имя входа** .</span><span class="sxs-lookup"><span data-stu-id="8fb4f-114">Use the **Login** tab instead.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="8fb4f-115">Список задач</span><span class="sxs-lookup"><span data-stu-id="8fb4f-115">Task List</span></span>  
  
### <a name="to-show-the-additional-connection-parameters-page"></a><span data-ttu-id="8fb4f-116">Отображение страницы «Дополнительные параметры соединения»</span><span class="sxs-lookup"><span data-stu-id="8fb4f-116">To show the Additional Connection Parameters page</span></span>  
  
1.  <span data-ttu-id="8fb4f-117">В среде [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]в меню **Запрос** наведите указатель на пункт **Соединение**и выберите команду **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="8fb4f-117">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], on the **Query** menu, point to **Connection**, and then click **Connect**.</span></span>  
  
2.  <span data-ttu-id="8fb4f-118">В диалоговом окне **Подключение к** щелкните **Параметры**и перейдите на вкладку **Дополнительные параметры соединения** .</span><span class="sxs-lookup"><span data-stu-id="8fb4f-118">In the **Connect to** dialog box, click **Options**, and then click the **Additional Connection Parameters** tab.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8fb4f-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="8fb4f-119">Examples</span></span>  
  
### <a name="example-a-connecting-to-the-database-engine"></a><span data-ttu-id="8fb4f-120">Пример А. Соединение с ядром СУБД</span><span class="sxs-lookup"><span data-stu-id="8fb4f-120">Example A: Connecting to the Database Engine</span></span>  
 <span data-ttu-id="8fb4f-121">Чтобы подключиться к базе данных [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] на сервере ACCOUNTING, введите следующее на странице **Дополнительные параметры соединения** :</span><span class="sxs-lookup"><span data-stu-id="8fb4f-121">To connect to the [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] database on a server named ACCOUNTING, enter the following in the **Additional connection parameters** page:</span></span>  
  
```  
;SERVER=ACCOUNTING;DATABASE=AdventureWorks2012  
```  
  
### <a name="example-b-connecting-to-analysis-services"></a><span data-ttu-id="8fb4f-122">Пример Б. Соединение со службами Analysis Services</span><span class="sxs-lookup"><span data-stu-id="8fb4f-122">Example B: Connecting to Analysis Services</span></span>  
 <span data-ttu-id="8fb4f-123">Чтобы подключиться к службам Analysis Services, указать, что все секции, прослушивающие уведомления, должны запрашиваться в реальном времени (с обходом кэширования) и задать время ожидания обратной записи равным 5, введите следующее на странице **Дополнительные параметры соединения** :</span><span class="sxs-lookup"><span data-stu-id="8fb4f-123">To connect to the Analysis Servers and cause all the partitions listening for notifications to be queried as real time (bypassing caching), and to set the writeback time out value to 5, enter the following in the **Additional connection parameters** page:</span></span>  
  
```  
;Real Time Olap=TRUE;Writeback Timeout=5  
```  
  
  
